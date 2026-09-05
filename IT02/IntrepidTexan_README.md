# IntrepidTexan.com Website Structure

## Current Website Structure

The live IntrepidTexan.com website now uses a clean top-level structure:

```text
/
    index.html

    about/
        index.html

    hikes/
        index.html
        Camino01.html
        Camino02.html
        Camino03.html
        Camino04.html
        Camino05.html
        Camino06.html
        Camino07.html
        Camino08.html
        Camino09.html

    stories/
        index.html

    travel/
        index.html
        IT_travel_photodata.xlsx
        photos/

    IT02/
        images/
        IT_A.html
        IT_B.html
        IT_C.html
        IT_D.html
```

The public-facing URLs are:

```text
https://intrepidtexan.com/
https://intrepidtexan.com/travel/
https://intrepidtexan.com/hikes/
https://intrepidtexan.com/stories/
https://intrepidtexan.com/about/
```

Visitors should normally use these clean URLs and should not need to navigate through `/IT02/`.

---

## Main Sections

The original website used the following naming convention:

```text
IT_A = TRAVEL
IT_B = HIKES
IT_C = STORIES
IT_D = ABOUT THE AUTHOR
```

Those old names are retained under `/IT02/` primarily for compatibility with old bookmarks, links, and earlier versions of the site.

The current live sections are:

```text
IT_A -> /travel/
IT_B -> /hikes/
IT_C -> /stories/
IT_D -> /about/
```

The files under `/IT02/` can redirect old URLs to the newer top-level sections.

---

## Homepage

The main homepage is now:

```text
/index.html
```

This means anyone entering:

```text
https://intrepidtexan.com/
```

goes directly to the main homepage.

The homepage links to:

- Travels
- Hikes
- Stories
- About the Author

---

## Travel

The live travel section is:

```text
/travel/
```

Main files:

```text
travel/
    index.html
    IT_travel_photodata.xlsx
    photos/
```

The travel map uses:

- Leaflet
- OpenStreetMap
- SheetJS
- `IT_travel_photodata.xlsx`
- Photos stored in `travel/photos/`

Travel-map locations are maintained in the Excel workbook rather than being hard-coded into the HTML.

The `current` worksheet is used for live map locations.

The `future` worksheet is reserved for planned or unfinished locations.

The workbook uses fixed column positions:

```text
Column A = Latitude
Column B = Longitude
Column C = Country
Column D = Location / Description
Column E = Filename
```

Column headings are not required.

---

## Hikes

The live hiking section is:

```text
/hikes/
```

Current Camino pages:

```text
Camino01.html
Camino02.html
Camino03.html
Camino04.html
Camino05.html
Camino06.html
Camino07.html
Camino08.html
Camino09.html
```

These pages retrieve their hike photos from folders under:

```text
/IT02/images/
```

The older `IT_B.html` page can redirect to:

```text
/hikes/
```

Future placeholder pages Camino10, Camino11, and Camino12 were not carried into the new `/hikes/` structure.

---

## Stories

The live stories section is:

```text
/stories/
```

The old `IT_C.html` page can redirect to:

```text
/stories/
```

---

## About the Author

The live About page is:

```text
/about/
```

The old `IT_D.html` page can redirect to:

```text
/about/
```

---

## IT02

`IT02` represents an earlier major iteration of the Intrepid Texan website.

It is intentionally retained rather than renamed because:

- old links may still point there
- some images are still stored there
- it preserves the earlier website structure
- changing the folder name would require updating many existing paths

A future major redesign could use another version folder such as:

```text
/IT03/
```

if desired.

---

## Images

Older website and Camino images are stored under:

```text
/IT02/images/
```

This keeps image files organized while allowing the newer top-level website pages to use them.

The travel map uses its own separate photo folder:

```text
/travel/photos/
```

---

## Hosting and Domain

Cloudflare manages the domain registration and DNS for IntrepidTexan.com.

GitHub Pages hosts the website files.

In general:

```text
Cloudflare = domain registration + DNS
GitHub     = website files + hosting
```

Account credentials are intentionally not stored in this README.

---

## Maintenance Philosophy

The current structure separates the public website from the older IT02 structure.

Normal public navigation should use:

```text
/
about/
hikes/
stories/
travel/
```

The `/IT02/` area should mainly be treated as:

- historical website structure
- compatibility redirects
- shared image storage

This keeps the public URLs simple while preserving older links and files.
