# Northwest Calgary Single-Detached Property Search Specification

**Document Version:** 2.2  
**Target Market:** Northwest Calgary (NW), Alberta, Canada  
**Target School Catchment:** William Aberhart High School (Transit & Driving Corridor)  
**Last Updated:** October 2026  

---

## 1. Core Search & Evaluation Criteria

* **Property Type:** Single-Detached Homes (Fee-Simple Title)
* **Maximum Purchase Price:** Under $1,000,000 CAD
* **Garage Specifications:** Double Attached or Double Detached Garage
* **School & Transit Accessibility:** Direct access via Red Line CTrain (Banff Trail / Crowfoot / Tuscany stations) or direct Express Bus routes (Routes 76, 129, 138) to **William Aberhart High School**.
* **Basement & Layout Preferences:**
  * High priority on **Legal or Secondary Basement Suites** (separate entry, wet bar/kitchen setup).
  * Strong preference for **Walk-Out Basement** configurations.
  * East-facing front orientation or green space backings preferred.
* **Property Status:** Verified active resale inventory from CREB® MLS® database.

---

## 2. Target Websites & Scanning Sources

The application data must be continuously synchronized by scanning official MLS® feeds and authorized local brokerage platforms:

### Official Aggregators & National Platforms
* **REALTOR.ca** — [https://www.realtor.ca](https://www.realtor.ca) *(Official CREA National Portal)*
* **Zolo Calgary** — [https://www.zolo.ca/calgary-real-estate/northwest-calgary](https://www.zolo.ca/calgary-real-estate/northwest-calgary) *(Fast 15-min update cycle)*
* **Redfin Canada** — [https://www.redfin.ca](https://www.redfin.ca) *(Interactive map UI, transit scores, and walkability metrics)*
* **Zillow Canada** — [https://www.zillow.com/calgary-ab/](https://www.zillow.com/calgary-ab/) *(Aerial and satellite views)*

### Local Calgary Brokerage Direct Feeds
* **Calgary House Finder** — [https://www.calgaryhousefinder.ca](https://www.calgaryhousefinder.ca) *(NW community breakdowns)*
* **Justin Havre & Associates / eXp Realty** — [https://www.justinhavre.com](https://www.justinhavre.com) *(Community lifestyle filters)*
* **Real-Estate.ca (Calgary)** — [https://www.real-estate.ca/calgary-listings/](https://www.real-estate.ca/calgary-listings/) *(Basement suite configurations)*
* **CIR Realty** — [https://www.cirrealty.ca](https://www.cirrealty.ca) *(Independent Alberta brokerage feed)*
* **RE/MAX Real Estate** — [https://www.remax.ca/ab/calgary-real-estate](https://www.remax.ca/ab/calgary-real-estate) *(Regional listing feed)*
* **Calgary Listings** — [https://www.calgarylistings.com](https://www.calgarylistings.com) *(Live 24h market activity)*

---

## 3. Web Application Requirements (`index.html`)

The single-page Web Application must include:
1. **Interactive Google Map:** Leaflet/Google Maps API map container initialized over NW Calgary (centered around `51.1000, -114.1600`), plotting pinned markers for every active listing, plus a special anchor marker for **William Aberhart High School**.
2. **Interactive Markers & Cards:** Clicking a map pin opens a popup card showing address, price, specs, walkout/suite badge, and direct URL to the Realtor site.
3. **Filter Controls:**
   * **Community Filter:** All NW, Hawkwood, Tuscany, Citadel, Sherwood, Arbour Lake.
   * **Max Price Slider / Select:** Up to $1,000,000 CAD.
   * **Basement Type:** All, Walkout Only, Suite / Separate Entry.
4. **Data Synchronization:** Map pins and table records must remain dynamically synced with filter changes.

---

## 4. Scanned Active Property Dataset

| MLS® # | Community | Address | Price | Beds/Baths | Sq. Ft. | Coordinates (Lat, Lng) | Feature Highlights | Transit Corridor to Aberhart | Direct Realtor Link |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **A2337818** | Hawkwood | 153 Hawkdale Circle NW | $829,900 | 5 Bed / 4 Bath | 2,117 sq ft | 51.1214, -114.1983 | Walkout basement, newly finished suite entry, 2nd kitchen | Route 76 bus to Crowfoot CTrain | [View Listing](https://www.zolo.ca/calgary-real-estate/153-hawkdale-circle-north-west) |
| **A2348026** | Hawkwood | 117 Hawkbury Close NW | $874,900 | 5 Bed / 4 Bath | 2,383 sq ft | 51.1235, -114.1950 | 2-storey detached, updated kitchen, high ceilings, mountain views | Route 76 express bus connect | [View Listing](https://www.zolo.ca/calgary-real-estate/117-hawkbury-close-north-west) |
| **A2335522** | Tuscany | 65 Tuscarora Place NW | $679,900 | 3 Bed / 4 Bath | 1,435 sq ft | 51.1278, -114.2385 | Full walkout basement, separate entrance, wet bar, mountain view | Tuscany CTrain direct to Banff Trail | [View Listing](https://calgaryhomes.ca/listing/a2335522-65-tuscarora-place-northwest-calgary-alberta-t3l2g1/) |
| **A2349480** | Citadel | 118 Citadel Crest Park NW | $719,900 | 4 Bed / 4 Bath | 1,948 sq ft | 51.1402, -114.1882 | Vaulted ceilings, finished basement, Poly-B replaced in 2026 | Bus 138 connect to Crowfoot CTrain | [View Listing](https://www.calgaryhousefinder.ca/listing/a2349480-118-citadel-crest-park-nw-calgary-alberta-t3g-4k5/) |
| **A2168910** | Arbour Lake | 11 Arbour Summit Close NW | $674,900 | 5 Bed / 4 Bath | 1,803 sq ft | 51.1305, -114.2051 | Lake privileges, 5 full beds, finished basement layout | Walk / feeder bus to Crowfoot CTrain | [View Listing](https://www.calgaryhousefinder.ca/listing/a2168910-11-arbour-summit-close-nw-calgary-alberta-t3g-3w1/) |
| **A2344733** | Sherwood | 112 Sherwood Crescent NW | $899,900 | 4 Bed / 4 Bath | 2,435 sq ft | 51.1610, -114.1480 | Full walkout basement, 18ft entry foyer, backs onto green space | Bus 129 / 82 connect to Red Line | [View Listing](https://calgaryhomes.ca/listing/a2344733-112-sherwood-crescent-northwest-calgary-alberta-t3r-0g2/) |
