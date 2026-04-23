# Bug Reports

---

## BUG-001
- **Title:** API accepts duplicate tracks in playlist
- **Steps to reproduce:** Send PATCH to /objects/{id} with two identical trackId values in the tracks array
- **Expected:** 400 Bad Request — duplicate tracks should be rejected
- **Actual:** 200 OK — both identical tracks accepted and saved
- **Severity:** High
- **Impact:** A user would see the same song twice in their playlist, creating a broken experience and data integrity issues

---

## BUG-002
- **Title:** API accepts negative trackCount value
- **Steps to reproduce:** Send PATCH to /objects/{id} with trackCount set to -5
- **Expected:** 400 Bad Request — trackCount must be 0 or greater
- **Actual:** 200 OK — negative value accepted and saved
- **Severity:** Medium
- **Impact:** A negative track count makes no logical sense and would cause display errors in the UI — showing "This playlist has -5 songs"

---

## BUG-003
- **Title:** API accepts track object with empty required fields
- **Steps to reproduce:** Send PATCH to /objects/{id} with a track containing only trackId — no title, artist or duration fields included
- **Expected:** 400 Bad Request — title, artist and duration are required fields and cannot be empty
- **Actual:** 200 OK — incomplete track object accepted and saved with only trackId present
- **Severity:** High
- **Impact:** A track with no title or artist cannot be displayed to the user — would appear as a blank entry in the playlist

---

## BUG-004
- **Title:** API accepts empty string as playlist name
- **Steps to reproduce:** Send PATCH to /objects/{id} with name field set to empty string ""
- **Expected:** 400 Bad Request — playlist name is a required field and cannot be empty
- **Actual:** 200 OK — empty name accepted and saved
- **Severity:** Medium
- **Impact:** A playlist with no name cannot be identified by the user — would display as blank in the music app interface making it impossible to distinguish between playlists

---

## BUG-005
- **Title:** API accepts wrong data types for numeric fields
- **Steps to reproduce:** Send PATCH to /objects/{id} with trackCount as string "five", trackId as string "abc", duration as string "four minutes"
- **Expected:** 400 Bad Request — trackCount, trackId and duration must be numeric values
- **Actual:** 200 OK — string values accepted for all numeric fields
- **Severity:** High
- **Impact:** Wrong data types break any feature depending on these fields — total playlist duration calculation, track lookup by id, and track count display would all fail in a real music app

---

## Summary

| Bug ID | Title | Severity | Status |
|--------|-------|----------|--------|
| BUG-001 | API accepts duplicate tracks | High | Open |
| BUG-002 | API accepts negative trackCount | Medium | Open |
| BUG-003 | API accepts empty track fields | High | Open |
| BUG-004 | API accepts empty playlist name | Medium | Open |
| BUG-005 | API accepts wrong data types | High | Open |
###this was done with the restfull api, thats way i used patch and the return are all 200 ok 
