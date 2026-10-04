# Northwest Calgary Single-Detached Property Search Specification

**Document Version:** 2.1  
**Target Market:** Northwest Calgary (NW), Alberta, Canada  
**Target School Catchment:** William Aberhart High School (Transit & Drive Corridor)  
**Last Updated:** October 2026  

---

## 1. Core Search & Evaluation Criteria

* **Property Type:** Single-Detached Homes (Fee-Simple Title)
* **Maximum Purchase Price:** Under $1,000,000 CAD
* **Garage Specifications:** Double Attached or Double Detached Garage
* **School & Transit Accessibility:** Efficient public transit access (Red Line CTrain or direct Express Bus routes) to **William Aberhart High School**.
* **Basement & Layout Preferences:**
  * High priority on **Legal Basement Suites** or layout potential for separate entrance/secondary suites.
  * Strong preference for **Walk-Out Basement** configurations.
  * Consideration for Main Floor Bedroom + Bath configurations.
  * Architectural preferences include East-facing orientations and third-floor/roof terrace potential.
* **Property Status:** Active market listings, quick possession builds, or immediate resale inventory.

---

## 2. Target Websites & Scanning Instructions

To retrieve and maintain the latest verified property results, scan the following official portals, national aggregators, and local brokerage feeds:

### Official Portals & Aggregators
* **REALTOR.ca** — [https://www.realtor.ca](https://www.realtor.ca) *(Official CREA MLS® Feed)*
* **Zolo Calgary** — [https://www.zolo.ca/calgary-real-estate/northwest-calgary](https://www.zolo.ca/calgary-real-estate/northwest-calgary) *(Fast refresh rate / historical price tracking)*
* **Redfin Canada** — [https://www.redfin.ca](https://www.redfin.ca) *(Interactive map UI, transit scores, and walkability metrics)*
* **Zillow Canada** — [https://www.zillow.com/calgary-ab/](https://www.zillow.com/calgary-ab/) *(Aerial views & neighborhood layout views)*

### Local Calgary Brokerage Websites
* **Calgary House Finder** — [https://www.calgaryhousefinder.ca](https://www.calgaryhousefinder.ca) *(Direct NW quadrant and community breakdown)*
* **Justin Havre & Associates / eXp Realty** — [https://www.justinhavre.com](https://www.justinhavre.com) *(Community lifestyle filters & quick possession updates)*
* **Real-Estate.ca (Calgary)** — [https://www.real-estate.ca/calgary-listings/](https://www.real-estate.ca/calgary-listings/) *(Categorization by quadrant, school zone, and basement configuration)*
* **CIR Realty** — [https://www.cirrealty.ca](https://www.cirrealty.ca) *(Independent Alberta brokerage direct feed)*
* **RE/MAX Real Estate (Central / Mountain View / Professionals)** — [https://www.remax.ca/ab/calgary-real-estate](https://www.remax.ca/ab/calgary-real-estate) *(Regional listing portal)*
* **Calgary Listings** — [https://www.calgarylistings.com](https://www.calgarylistings.com) *(New listings tracking within last 24h/7 days)*

### Scanning Protocol Guidelines
1. Filter listings exclusively to **Single-Family Detached** in **NW Calgary** under **$1,000,000 CAD**.
2. Verify that each property has a double garage (attached or detached) and assess proximity/transit connections to William Aberhart High School (e.g., Red Line CTrain via Banff Trail, Crowfoot, or Tuscany stations, or direct express routes).
3. Validate each listing against direct CREB® MLS® numbers across target brokerage endpoints. Exclude off-market, pending, or sold listings.
4. Synchronize output schema with `index.html` table updates.

---

## 3. Active Qualified Listings Tracker

| MLS® # | Community | Address | Price | Beds / Baths | Sq. Ft. | Key Architectural & Layout Highlights | Aberhart High Commute / Transit | Listing Source URL |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **A2337818** | Hawkwood | 153 Hawkdale Circle NW | $829,900 | 5 Bed / 4 Bath | 2,117 sq ft | • **2-Storey Walkout Basement**<br>• Poly-B replaced; basement kitchen entry potential<br>• Double attached garage; mountain views | Route 76 / Express Bus connect to Crowfoot CTrain | [Zolo Listing Link](https://www.zolo.ca/calgary-real-estate/153-hawkdale-circle-north-west) |
| **A2335522** | Tuscany | 65 Tuscarora Place NW | $679,900 | 3 Bed / 4 Bath | 1,435 sq ft | • **Full Walkout Basement**<br>• Separate entry with wet bar; cul-de-sac location<br>• Double attached garage with mountain views | Direct CTrain from Tuscany Station to Banff Trail Station | [Calgary Homes Link](https://calgaryhomes.ca/listing/a2335522-65-tuscarora-place-northwest-calgary-alberta-t3l2g1/) |
| **A2344733** | Sherwood | 112 Sherwood Crescent NW | $899,900 | 4 Bed / 4 Bath | 2,435 sq ft | • **Walkout Basement**<br>• East-facing front exposure; 18ft entry foyer<br>• Backs onto green space; double attached garage | Express Bus 129/82 to Red Line CTrain connection | [Calgary Homes Link](https://calgaryhomes.ca/listing/a2344733-112-sherwood-crescent-northwest-calgary-alberta-t3r-0g2/) |
| **A2349480** | Citadel | 118 Citadel Crest Park NW | $719,900 | 4 Bed / 4 Bath | 1,948 sq ft | • Double attached garage<br>• Vaulted ceilings; fully finished basement<br>• Poly-B fully replaced | Express Bus 138 connecting to Crowfoot CTrain Station | [Calgary House Finder Link](https://www.calgaryhousefinder.ca/listing/a2349480-118-citadel-crest-park-nw-calgary-alberta-t3g-4k5/) |
| **A2168910** | Arbour Lake | 11 Arbour Summit Close NW | $674,900 | 5 Bed / 4 Bath | 1,803 sq ft | • Full lake access privileges<br>• 5 Bedrooms with finished basement layout<br>• Double attached garage | Direct walk or feeder bus to Crowfoot CTrain Station | [Calgary House Finder Link](https://www.calgaryhousefinder.ca/listing/a2168910-11-arbour-summit-close-nw-calgary-alberta-t3g-3w1/) |

---

## 4. Data Integration & Source Guidelines

* **Direct MLS® Reference Enforcement:** Generated/mock MLS numbers are prohibited. All entries must map directly to verifiable CREB® MLS® numbers and active public listing endpoints (`realtor.ca`, `zolo.ca`, `calgaryhousefinder.ca`, `calgaryhomes.ca`).
* **Display Application Structure:** `index.html` maintains synchronization with this data specification, displaying verified active listings with property specs, transit connection details, and direct MLS links.
