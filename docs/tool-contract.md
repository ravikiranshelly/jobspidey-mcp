# v1 tools and permissions

Contract status: production direct SDK and native Codex acceptance passed. The
server's live `tools/list` schemas are authoritative after validation. Account
identity comes from the grant; tools never accept a customer ID to select an
account. Every stateful request requires a caller-generated `request_id`.

| Tool | Purpose | Required permission |
| --- | --- | --- |
| `get_account_context` | Read connection limits, readiness, saved preferences, supported sites/countries and published templates. | Basic connection |
| `get_candidate_context` | Read permitted candidate facts and uncertainty; master-resume text is explicit. | `profile:read`; additional `resume:read` for `include_resume_text` |
| `search_jobs` | Start an owned search and return search/operation handles. | `jobs:search`, `jobs:read` |
| `list_search_results` | Page brief results within the specified owned search. | `jobs:read` |
| `get_job` | Read a stable owned job and its description quality. | `jobs:read` |
| `load_more_jobs` | Extend the exact search when the provider supports it. | `jobs:search`, `jobs:read` |
| `prepare_application` | Prepare one job, owned application or custom job; reuse existing packages. | `documents:generate` |
| `get_operation` | Read progress, action requirements and retry timing. | Permissions appropriate to the operation |
| `get_application_package` | Read readiness, delivered text/manifests and expiring PDF links. | `applications:read`, `documents:read` |
| `list_applications` | Read tracker summaries and document readiness. | `applications:read` |
| `record_application_outcome` | Persist an authorized external-outcome report and tracker update. | Optional `applications:write` |

Default consent does not include master-resume text or application-write access.
Normal customer generation entitlements apply. Replaying/reusing accepted work
and refreshing package links do not create another generation charge. Return
structured errors and server-directed retry hints; do not retry changed input
under an accepted request key.

Search results remain attached to their original search. Default result pages
contain ten brief jobs, maximum 25. Full job descriptions and resume text are
explicit reads. One active initial search per account and seven-day search
snapshot retention are v1 service limits, subject to current server policy.

Operations use `queued`, `running`, `needs_input`, `succeeded`, `partial`, and
`failed`. A succeeded worker is not proof of package readiness. A complete
package needs two valid delivered PDFs. Missing artifacts, empty paths and
generation-error markers are not usable files. If one PDF is available, report
a partial package. Links are short-lived and bound to the owned grant, artifact
and revision; disconnect/scope removal invalidates existing links.

The runtime exposes each of these eleven operations with bounded schemas and
explicit `readOnlyHint`, `destructiveHint` and `openWorldHint` booleans. Public
metadata and results describe behavior without hidden instructions or promotion.
This bundle does not implement tools, an employer browser, submission, a
scheduler, email sending, document editing, or automatic purchases.
