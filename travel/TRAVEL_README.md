# Intrepid Texan Travel Map

## Purpose

This folder contains the files used for the live Intrepid Texan travel photo map at:

```text
https://intrepidtexan.com/travel/
```

The map is designed so that new locations can be added without editing the HTML each time.

Photo information is maintained in an Excel workbook and loaded automatically by the map when the page opens.

---

## Website Structure

The current main website structure is:

```text
/
    index.html
    about/
        index.html
    hikes/
        index.html
        Camino01.html
        Camino02.html
        ...
        Camino09.html
    stories/
        index.html
    travel/
        index.html
        IT_travel_photodata.xlsx
        README.md
        photos/
            *.JPG
```

Legacy files and older website material are maintained separately under:

```text
/IT02/
```

The live travel page itself is:

```text
/travel/index.html
```

---

## Travel Folder Structure

```text
travel/
    index.html
    IT_travel_photodata.xlsx
    README.md
    photos/
        *.JPG
```

---

## Main Files

### index.html

This is the live travel map.

It uses:

- Leaflet for the interactive map
- OpenStreetMap map tiles
- SheetJS to read the Excel workbook
- A custom full-screen photo viewer
- Mouse-wheel zoom on desktop
- Click-and-drag when zoomed
- Pinch zoom and pan on phones/tablets
- Swipe-to-close at normal photo size

The page automatically reads the `current` worksheet from:

```text
IT_travel_photodata.xlsx
```

The `future` worksheet is ignored by the live map.

---

## IT_travel_photodata.xlsx

This workbook is the master database for travel-photo locations.

It contains two worksheets:

### current

Only rows on this sheet are displayed on the live map.

Required column headings:

| Latitude | Longitude | Country | Location | Filename |
|---|---|---|---|---|

Example:

| Latitude | Longitude | Country | Location | Filename |
|---:|---:|---|---|---|
| 34.5692 | 69.2127 | Afghanistan | Kabul airport | afghan1.JPG |

Latitude and longitude should normally be entered to four or five decimal places.

Five decimal places is more than sufficient for this travel-photo map.

### future

This sheet is reserved for future locations and planned additions.

The live website does not read this sheet.

Rows can be developed here and later moved or copied to `current` when ready for publication.

---

## Photo Files

All travel photos used by the map are stored in:

```text
travel/photos/
```

### Required filename standard

All normalized travel-photo files should use the uppercase extension:

```text
.JPG
```

Example:

```text
BlueMosque.Istanbul.TK.JPG
```

Do not use lowercase:

```text
.jpg
```

GitHub Pages is case-sensitive, so the filename entered in the Excel workbook must match the filename in the `photos` folder exactly, including:

- capitalization
- punctuation
- spaces
- spelling
- `.JPG` extension

For example:

```text
Photo.JPG
```

and:

```text
photo.jpg
```

are different filenames to GitHub Pages.

---

## Adding a New Travel Photo

1. Normalize or resize the photo using the standard photo-processing software.
2. Confirm that the resulting filename ends in `.JPG`.
3. Upload the photo to `travel/photos/`.
4. Open `IT_travel_photodata.xlsx`.
5. Add a row to the `current` worksheet containing:
   - Latitude
   - Longitude
   - Country
   - Location description
   - Exact photo filename
6. Save the workbook.
7. Upload or replace `travel/IT_travel_photodata.xlsx`.
8. Wait for GitHub Pages to publish the updated files.
9. Test the marker and photo on the live map.

No change to `travel/index.html` should normally be required when adding a location.

---

## Moving a Future Location to the Live Map

When a location on the `future` worksheet is ready:

1. Copy or move the completed row to `current`.
2. Make sure the corresponding `.JPG` file is in `travel/photos/`.
3. Save and re-upload `IT_travel_photodata.xlsx`.

The location will then appear automatically on the live map.

---

## Troubleshooting Broken Photos

If a map marker appears but the photo is broken, first compare:

```text
IT_travel_photodata.xlsx -> Filename
```

with:

```text
travel/photos/ -> actual filename
```

The two must match character-for-character.

The most common error is `.jpg` versus `.JPG`.

Also check for:

- spelling differences
- missing punctuation
- extra spaces
- incorrect folder location
- photo not yet uploaded
- GitHub Pages still publishing the latest commit

---

## Map Data Notes

Some coordinates are approximate when the exact photo location is unknown.

Approximate locations should be identified in the Location field with wording such as:

```text
(approx.)
```

When better location information becomes available, update the coordinates in the Excel workbook rather than modifying the HTML.

---

## Maintenance Philosophy

The Excel workbook is the authoritative travel-location database.

The normal maintenance workflow should be:

```text
Photo          -> travel/photos/
Location data  -> IT_travel_photodata.xlsx
HTML           -> normally unchanged
```

This keeps the travel map easy to maintain as the number of photos and locations grows.

---

## Live Page

The public travel map is:

```text
https://intrepidtexan.com/travel/
```

Visitors should normally reach the travel section through the main homepage:

```text
https://intrepidtexan.com/
```

They should not need to navigate through the older `/IT02/` website structure.
