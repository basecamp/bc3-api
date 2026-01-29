# Basecamp 4 API Documentation Repo

Docs-only repo — no code, no build system. `README.md` is the main guide (auth, pagination, domain model, endpoint index). `sections/` has one `.md` per API resource (~47 files).

## Section file format

Every `sections/*.md` follows this structure:

1. H1 title with `=====` underline, H2 per endpoint with `-----` underline (Setext, not ATX)
2. Endpoints bullet list with anchor links: `- [Get messages](#get-messages)`
3. Endpoint description as bullet: `* \`GET /buckets/1/...\`` with prose
4. `###### Example JSON Response` then `<!-- START GET /path -->` / `<!-- END GET /path -->` wrapping `` ```json `` block
5. `###### Copy as cURL` then `` ```shell `` block using `$ACCESS_TOKEN` and `$ACCOUNT_ID` env vars
6. Write endpoints add `###### Example JSON Request` before the cURL
7. `**Required parameters**:` (bold) and `_Optional parameters_:` (italic) with bullet lists
8. Reference-style links at bottom: `[1]: https://...`, `[pagination]: ...`

## README.md endpoint index

Lives between `<!-- START API ENDPOINTS -->` and `<!-- END API ENDPOINTS -->`. New sections go alphabetically.

## Commit messages

Imperative verb + description + `(#PR)`: `Add API documentation for timeline endpoints (#369)`

## Constraints

- No YAML frontmatter
- Don't invent API endpoints — only document real ones
- Don't add files outside `sections/` and repo root
