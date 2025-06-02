# TravelTip

**TravelTip** is a web app for managing and exploring favorite locations, with map integration, filtering, sorting, and theming.

---

## Features

- **Location Management (CRUDL):**
  - **Create:** Add a new location by clicking on the map, entering a name and rating.
  - **Read:** View a list of locations with details and statistics.
  - **Update:** Edit location name and rating.
  - **Delete:** Remove locations from your list.
  - **List:** Filter and sort locations by name, rating, or creation time.

- **Map Integration:**
  - Search for addresses and pan the map to them.
  - Pan to your current geolocation.
  - Markers for selected locations.
  - Copy or share location links.

- **UI & Theming:**
  - Responsive layout for mobile and desktop.
  - Multiple color themes (Default, Aqua, Green).
  - Custom fonts: Fredoka and Rubik Doodle Shadow.
  - Stylish, accessible forms and controls.

- **Statistics:**
  - Pie chart showing locations by last update.
  - Legend for easy interpretation.

---

## Usage

### Main UI Elements

- **Header:**  
  - App title, search bar, and theme selector.
- **Main Content:**  
  - **Map:** Interactive map with markers.
  - **Locations Panel:**  
    - Selected location details.
    - Filter and sort controls.
    - Locations list.
    - Statistics section.

### Example Location Object

```js
{
  id: 'GEouN',
  name: 'Dahab, Egypt',
  rate: 5,
  geo: {
    address: 'Dahab, South Sinai, Egypt',
    lat: 28.5096676,
    lng: 34.5165187,
    zoom: 11
  },
  createdAt: 1706562160181,
  updatedAt: 1706562160181
}
```

---

## Project Structure

```
css/
  base/         # Base styles (reset, layout, helpers)
  cmps/         # Component styles (header, locations, map, theme selector, etc.)
  setup/        # Variables, media queries, typography
  assets/fonts/ # Custom fonts
js/
  services/     # Utility, map, and location services
  app.controller.js # Main app logic and DOM interaction
index.html      # Main HTML file
```

---

## Services

```js
export const locService = {
  query,
  getById,
  remove,
  save,
  setFilterBy,
  setSortBy,
  setUserPos,
  getLocCountByRateMap,
  getLocCountByLastUpdate
}

export const mapService = {
  initMap,
  getUserPosition,
  setMarker,
  panTo,
  lookupAddressGeo,
  addClickListener
}
```

---

## Controller

All main actions are exposed on the global `app` object for easy DOM integration:

```js
window.app = {
  onRemoveLoc,
  onUpdateLoc,
  onSelectLoc,
  onPanToUserPos,
  onSearchAddress,
  onCopyLoc,
  onShareLoc,
  onSetSortBy,
  onSetFilterBy,
  onChangeTheme
}
```

---

## Theming

- Switch between themes using the theme selector in the header.
- Themes are defined in `css/setup/vars.css` and applied via body classes.

---

## Fonts

- **Fredoka** and **Rubik Doodle Shadow** are included for a modern, playful look.

---

## Getting Started

1. Clone the repository.
2. Open `index.html` in your browser.
3. Use the app to add, view, and manage locations!

---

## License

Fonts are licensed under the [SIL Open Font License](https://openfontlicense.org).

---

*Made with ❤️ for travel lovers!*