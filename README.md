# AutoCAD (autocad)

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
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

APIs for Autodesk AutoCAD, providing programmatic access to CAD design, drawing, and automation capabilities through Autodesk Platform Services (APS, formerly Forge) and desktop development environments including AutoLISP, ObjectARX, .NET, and JavaScript.

**URL:** [https://www.autodesk.com/developer-network/platform-technologies/autocad](https://www.autodesk.com/developer-network/platform-technologies/autocad)

**Run:** [Capabilities Using Naftiko](https://github.com/naftiko/fleet?utm_source=api-evangelist&utm_medium=readme&utm_campaign=company-api-evangelist&utm_content=repo)

## Tags:

 - 3D Modeling, Architecture, CAD, Design, Drawing, Engineering

## Timestamps

- **Created:** 2024-01-01
- **Modified:** 2026-04-18

## APIs

### AutoCAD API
Core API for AutoCAD automation, drawing manipulation, and entity management.

**Human URL:** [https://www.autodesk.com/developer-network/platform-technologies/autocad](https://www.autodesk.com/developer-network/platform-technologies/autocad)

#### Tags:

 - Automation, CAD, Drawing, Entities

### AutoCAD Design Automation API
Cloud-based API that enables running AutoCAD scripts and custom add-ins in the cloud for batch processing at scale.

**Human URL:** [https://aps.autodesk.com/apis-and-services/autocad-automation-api](https://aps.autodesk.com/apis-and-services/autocad-automation-api)

#### Tags:

 - AutoLISP, Batch Processing, Cloud, Design Automation, Scripting

### AutoCAD Data Management API
API for managing AutoCAD files, versions, and collaboration workflows.

**Human URL:** [https://forge.autodesk.com/en/docs/data/v2/developers_guide/overview/](https://forge.autodesk.com/en/docs/data/v2/developers_guide/overview/)

#### Tags:

 - Collaboration, File Management, Storage, Version Control

### AutoCAD Model Derivative API
API for translating AutoCAD design files into formats like SVF and SVF2 for rendering in the Viewer SDK.

**Human URL:** [https://aps.autodesk.com/developer/overview/model-derivative-api](https://aps.autodesk.com/developer/overview/model-derivative-api)

#### Tags:

 - File Conversion, Metadata, Model Derivative, Thumbnails, Translation

### AutoCAD Webhooks API
API enabling applications to listen for and receive notifications when specific events occur in AutoCAD data and workflows.

**Human URL:** [https://aps.autodesk.com/developer/overview/webhooks-api](https://aps.autodesk.com/developer/overview/webhooks-api)

#### Tags:

 - Events, Notifications, Real-Time, Webhooks

### AutoCAD Authentication API
OAuth 2.0-based authentication API for securing access to AutoCAD and Autodesk Platform Services APIs.

**Human URL:** [https://aps.autodesk.com/developer/overview/authentication-api](https://aps.autodesk.com/developer/overview/authentication-api)

#### Tags:

 - Authentication, Authorization, OAuth, Security

## Features

| Name | Description |
|------|-------------|
| Cloud-Based Design Automation | Run AutoCAD scripts and add-ins in the cloud for batch processing without local AutoCAD installation. |
| 3D Model Translation | Translate CAD files between formats and extract metadata for web-based viewing and analysis. |
| File Version Management | Manage design file versions, revisions, and collaboration workflows through the Data Management API. |
| Event-Driven Webhooks | Receive real-time notifications when design files are created, updated, or shared. |
| OAuth 2.0 Authentication | Secure API access with 2-legged and 3-legged OAuth flows for application and user-level authorization. |
| Web-Based Viewer | Embed 2D and 3D design viewers in web applications with the Viewer SDK. |

## Use Cases

| Name | Description |
|------|-------------|
| Automated Drawing Generation | Generate construction drawings, floor plans, and engineering diagrams automatically using Design Automation API. |
| Design File Collaboration | Build collaborative design workflows with file sharing, version control, and real-time notifications. |
| Batch File Processing | Process thousands of CAD files in the cloud for format conversion, data extraction, and quality checks. |
| BIM Integration | Integrate Building Information Modeling data with enterprise systems for construction project management. |
| Custom CAD Applications | Build custom AutoCAD plugins and extensions using ObjectARX, .NET, AutoLISP, or JavaScript APIs. |

## Integrations

| Name | Description |
|------|-------------|
| Autodesk Construction Cloud | Integration with ACC for construction project management and design coordination. |
| BIM 360 | Cloud-based BIM collaboration platform integration for construction workflows. |
| Revit | Interoperability with Revit for architectural design and BIM workflows. |
| Navisworks | Integration for 3D coordination, clash detection, and project review. |
| Power BI | Data visualization integration for design analytics and project reporting. |

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
