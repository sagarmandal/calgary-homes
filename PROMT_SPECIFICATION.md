# Northwest Calgary Home Finder — System & Prompt Specification

This document contains the prompt structure, functionality specifications, data requirements, and live link behaviors used to generate and maintain the **NW Calgary Single-Detached Home Showcase** portal (`index.html`).

---

## 1. Primary Generation Prompt

> **Prompt:**  
> "Create a single-page web application (`index.html`) using HTML, CSS, and JavaScript for browsing single-detached homes in Northwest Calgary with direct public transit access to William Aberhart High School, modeled after the split-screen map layout on Realtor.ca.
> 
> **Key Layout & Interface Requirements:**
> 1. **Realtor.ca Split-Screen Portal Layout:**
>    - Create a two-column desktop viewport with a **fixed interactive map pane on the left** and a **scrollable grid of property cards on the right**.
>    - Map pins must be styled as **price-pill tags** (e.g., `$745k`) that highlight and scale on hover.
>    - Sync hover and click interactions between map markers and listing cards.
>
> 2. **Dataset Size & Pagination:**
>    - Generate a dataset of **100 realistic single-detached property listings** across Northwest Calgary communities.
>    - Initial load displays **18 property cards**.
>    - A **"Load More Listings (+9)"** button appends **9 additional properties per click** without page reloads.
>
> 3. **Comprehensive Card Criteria & Contact Display:**
>    - Each property card must explicitly display:
>      - Price, Builder Name, Address, Community, Contact Number (`403-263-0530`)
>      - Facing Direction (East, West, North, South Facing)
>      - Year Built / Possession & Open House Hours
>      - Garage Type, Main Floor Bed/Bath
>      - Feature Flags: Walk-Out Basement, Legal Suite, Open to Below, Roof Terrace
>      - Commute & Transit Times to **William Aberhart High School** and **Downtown Calgary**
>
> 4. **Interactive Filters & Facing Dropdown:**
>    - Dropdown filters for **Community**, **Facing Direction (All, East, West, North, South)**, **Minimum Year Built**, and **Sorting Options** (Price, Commute to Aberhart, Year Built).
>    - Feature Checkboxes for Walk-Out, Legal Suite, Open to Below, and Roof Terrace.
>
> 5. **Working Live Search Action Links (`target="_blank" rel="noopener noreferrer"`):**
>    - Cards feature links targeting active Calgary NW search queries:
>      - Realtor.ca: `https://www.realtor.ca/ab/calgary/${community-slug}/real-estate`
>      - RE/MAX: `https://www.remax.ca/ab/calgary-real-estate?query=${address}`"

---

## 2. Technical Stack & Data Schema

| Component | Technology | Purpose |
| :--- | :--- | :--- |
| **Frontend Framework** | Vanilla HTML5 / CSS3 / ES6 JavaScript | Standalone single-file application |
| **Interactive Map** | Leaflet.js v1.9.4 + OpenStreetMap | GIS rendering with price-pill markers |

```javascript
{
  id: "A2348001",
  address: "10 Ambleton Way NW",
  community: "Ambleton",
  priceNumeric: 745000,
  price: "$745,000",
  priceShort: "$745k",
  yearBuilt: 2026,
  facing: "East",                      // Directional orientation flag for dropdown filter
  garage: "Double Attached",
  mainBedBath: "Yes (1 Bed + Full Bath)",
  suiteStatus: "Legal Basement Suite",
  hasLegalSuite: true,
  openHouse: "Sat & Sun 1:00 PM - 4:00 PM",
  distAberhartMin: 20,
  distAberhart: "20 mins (Express Bus/Car)",
  distDowntown: "30 mins (CTrain/Drive)",
  builder: "Broadview Homes",
  walkout: "Yes",
  openToBelow: "Yes",
  terrace: "No",
  spacious: "2,010 sq ft",
  lat: 51.1710,
  lng: -114.1350,
  realtorUrl: "[https://www.realtor.ca/ab/calgary/ambleton/real-estate](https://www.realtor.ca/ab/calgary/ambleton/real-estate)",
  remaxUrl: "[https://www.remax.ca/ab/calgary-real-estate?query=10%20Ambleton%20Way%20NW%2C%20Calgary](https://www.remax.ca/ab/calgary-real-estate?query=10%20Ambleton%20Way%20NW%2C%20Calgary)",
  contactPhone: "403-263-0530"        // Contact showing number
}
