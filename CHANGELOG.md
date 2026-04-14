# Changelog

All notable changes to this project are documented in this file.

## [1.2.0] - 2026-04-14

### Added
- Added datalist element with autocomplete dropdown for country selection in Rules module.
- Added `povuciPravilo()` autofill function that populates all rule fields based on selected country.
- Added global `globalnaPravila` variable to cache rules for frontend lookup.
- Added dynamic datalist population from loaded country rules.
- Added dynamic button label switching based on country existence (new vs. existing).

### Changed
- Changed Rules module input from simple text field to datalist-enabled field with autocomplete.
- Changed form behavior to auto-populate when country is selected from dropdown.
- Changed button label to reflect action type: "SPREMI IZMJENE" for updates, "SPREMI U BAZU" for new entries.
- Changed form reset flow to include button state restoration via `povuciPravilo()`.

### Technical Details
- Frontend files updated:
  - Index.html: Added `list="listaDrzava"` and `onchange="povuciPravilo()"` to c_Drzava input
  - Index.html: Added `<datalist id="listaDrzava"></datalist>` element
  - JS.html: Added `globalnaPravila` global variable initialization
  - JS.html: Added autofill datalist population in `loadRules()` success handler
  - JS.html: Added complete `povuciPravilo()` function for field autofill and button state
  - JS.html: Added `povuciPravilo()` call in `submitCountry()` after form reset
- Backend remains unchanged (already had smart upsert logic in `saveNewCountry()`):
  - Code.js: Existing upsert logic compares case-insensitive country names for updates

### Notes
- Rules module now fully supports edit workflow (true update, not duplicate creation).
- Autofill improves data consistency by preventing manual re-entry of unchanged fields.

## [1.1.0] - 2026-04-14

### Added
- Added map picker modal for flight location selection.
- Added map marker click/drag workflow for precise location input.
- Added My Location action in map picker.
- Added reverse geocoding to append place name to coordinates.
- Added satellite layer and base layer switching.
- Added flight radius slider in New Flight form.
- Added live radius value label in New Flight form.
- Added Radius column in Log table view.
- Added radius slider to Log inline edit mode.
- Added backend Radius (m) persistence in Letovi sheet.

### Changed
- Changed Log editing from prompt-based flow to inline row editing.
- Changed Service editing from prompt-based flow to inline row editing.
- Updated map tile providers to Google street and satellite layers.
- Updated map zoom limits for better stability and usability.
- Updated flight reset flow to restore radius default after save.

### Fixed
- Fixed map parser/runtime issues in Apps Script HTML rendering context.
- Fixed coordinate validation edge cases that could break tile loading.
- Fixed map behavior when switching base layers and zoom levels.
- Fixed compatibility path for older Letovi sheet structure by migrating Radius column.

### Technical Details
- Frontend files updated:
  - Index.html
  - JS.html
  - CSS.html
- Backend files updated:
  - Code.js
- Data model update:
  - Letovi header extended with Radius (m)
  - saveFlight/updateFlight/getRecentFlights now handle radius

## [1.0.0] - Initial release

### Added
- Initial Google Apps Script web app for drone operations:
  - New Flight module
  - Service module
  - Log module
  - Rules module
- Google Sheets backend integration for Letovi, Odrzavanje, and PravilaZemalja.
- Basic flight logging with location, takeoff/landing time, duration, and notes.
- Service entry logging and recent service history.
- Country rules search, display, and admin seed workflow.
- Pilot profile and document links stored in localStorage.
- Offline queue and sync-on-reconnect behavior.
- PWA-ready meta/manifest setup.

### Notes
- Pre-release iterations were not tracked as separate changelog entries.
- This baseline entry is reconstructed from README scope.
