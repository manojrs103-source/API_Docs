# Publishing API Documentation

## 1. Purpose

Publishing makes the approved API documentation available to its intended audience.

The publication destination depends on the organization's documentation process. It may be a developer portal, an API reference site, an internal knowledge base, or a Git repository.

## 2. Common publishing options

| Platform | Typical use |
|---|---|
| GitHub | Store Markdown and OpenAPI source files with version history |
| Confluence | Publish internal knowledge and collaboration pages |
| Swagger UI | Render an interactive API reference from an OpenAPI document |
| Developer portal | Provide API guides and references to external or internal developers |

These are common options, not a confirmed list of platforms used by Tekion.

## 3. Suggested GitHub structure

```text
API_Docs/
├── README.md
├── docs/
│   ├── 01-api-overview.md
│   ├── 02-information-gathering.md
│   ├── 03-api-specifications.md
│   ├── 04-api-testing-postman.md
│   ├── 05-api-reference.md
│   ├── 06-request-response-examples.md
│   ├── 07-error-handling.md
│   ├── 08-developer-review.md
│   ├── 09-publishing.md
│   └── 10-maintenance.md
└── openapi/
    └── vehicle-inventory.yaml
```

## 4. Publishing workflow

1. Complete the technical and editorial reviews.
2. Validate Markdown links and the OpenAPI file.
3. Check examples for secrets and sensitive data.
4. Commit the approved changes to the designated branch.
5. Create a pull request if the repository uses review-based changes.
6. Obtain required approvals.
7. Merge or publish through the team's approved process.
8. Verify the published pages and navigation.
9. Communicate the publication to the intended audience.

## 5. Publication checklist

- [ ] Correct API name and version.
- [ ] Approved endpoint information.
- [ ] Working internal links.
- [ ] Valid code blocks and JSON examples.
- [ ] Valid OpenAPI file.
- [ ] No secrets or sensitive customer data.
- [ ] Technical approval recorded.
- [ ] Correct access permissions.
- [ ] Published pages render correctly.

## 6. Important distinction

Committing a Markdown file to GitHub stores and versions the source. It does not automatically create a fully featured API developer portal. Interactive reference rendering generally requires a tool such as Swagger UI or another documentation platform.
