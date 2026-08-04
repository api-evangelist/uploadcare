# Uploadcare (uploadcare)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Uploadcare is a file uploading and processing platform that provides REST APIs for file management, CDN delivery, image transformations, document conversion, video encoding, and malware scanning. Developers can integrate file upload widgets, manage files and metadata, apply on-the-fly image transformations via URL-based CDN API, handle multipart uploads for large files, configure webhooks, and leverage add-ons for extended processing capabilities.

**APIs.json:** https://raw.githubusercontent.com/api-evangelist/uploadcare/refs/heads/main/apis.yml

**Naftiko:** https://github.com/naftiko/fleet?utm_source=api-evangelist&utm_medium=readme&utm_campaign=uploadcare-api-evangelist&utm_content=repo

## Tags

- File Upload
- File Management
- CDN
- Image Transformation
- Document Conversion
- Video Encoding
- Malware Scanning
- Storage
- Webhooks

## APIs

| Name | Description | Docs |
|------|-------------|------|
| Uploadcare REST API | Manage files, groups, webhooks, add-ons, conversions, and video encoding via signed REST requests | [Docs](https://uploadcare.com/docs/rest_api/) |
| Uploadcare Upload API | Direct binary, multipart, URL-based, and UUID-based file uploads up to 5 TB | [Docs](https://uploadcare.com/docs/api/upload/) |
| Uploadcare CDN & Image Transformation API | URL-based on-the-fly image transformations cached on global Smart CDN | [Docs](https://uploadcare.com/docs/api_reference/cdn/) |

## Plans, Rate Limits & FinOps

| Resource | File |
|----------|------|
| Plans & Pricing | [plans/uploadcare-plans-pricing.yml](plans/uploadcare-plans-pricing.yml) |
| Rate Limits | [rate-limits/uploadcare-rate-limits.yml](rate-limits/uploadcare-rate-limits.yml) |
| FinOps Framework | [finops/uploadcare-finops.yml](finops/uploadcare-finops.yml) |

**Pricing Summary:**
- Free: $0/month — 1,000 operations, 10 MB max file size
- Pro: $66/month — 100,000 operations, 1 GB max file size
- Business: $166/month — 250,000 operations, 10 GB max file size
- Enterprise: Custom pricing

## Timestamps

- **Created:** 2026-06-12
- **Modified:** 2026-06-12

## Common

| Type | URL |
|------|-----|
| Website | https://uploadcare.com/ |
| Documentation | https://uploadcare.com/docs/ |
| GitHub | https://github.com/uploadcare |
| LinkedIn | https://www.linkedin.com/company/uploadcare |
| Blog | https://uploadcare.com/blog/ |
| Pricing | https://uploadcare.com/pricing/ |
| Status Page | https://status.uploadcare.com/ |
| X (Twitter) | https://twitter.com/uploadcare |

## Maintainers

| Name | Email |
|------|-------|
| Kin Lane | kin@apievangelist.com |
