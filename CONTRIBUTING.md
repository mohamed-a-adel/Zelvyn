# Contributing to the Zelvyn API handbook

Thanks for helping improve the public Zelvyn API documentation. This repository
is the public handbook: the endpoint reference, the OpenAPI mirror, and
copy-pasteable examples in 13 languages.

## Ways to contribute

- **Fix documentation** — typos, unclear wording, broken links, or an example
  that does not match the live API.
- **Improve an example** — make a snippet more idiomatic for its language while
  keeping it copy-pasteable.
- **Report a mismatch** — if the live API behaves differently from this
  handbook, open an issue with the request id from the response.
- **Suggest a new example or language** — open a feature request first so we can
  agree on the shape before you write it.

## Ground rules

- **Never include a live API key, token, password, or personal data** in an
  issue, pull request, commit, or code sample. Use a placeholder such as
  `zlv_live_<keyId>_<secret>`.
- **Do not open public issues for security problems.** Follow
  [SECURITY.md](SECURITY.md) instead.
- Be respectful and follow the [Code of Conduct](CODE_OF_CONDUCT.md).
- Keep examples keyless by default. Every endpoint works without a key; an API
  key is optional and only raises the caller's rate limit. If you show the
  optional header, keep it clearly marked as optional.
- Do not publish fake flows, fictional SDKs, or features that do not exist.

## Editing the handbook

The endpoint pages, language pages, and most of the README are **generated** from
the live OpenAPI document. Do not edit those files by hand — a regeneration will
overwrite the change.

- Generated files: `README.md`, `docs/authentication.md`, `docs/errors.md`,
  `docs/rate-limits.md`, `docs/versioning.md`, `docs/endpoints/**`,
  `docs/languages/**`, `openapi.json`, `requests.json`.
- Hand-maintained files: this file, `CODE_OF_CONDUCT.md`, `LICENSE`,
  `SECURITY.md`, `ACCESSIBILITY.md`, and `.github/**`.

For a generated-page change, describe the correct wording in the issue or pull
request and the maintainer will update the generator.

## Submitting a change

1. Fork the repository and create a short, descriptive branch.
2. Make the smallest change that fixes the problem.
3. Check every link and code fence you touched.
4. If you changed an example, run it against a test or live endpoint when you
   can, and say which one in the pull request.
5. Open a pull request using the template. Link the issue it closes.
6. Keep the pull request focused: one topic per pull request.

## Commit messages

Use a clear, imperative subject line, for example:

```text
docs: correct the mean response example
fix: repair the Python timeout example
```

## Review

A maintainer reviews every pull request. Documentation fixes are usually
reviewed quickly; changes that alter the public contract or add a new language
need a longer review. We may ask you to split a large pull request.

## License

By contributing, you agree that your contribution is published under the terms
in [LICENSE](LICENSE). You confirm that you wrote the contribution or have the
right to submit it.
