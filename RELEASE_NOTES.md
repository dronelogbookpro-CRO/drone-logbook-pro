# Drone Logbook App - Release Notes

## Latest - Version 1.2.0
Date: 2026-04-14
Release: Rules Module Autofill + Smart Upsert

### Highlights
- New dropdown selector for existing countries in Rules module.
- Automatic form population (autofill) when selecting a country.
- Smart upsert backend logic: Update existing rules or add new ones.
- Dynamic button label change based on country state.
- Improved country rules lookup experience with datalist filtering.

#### What Is New
- Rules input now features autocomplete dropdown with all available countries.
- Selecting a country from dropdown automatically fills all fields with existing rules data.
- Button text dynamically changes:
  - "SPREMI U BAZU" (Save to DB) for new countries
  - "SPREMI IZMJENE" (Save Changes) for existing countries
- Backend smart save logic prevents duplicates by comparing case-insensitive country names.
- Form resets properly after successful submission with button state restoration.

#### Data And Compatibility
- Rules module now supports true edit workflow (update instead of duplicate).
- Existing rules in Google Sheet remain compatible with new lookup logic.

#### Notes
- This release improves the Rules management workflow, making it easier to add new rules or update existing ones without manual tracking.

---

Date: 2026-04-14
Version: 1.1.0
Release: Map Picker + Inline Edit Upgrade

## Highlights
- New map-based location picker in New Flight and Log edit.
- Added Map/Satellite switch with improved satellite coverage.
- Added My Location button for quick GPS centering.
- Added automatic place name lookup from coordinates.
- Added flight radius slider in New Flight and Log edit.

## What Is New
- New Flight now supports selecting location directly on an interactive map.
- Location can be set by click or by dragging marker.
- Reverse geocoding now appends place name after coordinates.
- Flight radius is now part of the flight record:
  - default: 500 m
  - min: 100 m
  - max: 2000 m
  - step: 50 m
- Log table now shows Radius as a dedicated column.
- Log inline edit now supports radius changes with slider.

## Editing Experience
- Log entries are edited inline (no popup prompts).
- Service entries are edited inline (no popup prompts).
- Added clear Save/Cancel flow for edit mode.

## Stability Improvements
- Improved map initialization and coordinate normalization.
- Reduced parser-related breakage in Google Apps Script HTML context.
- Improved zoom behavior and layer consistency in map picker.

## Data And Compatibility
- Added Radius (m) field to flight storage.
- Existing data remains compatible through automatic sheet migration.

## Notes
- This release focuses on faster data entry, better location precision, and safer edits.
