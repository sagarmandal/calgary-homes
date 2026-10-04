# Northwest Calgary Home Finder — System & Prompt Specification

This document contains the prompt structure, functionality specifications, and data requirements used to generate and maintain the **NW Calgary Single-Detached Home Showcase** portal (`index.html`).

---

## 1. Primary Generation Prompt

> **Prompt:**  
> "Create a single-page web application (`index.html`) using HTML, CSS, and JavaScript for browsing single-detached homes in Northwest Calgary with direct public transit access to William Aberhart High School, modeled after the split-screen map layout on Realtor.ca.
> 
> **Key Layout & Interface Requirements:**
> 1. **Realtor.ca Split-Screen Portal Layout:**
>    - Create a two-column desktop viewport with a **fixed interactive map pane on the left** and a **scrollable grid of property cards on the right**.
>    - Map pins must be styled as **price-pill tags** (e.g., `$745k`) that highlight and scale on hover.
>    - Sync hover and click interactions between map markers and listing cards (hovering a card highlights its corresponding map pin; clicking a pin scrolls to and highlights its card).
>
> 2. **Dataset Size & Pagination:**
>    - Generate a dataset of **100 realistic single-detached property listings** across Northwest Calgary communities.
>    - Initial load displays **18 property cards**.
>    - A **"Load More Listings (+9)"** button at the bottom appends **9 additional properties per click** without page reloads.
>
> 3. **Comprehensive Card Criteria Display:**
>    - Each property card must explicitly display all structural and feature specifications:
>      - Price, Builder Name, Address, Community
>      - Orientation / Facing (e.g., East Facing)
>      - Year Built / Possession
>      - Garage Type (e.g., Double Attached / Detached)
>      - Main Floor Bed/Bath Availability
>      - Legal Basement Suite Status
>      - **Walk-Out Basement** (Yes / No)
>      - **Open to Below** Ceiling Feature (Yes / No)
>      - **3rd Floor Roof Terrace** (Yes / No)
>      - Floor Area Square Footage
>      - Commute & Transit Times to **William Aberhart High School** and **Downtown Calgary**
>      - Open House Hours & Move-in Status
>
> 4. **Interactive Filters & Feature Checkboxes:**
>    - Dropdown filters for **Community**, **Minimum Year Built** (Any Year, 2026, 2025+, 2024+, 2023+), and **Sorting Options** (Price Low/High, Commute to Aberhart, Year Built).
>    - **"Must Have / Feature" Checkboxes** allowing users to instantly filter listings by:
>      - Walk-Out Basement
>      - Open to Below
>      - 3rd Floor Roof Terrace
>      - Legal Basement Suite
>
> 5. **Real-time Page Refresh & Fixed MLS Links:**
>    - A **"🔄 Refresh Live"** header button executing a live cache-bypassing page refresh (`location.reload(true)`).
>    - Direct redirection to official Realtor.ca listing lookup engines via formatted URLs (`https://www.realtor.ca/real-estate-search?m=${item.id}`)."

---

## 2. Technical Stack & Architecture

| Component | Technology / Library | Purpose |
| :--- | :--- | :--- |
| **Frontend Framework** | Vanilla HTML5 / CSS3 / JavaScript (ES6+) | Standalone zero-dependency single-file application (`index.html`) |
| **Interactive Map** | [Leaflet.js v1.9.4](https://leafletjs.com/) + OpenStreetMap | Interactive GIS map render with custom price pill markers |
| **Layout & Styling** | CSS Grid & Flexbox Viewport Split | Fixed left map / scrollable right grid layout |
| **Data Engine** | In-Memory JS Filtering & Array Operations | Client-side search, multi-criteria filtering, and pagination |

---

## 3. Data Schema Specifications

Every listing object in the `propertiesData` array matches the following schema:

```javascript
{
  id: "A2348001",                      // MLS Listing ID
  address: "10 Ambleton Way NW",       // Full Street Address
  community: "Ambleton",               // NW Calgary Neighborhood
  priceNumeric: 745000,                // Raw Integer Price (for sorting)
  price: "$745,000",                   // Formatted Price
  priceShort: "$745k",                 // Map Pill Tag Text
  yearBuilt: 2026,                     // Year Built / Possession
  facing: "East",                      // Directional Orientation
  garage: "Double Attached",           // Garage Configuration
  mainBedBath: "Yes (1 Bed + Full Bath)", // Main Floor Bed/Bath Availability
  suiteStatus: "Legal Basement Suite", // Legal Suite Description
  hasLegalSuite: true,                 // Boolean Filter Flag
  status: "Quick Possession",          // Possession Status
  openHouse: "Sat & Sun 1:00 PM - 4:00 PM", // Open House Hours
  distAberhartMin: 20,                 // Transit Commute Minutes (for sorting)
  distAberhart: "13 km (20 min drive / Bus Express)",
  distDowntown: "18 km (23 min drive)",
  builder: "Broadview Homes",          // Builder Reference
  walkout: "Yes",                      // Feature Flag ("Yes" / "No")
  openToBelow: "Yes",                  // Feature Flag ("Yes" / "No")
  terrace: "No",                       // Feature Flag ("Yes" / "No")
  spacious: "2,010 sq ft",             // Square Footage
  lat: 51.1710,                        // Latitude Coordinate
  lng: -114.1350                       // Longitude Coordinate
}
