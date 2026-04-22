# music-streming-api-qa
##Overview
QA testing in postman for a music streaming API using itunes and restful apis.
##APIs Used
- **Restful-API.dev** (https://api.restful-api.dev) — playlist and track management
-**iTunes Search API** (https://itunes.apple.com/search) — music search and catalogue data
## Test Coverage

### 1. Search Functionality
- Search by valid artist name
- Search by valid track name
- Search with special characters
- Search with empty string
- Search with nonsense string
- Search with numbers

### 2. Playlist Management
- Create a playlist
- Read a playlist
- Update a playlist name
- Delete a playlist


### 3. Bug Hunt
| Bug ID | Title | Severity |
|--------|-------|----------|
| BUG-001 | API accepts duplicate tracks | High |
| BUG-002 | API accepts negative trackCount | Medium |
| BUG-003 | API accepts track with missing fields | High |
| BUG-004 | API accepts empty playlist name | Medium |
| BUG-005 | API accepts wrong data types for numeric fields | High |

## How to use this collection
1. Download and install Postman (postman.com/downloads)
2. In Postman click **Import**
3. Select the `.json` file from this repository
4. The full collection will appear in your Postman sidebar
5. Run requests in order — Search -> Managing Playlist-> Bug Hunt
