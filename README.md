# Rex Airlines (rex-airlines)

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

## Common

- [Website](https://www.rex.com.au/)
- [Travel Agent Portal](https://www.rex.com.au/TravelAgent/Index.aspx)
- [Travel Agent Registration](https://www.rex.com.au/TravelAgent/agentregistration.aspx)
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
- [Contact Us](https://www.rex.com.au/FeedBack/ContactUs.aspx)
- [Media Releases](https://www.rex.com.au/MediaAndCommunications/)
- [LinkedIn](https://au.linkedin.com/company/regional-express/)
- [Twitter](https://twitter.com/rexairlines)
- [Facebook](https://www.facebook.com/Rex-116487266942908/)
- [Instagram](https://www.instagram.com/rex.airlines/)

## Maintainers

- Kin Lane — kin@apievangelist.com
