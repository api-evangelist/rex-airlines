# Rex Airlines (rex-airlines)

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

Rex Airlines (Regional Express, IATA ZL / ICAO RXA) is Australia's second-largest regional carrier, headquartered in Mascot, New South Wales, flying a Saab 340 fleet to roughly 45 regional destinations across every Australian state. Formed in 2002 from the merger of Hazelton and Kendell Airlines, Rex entered voluntary administration in July 2024 and was acquired by US holding company Air T in December 2025 with Australian federal government debt support. In the distribution chain Rex is the inventory owner, not an intermediary — it runs Sabre's SabreSonic passenger service suite (inventory, reservations, ticketing, ancillaries, check-in) per Sabre's February 2021 announcement, sells direct through its own ASP.NET booking engine at ibe2.rex.com.au, and reaches trade through a web-only Travel Agent portal gated on an IATA, DAPA or TIDS agency number. Its API posture is honest to state plainly: no developer portal, no public documentation, no OpenAPI, and no NDC claim anywhere on rex.com.au. The only published trace of a programmatic interface is a bare "Request API Access" checkbox on the agent registration form — accreditation required, contract unspecified, nothing documented, and no exit path beyond a privacy-law request to the Customer Contact Centre.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/rex-airlines/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/rex-airlines/refs/heads/main/apis.yml)

## Tags

- Travel
- Australia
- Aviation
- Airline
- Regional Aviation
- Distribution
- Booking
- Corporate Travel
- Loyalty
- Freight

## Timestamps

- **Created:** 2026-07-28
- **Modified:** 2026-07-28

## APIs

None listed.

Rex Airlines publishes no documented API. `developer.rex.com.au`, `developers.rex.com.au`, `api.rex.com.au` and `docs.rex.com.au` do not resolve; `/developers`, `/api`, `/docs`, `/openapi.json`, `/swagger.json`, `/api-docs`, `/.well-known/security.txt`, `/robots.txt` and `/sitemap.xml` all return 404 on `www.rex.com.au`.

The one real trace of a programmatic interface is a checkbox labelled **"Request API Access"** on the travel agent registration form at `/TravelAgent/agentregistration.aspx`. It carries no specification, no name, no base URL, no terms and no pricing, and it sits behind a mandatory IATA / DAPA / TIDS accreditation number. Because nothing about it is published, it is not listed as an API here — it is recorded as evidence in [review.yml](review.yml).

## Switching Cost

| Dimension | Finding |
| --- | --- |
| Interface shape | `proprietary-undocumented` — no standard named anywhere; no NDC, no OpenTravel/OTA, no HTNG |
| Second source | `no-alternative` — Rex is the sole operator on most of its ~45 regional ports, and aggregators can only resell what Rex files |
| Exit path | `export-on-request` — agent statements capped at 4 months' download / 2 months' retention; consumer data only via a Privacy Act 1988 (Cth) APP request to the Customer Contact Centre |
| Identifier portability | IATA `ZL` / ICAO `RXA`, IATA airport codes and IATA/TIDS agency numbers are portable; the "Booking Reloc" PNR locator, Rex Flyer number and Rex Points balance are not |
| Contractual lock-in | Commission payable only on bookings made inside a logged-in portal session; accreditation number immutable for the life of the registration; Rex Points non-transferable, non-cashable, expiring on a rolling 36 months; automated access to the site prohibited without prior express written consent |
| Distribution model | `gds-intermediated` — SabreSonic PSS carries inventory, reservations and ticketing, with direct web and an HTML agent portal layered on top |
| NDC posture | Absent — no certification claimed, no NDC endpoint, no GDS surcharge published; Rex is not in Duffel's NDC-certified listing while Qantas is |
| Access gate | `accredited-or-licensed` — ABN, Australian travel agency licence number, IATA/DAPA/TIDS accreditation, agency bank/BSB details, and an RCTI/GST agreement, before an undocumented API request is even considered |

## Artifacts

| Artifact | File | Method | Finding |
| --- | --- | --- | --- |
| Domain security | [security/rex-airlines-domain-security.yml](security/rex-airlines-domain-security.yml) | probed | TLS 1.3 on four of five hosts (Rex Flyer still TLS 1.2); no HSTS on `www` or the loyalty host; no CAA and no DNSSEC on either domain; `rex.com.au` DMARC is `p=none`; `rexflyer.com.au` publishes no SPF and no DMARC at all. |
| Well-known | [well-known/rex-airlines-well-known.yml](well-known/rex-airlines-well-known.yml) | probed | Recorded negative — no `/.well-known/` surface (security.txt, OIDC, RFC 8414, api-catalog, ai-plugin) and no `/llms.txt` on any of the five hosts. No pointer wired, because nothing exists. |
| llms.txt | [llms/rex-airlines-llms.txt](llms/rex-airlines-llms.txt) | generated | Written by API Evangelist from this catalog record — Rex publishes none. States the no-API posture plainly and separates third-party Rex data resellers (Aviation Edge, Airhex, Flightera) from anything Rex itself offers. |

No packages, SDKs, CLI, MCP server, OpenAPI, AsyncAPI, changelog, status page, trust centre or vulnerability-disclosure programme was found. Those artifacts are absent from this repo rather than stubbed — an empty result is a real result.

## Common

- [Website](https://www.rex.com.au/)
- [Travel Agent Portal](https://www.rex.com.au/TravelAgent/Index.aspx)
- [Travel Agent Registration](https://www.rex.com.au/TravelAgent/agentregistration.aspx) — also wired as `SignUp`; the only published route to programmatic access
- [Travel Agent FAQ](https://www.rex.com.au/TravelAgent/faq.aspx)
- [Booking Engine](https://ibe2.rex.com.au/)
- [Manage Booking](https://mbe.rex.com.au/)
- [Flight Schedules](https://www.rex.com.au/Schedules/default.aspx)
- [Network](https://www.rex.com.au/FlightInfo/Network.aspx)
- [Loyalty Program](https://www.rex.com.au/rexflyer/LoyaltyHomePage.aspx)
- [Loyalty Terms of Service](https://www.rex.com.au/rexflyer/RexFlyerTC.aspx)
- [Terms of Service](https://www.rex.com.au/site_terms.aspx)
- [Conditions of Carriage](https://www.rex.com.au/FlightInfo/COC.aspx)
- [Privacy Policy](https://www.rex.com.au/privacy.aspx)
- [Freight](https://www.rex.com.au/Products_Promo/Freight/Default.aspx)
- [Corporate](https://www.rex.com.au/Corporate/)
- [About](https://www.rex.com.au/AboutRex/OurCompany/overview.aspx)
- [Contact Us](https://www.rex.com.au/FeedBack/ContactUs.aspx) — also wired as `Support`
- [Media Releases](https://www.rex.com.au/MediaAndCommunications/)
- [LinkedIn](https://au.linkedin.com/company/regional-express/)
- [Twitter](https://twitter.com/rexairlines)
- [Facebook](https://www.facebook.com/Rex-116487266942908/)
- [Instagram](https://www.instagram.com/rex.airlines/)

## Maintainers

- Kin Lane — kin@apievangelist.com
