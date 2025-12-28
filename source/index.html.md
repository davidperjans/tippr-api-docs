---
title: Tippr API v1
language_tabs:
  - shell: Shell
  - http: HTTP
  - javascript: JavaScript
  - ruby: Ruby
  - python: Python
  - php: PHP
  - java: Java
  - go: Go
toc_footers: []
includes: []
search: true
highlight_theme: darkula
headingLevel: 2

---

<!-- Generator: Widdershins v4.0.1 -->

<h1 id="tippr-api">Tippr API v1</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

Football prediction league API. Authenticate with Supabase JWT token.

# Authentication

- HTTP Authentication, scheme: bearer Paste Supabase access_token

<h1 id="tippr-api-adminapifootball">AdminApiFootball</h1>

## post__api_admin_apifootball_tournaments_{tournamentId}_baseline

> Code samples

```shell
# You can also use wget
curl -X POST /api/admin/apifootball/tournaments/{tournamentId}/baseline \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST /api/admin/apifootball/tournaments/{tournamentId}/baseline HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/admin/apifootball/tournaments/{tournamentId}/baseline',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post '/api/admin/apifootball/tournaments/{tournamentId}/baseline',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('/api/admin/apifootball/tournaments/{tournamentId}/baseline', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/api/admin/apifootball/tournaments/{tournamentId}/baseline', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/admin/apifootball/tournaments/{tournamentId}/baseline");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/api/admin/apifootball/tournaments/{tournamentId}/baseline", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api/admin/apifootball/tournaments/{tournamentId}/baseline`

*Sync tournament baseline data (teams, venues, fixtures) from API-FOOTBALL.
This is the initial sync that maps external data to existing teams/matches.
Use createMissingTeams=true to auto-create teams that don't exist in the database.*

<h3 id="post__api_admin_apifootball_tournaments_{tournamentid}_baseline-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|tournamentId|path|string(uuid)|true|none|
|force|query|boolean|false|none|
|createMissingTeams|query|boolean|false|none|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": {
    "teamsUpdated": 0,
    "teamsCreated": 0,
    "teamsUnmapped": 0,
    "venuesUpserted": 0,
    "matchesUpserted": 0,
    "matchesLinked": 0,
    "matchesSkipped": 0,
    "unmappedTeams": [
      "string"
    ],
    "warnings": [
      "string"
    ],
    "syncedAt": "2019-08-24T14:15:22Z"
  }
}
```

<h3 id="post__api_admin_apifootball_tournaments_{tournamentid}_baseline-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[SyncTournamentBaselineResultResult](#schemasynctournamentbaselineresultresult)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

## post__api_admin_apifootball_tournaments_{tournamentId}_results

> Code samples

```shell
# You can also use wget
curl -X POST /api/admin/apifootball/tournaments/{tournamentId}/results \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST /api/admin/apifootball/tournaments/{tournamentId}/results HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/admin/apifootball/tournaments/{tournamentId}/results',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post '/api/admin/apifootball/tournaments/{tournamentId}/results',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('/api/admin/apifootball/tournaments/{tournamentId}/results', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/api/admin/apifootball/tournaments/{tournamentId}/results', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/admin/apifootball/tournaments/{tournamentId}/results");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/api/admin/apifootball/tournaments/{tournamentId}/results", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api/admin/apifootball/tournaments/{tournamentId}/results`

*Sync tournament match results from API-FOOTBALL.
Updates scores and statuses for matches that are live or recently finished.*

<h3 id="post__api_admin_apifootball_tournaments_{tournamentid}_results-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|tournamentId|path|string(uuid)|true|none|
|force|query|boolean|false|none|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": {
    "matchesUpdated": 0,
    "matchesUnchanged": 0,
    "matchesNotFound": 0,
    "apiCallsMade": 0,
    "updates": [
      {
        "matchId": "685569fd-95e6-4335-9aa5-fdd22382bd9e",
        "homeTeam": "string",
        "awayTeam": "string",
        "oldStatus": "string",
        "newStatus": "string",
        "oldScore": "string",
        "newScore": "string"
      }
    ],
    "warnings": [
      "string"
    ],
    "syncedAt": "2019-08-24T14:15:22Z"
  }
}
```

<h3 id="post__api_admin_apifootball_tournaments_{tournamentid}_results-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[SyncTournamentResultsResultResult](#schemasynctournamentresultsresultresult)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

## post__api_admin_apifootball_matches_{matchId}_lineups

> Code samples

```shell
# You can also use wget
curl -X POST /api/admin/apifootball/matches/{matchId}/lineups \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST /api/admin/apifootball/matches/{matchId}/lineups HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/admin/apifootball/matches/{matchId}/lineups',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post '/api/admin/apifootball/matches/{matchId}/lineups',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('/api/admin/apifootball/matches/{matchId}/lineups', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/api/admin/apifootball/matches/{matchId}/lineups', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/admin/apifootball/matches/{matchId}/lineups");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/api/admin/apifootball/matches/{matchId}/lineups", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api/admin/apifootball/matches/{matchId}/lineups`

*Sync match lineups from API-FOOTBALL.
Lineups are typically available ~60 minutes before kickoff.*

<h3 id="post__api_admin_apifootball_matches_{matchid}_lineups-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|matchId|path|string(uuid)|true|none|
|force|query|boolean|false|none|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": {
    "success": true,
    "lineupsAvailable": true,
    "teamsWithLineups": 0,
    "fetchedAt": "2019-08-24T14:15:22Z",
    "message": "string"
  }
}
```

<h3 id="post__api_admin_apifootball_matches_{matchid}_lineups-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[SyncMatchLineupsResultResult](#schemasyncmatchlineupsresultresult)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

## get__api_admin_apifootball_leagues_validate

> Code samples

```shell
# You can also use wget
curl -X GET /api/admin/apifootball/leagues/validate \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET /api/admin/apifootball/leagues/validate HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/admin/apifootball/leagues/validate',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get '/api/admin/apifootball/leagues/validate',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('/api/admin/apifootball/leagues/validate', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/api/admin/apifootball/leagues/validate', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/admin/apifootball/leagues/validate");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/admin/apifootball/leagues/validate", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/admin/apifootball/leagues/validate`

*Validate that a league/season combination exists in API-FOOTBALL
and check what data coverage is available.*

<h3 id="get__api_admin_apifootball_leagues_validate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|query|integer(int32)|false|none|
|season|query|integer(int32)|false|none|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": {
    "isValid": true,
    "leagueName": "string",
    "leagueType": "string",
    "country": "string",
    "hasLineupsSupport": true,
    "hasEventsSupport": true,
    "hasStatisticsSupport": true,
    "errorMessage": "string"
  }
}
```

<h3 id="get__api_admin_apifootball_leagues_validate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[ValidateLeagueResultResult](#schemavalidateleagueresultresult)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

## post__api_admin_apifootball_tournaments_{tournamentId}_merge-teams

> Code samples

```shell
# You can also use wget
curl -X POST /api/admin/apifootball/tournaments/{tournamentId}/merge-teams \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST /api/admin/apifootball/tournaments/{tournamentId}/merge-teams HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/admin/apifootball/tournaments/{tournamentId}/merge-teams',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post '/api/admin/apifootball/tournaments/{tournamentId}/merge-teams',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('/api/admin/apifootball/tournaments/{tournamentId}/merge-teams', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/api/admin/apifootball/tournaments/{tournamentId}/merge-teams', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/admin/apifootball/tournaments/{tournamentId}/merge-teams");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/api/admin/apifootball/tournaments/{tournamentId}/merge-teams", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api/admin/apifootball/tournaments/{tournamentId}/merge-teams`

*Merge duplicate teams in a tournament.
Finds old teams (without ApiFootballId) and merges them with new teams (with ApiFootballId).
Transfers DisplayName (Swedish name), FifaRank, FifaPoints, and updates all references.
Use dryRun=true (default) to preview changes without applying them.*

<h3 id="post__api_admin_apifootball_tournaments_{tournamentid}_merge-teams-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|tournamentId|path|string(uuid)|true|none|
|dryRun|query|boolean|false|none|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": {
    "teamsMerged": 0,
    "teamsDeleted": 0,
    "matchesUpdated": 0,
    "predictionsUpdated": 0,
    "favoritesUpdated": 0,
    "wasDryRun": true,
    "mergeActions": [
      {
        "oldTeamName": "string",
        "oldTeamId": "2cc91b4f-bb2c-4e92-8025-83da45bec7aa",
        "newTeamName": "string",
        "newTeamId": "e64af117-bcb1-4d41-a79b-76a519341754",
        "transferredDisplayName": "string",
        "transferredFifaRank": 0,
        "transferredFifaPoints": 0.1
      }
    ]
  }
}
```

<h3 id="post__api_admin_apifootball_tournaments_{tournamentid}_merge-teams-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[MergeDuplicateTeamsResultResult](#schemamergeduplicateteamsresultresult)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

## post__api_admin_apifootball_tournaments_{tournamentId}_standings

> Code samples

```shell
# You can also use wget
curl -X POST /api/admin/apifootball/tournaments/{tournamentId}/standings \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST /api/admin/apifootball/tournaments/{tournamentId}/standings HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/admin/apifootball/tournaments/{tournamentId}/standings',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post '/api/admin/apifootball/tournaments/{tournamentId}/standings',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('/api/admin/apifootball/tournaments/{tournamentId}/standings', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/api/admin/apifootball/tournaments/{tournamentId}/standings', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/admin/apifootball/tournaments/{tournamentId}/standings");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/api/admin/apifootball/tournaments/{tournamentId}/standings", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api/admin/apifootball/tournaments/{tournamentId}/standings`

*Sync group standings from API-FOOTBALL.
Creates groups if they don't exist, assigns teams to groups,
and updates group standings (position, points, goals, etc.).*

<h3 id="post__api_admin_apifootball_tournaments_{tournamentid}_standings-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|tournamentId|path|string(uuid)|true|none|
|force|query|boolean|false|none|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": {
    "groupsCreated": 0,
    "groupsUpdated": 0,
    "teamsAssignedToGroups": 0,
    "standingsUpserted": 0,
    "warnings": [
      "string"
    ],
    "syncedAt": "2019-08-24T14:15:22Z"
  }
}
```

<h3 id="post__api_admin_apifootball_tournaments_{tournamentid}_standings-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[SyncGroupStandingsResultResult](#schemasyncgroupstandingsresultresult)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

## post__api_admin_apifootball_tournaments_{tournamentId}_squads

> Code samples

```shell
# You can also use wget
curl -X POST /api/admin/apifootball/tournaments/{tournamentId}/squads \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST /api/admin/apifootball/tournaments/{tournamentId}/squads HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/admin/apifootball/tournaments/{tournamentId}/squads',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post '/api/admin/apifootball/tournaments/{tournamentId}/squads',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('/api/admin/apifootball/tournaments/{tournamentId}/squads', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/api/admin/apifootball/tournaments/{tournamentId}/squads', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/admin/apifootball/tournaments/{tournamentId}/squads");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/api/admin/apifootball/tournaments/{tournamentId}/squads", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api/admin/apifootball/tournaments/{tournamentId}/squads`

*Sync team squads (players) from API-FOOTBALL.
Fetches all players for all teams in the tournament.
Players are used for top scorer predictions and lineup display.*

<h3 id="post__api_admin_apifootball_tournaments_{tournamentid}_squads-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|tournamentId|path|string(uuid)|true|none|
|force|query|boolean|false|none|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": {
    "teamsProcessed": 0,
    "teamsSkipped": 0,
    "playersCreated": 0,
    "playersUpdated": 0,
    "warnings": [
      "string"
    ],
    "syncedAt": "2019-08-24T14:15:22Z"
  }
}
```

<h3 id="post__api_admin_apifootball_tournaments_{tournamentid}_squads-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[SyncTeamSquadsResultResult](#schemasyncteamsquadsresultresult)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

<h1 id="tippr-api-adminbonuspredictions">AdminBonusPredictions</h1>

## get__api_admin_bonus-predictions

> Code samples

```shell
# You can also use wget
curl -X GET /api/admin/bonus-predictions \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET /api/admin/bonus-predictions HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/admin/bonus-predictions',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get '/api/admin/bonus-predictions',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('/api/admin/bonus-predictions', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/api/admin/bonus-predictions', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/admin/bonus-predictions");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/admin/bonus-predictions", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/admin/bonus-predictions`

<h3 id="get__api_admin_bonus-predictions-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|leagueId|query|string(uuid)|false|none|
|questionId|query|string(uuid)|false|none|
|userId|query|string(uuid)|false|none|
|page|query|integer(int32)|false|none|
|pageSize|query|integer(int32)|false|none|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": {
    "items": [
      {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "userId": "2c4a230c-5085-4924-a3e1-25fb4fc5965b",
        "username": "string",
        "bonusQuestionId": "a0b61934-6fef-4d97-866d-54f4b60aee83",
        "leagueId": "58549e12-c6e6-4e03-99d1-6e916f71ce9a",
        "leagueName": "string",
        "answerTeamId": "ab2250dd-c194-4fab-a78b-360f3b350150",
        "answerTeamName": "string",
        "answerText": "string",
        "pointsEarned": 0
      }
    ],
    "totalCount": 0,
    "page": 0,
    "pageSize": 0,
    "totalPages": 0,
    "hasNextPage": true,
    "hasPreviousPage": true
  }
}
```

<h3 id="get__api_admin_bonus-predictions-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[AdminBonusPredictionListDtoPagedResultResult](#schemaadminbonuspredictionlistdtopagedresultresult)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

<h1 id="tippr-api-adminbonusquestions">AdminBonusQuestions</h1>

## get__api_admin_bonus-questions_{bonusQuestionId}

> Code samples

```shell
# You can also use wget
curl -X GET /api/admin/bonus-questions/{bonusQuestionId} \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET /api/admin/bonus-questions/{bonusQuestionId} HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/admin/bonus-questions/{bonusQuestionId}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get '/api/admin/bonus-questions/{bonusQuestionId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('/api/admin/bonus-questions/{bonusQuestionId}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/api/admin/bonus-questions/{bonusQuestionId}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/admin/bonus-questions/{bonusQuestionId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/admin/bonus-questions/{bonusQuestionId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/admin/bonus-questions/{bonusQuestionId}`

<h3 id="get__api_admin_bonus-questions_{bonusquestionid}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|bonusQuestionId|path|string(uuid)|true|none|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "tournamentId": "4a951104-9f98-4996-b388-a0ef2c00bb2a",
    "tournamentName": "string",
    "questionType": 0,
    "question": "string",
    "answerTeamId": "ab2250dd-c194-4fab-a78b-360f3b350150",
    "answerTeamName": "string",
    "answerText": "string",
    "isResolved": true,
    "points": 0,
    "createdAt": "2019-08-24T14:15:22Z",
    "updatedAt": "2019-08-24T14:15:22Z",
    "predictionCount": 0
  }
}
```

<h3 id="get__api_admin_bonus-questions_{bonusquestionid}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[AdminBonusQuestionDtoResult](#schemaadminbonusquestiondtoresult)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

## put__api_admin_bonus-questions_{bonusQuestionId}

> Code samples

```shell
# You can also use wget
curl -X PUT /api/admin/bonus-questions/{bonusQuestionId} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
PUT /api/admin/bonus-questions/{bonusQuestionId} HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```javascript
const inputBody = '{
  "questionType": 0,
  "question": "string",
  "points": 0
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/admin/bonus-questions/{bonusQuestionId}',
{
  method: 'PUT',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.put '/api/admin/bonus-questions/{bonusQuestionId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.put('/api/admin/bonus-questions/{bonusQuestionId}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('PUT','/api/admin/bonus-questions/{bonusQuestionId}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/admin/bonus-questions/{bonusQuestionId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "/api/admin/bonus-questions/{bonusQuestionId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /api/admin/bonus-questions/{bonusQuestionId}`

> Body parameter

```json
{
  "questionType": 0,
  "question": "string",
  "points": 0
}
```

<h3 id="put__api_admin_bonus-questions_{bonusquestionid}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|bonusQuestionId|path|string(uuid)|true|none|
|body|body|[UpdateBonusQuestionRequest](#schemaupdatebonusquestionrequest)|false|none|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "tournamentId": "4a951104-9f98-4996-b388-a0ef2c00bb2a",
    "tournamentName": "string",
    "questionType": 0,
    "question": "string",
    "answerTeamId": "ab2250dd-c194-4fab-a78b-360f3b350150",
    "answerTeamName": "string",
    "answerText": "string",
    "isResolved": true,
    "points": 0,
    "createdAt": "2019-08-24T14:15:22Z",
    "updatedAt": "2019-08-24T14:15:22Z",
    "predictionCount": 0
  }
}
```

<h3 id="put__api_admin_bonus-questions_{bonusquestionid}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[AdminBonusQuestionDtoResult](#schemaadminbonusquestiondtoresult)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

## delete__api_admin_bonus-questions_{bonusQuestionId}

> Code samples

```shell
# You can also use wget
curl -X DELETE /api/admin/bonus-questions/{bonusQuestionId} \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
DELETE /api/admin/bonus-questions/{bonusQuestionId} HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/admin/bonus-questions/{bonusQuestionId}',
{
  method: 'DELETE',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.delete '/api/admin/bonus-questions/{bonusQuestionId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.delete('/api/admin/bonus-questions/{bonusQuestionId}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('DELETE','/api/admin/bonus-questions/{bonusQuestionId}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/admin/bonus-questions/{bonusQuestionId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "/api/admin/bonus-questions/{bonusQuestionId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /api/admin/bonus-questions/{bonusQuestionId}`

<h3 id="delete__api_admin_bonus-questions_{bonusquestionid}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|bonusQuestionId|path|string(uuid)|true|none|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": true
}
```

<h3 id="delete__api_admin_bonus-questions_{bonusquestionid}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[BooleanResult](#schemabooleanresult)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

## post__api_admin_bonus-questions_{bonusQuestionId}_recalculate

> Code samples

```shell
# You can also use wget
curl -X POST /api/admin/bonus-questions/{bonusQuestionId}/recalculate \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST /api/admin/bonus-questions/{bonusQuestionId}/recalculate HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/admin/bonus-questions/{bonusQuestionId}/recalculate',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post '/api/admin/bonus-questions/{bonusQuestionId}/recalculate',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('/api/admin/bonus-questions/{bonusQuestionId}/recalculate', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/api/admin/bonus-questions/{bonusQuestionId}/recalculate', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/admin/bonus-questions/{bonusQuestionId}/recalculate");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/api/admin/bonus-questions/{bonusQuestionId}/recalculate", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api/admin/bonus-questions/{bonusQuestionId}/recalculate`

<h3 id="post__api_admin_bonus-questions_{bonusquestionid}_recalculate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|bonusQuestionId|path|string(uuid)|true|none|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": {
    "predictionsUpdated": 0,
    "correctPredictions": 0,
    "totalPointsAwarded": 0,
    "leaguesAffected": 0
  }
}
```

<h3 id="post__api_admin_bonus-questions_{bonusquestionid}_recalculate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[RecalculateBonusQuestionResultResult](#schemarecalculatebonusquestionresultresult)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

<h1 id="tippr-api-adminchat">AdminChat</h1>

## get__api_admin_chat_messages

> Code samples

```shell
# You can also use wget
curl -X GET /api/admin/chat/messages \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET /api/admin/chat/messages HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/admin/chat/messages',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get '/api/admin/chat/messages',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('/api/admin/chat/messages', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/api/admin/chat/messages', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/admin/chat/messages");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/admin/chat/messages", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/admin/chat/messages`

<h3 id="get__api_admin_chat_messages-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|leagueId|query|string(uuid)|false|none|
|cursor|query|string(date-time)|false|none|
|take|query|integer(int32)|false|none|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": {
    "messages": [
      {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "leagueId": "58549e12-c6e6-4e03-99d1-6e916f71ce9a",
        "leagueName": "string",
        "userId": "2c4a230c-5085-4924-a3e1-25fb4fc5965b",
        "username": "string",
        "userDisplayName": "string",
        "userAvatarUrl": "string",
        "message": "string",
        "isEdited": true,
        "editedAt": "2019-08-24T14:15:22Z",
        "isDeleted": true,
        "createdAt": "2019-08-24T14:15:22Z"
      }
    ],
    "nextCursor": "2019-08-24T14:15:22Z",
    "hasMore": true
  }
}
```

<h3 id="get__api_admin_chat_messages-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[AdminChatMessagesResponseResult](#schemaadminchatmessagesresponseresult)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

## delete__api_admin_chat_messages_{messageId}

> Code samples

```shell
# You can also use wget
curl -X DELETE /api/admin/chat/messages/{messageId} \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
DELETE /api/admin/chat/messages/{messageId} HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/admin/chat/messages/{messageId}',
{
  method: 'DELETE',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.delete '/api/admin/chat/messages/{messageId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.delete('/api/admin/chat/messages/{messageId}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('DELETE','/api/admin/chat/messages/{messageId}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/admin/chat/messages/{messageId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "/api/admin/chat/messages/{messageId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /api/admin/chat/messages/{messageId}`

<h3 id="delete__api_admin_chat_messages_{messageid}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|messageId|path|string(uuid)|true|none|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": true
}
```

<h3 id="delete__api_admin_chat_messages_{messageid}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[BooleanResult](#schemabooleanresult)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

<h1 id="tippr-api-adminleagues">AdminLeagues</h1>

## get__api_admin_leagues

> Code samples

```shell
# You can also use wget
curl -X GET /api/admin/leagues \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET /api/admin/leagues HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/admin/leagues',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get '/api/admin/leagues',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('/api/admin/leagues', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/api/admin/leagues', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/admin/leagues");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/admin/leagues", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/admin/leagues`

<h3 id="get__api_admin_leagues-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|tournamentId|query|string(uuid)|false|none|
|ownerId|query|string(uuid)|false|none|
|search|query|string|false|none|
|isPublic|query|boolean|false|none|
|page|query|integer(int32)|false|none|
|pageSize|query|integer(int32)|false|none|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": {
    "items": [
      {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "name": "string",
        "description": "string",
        "tournamentId": "4a951104-9f98-4996-b388-a0ef2c00bb2a",
        "tournamentName": "string",
        "ownerId": "4d206909-730f-409a-88f6-dcfaa8fc28cc",
        "ownerUsername": "string",
        "isPublic": true,
        "isGlobal": true,
        "maxMembers": 0,
        "createdAt": "2019-08-24T14:15:22Z",
        "memberCount": 0
      }
    ],
    "totalCount": 0,
    "page": 0,
    "pageSize": 0,
    "totalPages": 0,
    "hasNextPage": true,
    "hasPreviousPage": true
  }
}
```

<h3 id="get__api_admin_leagues-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[AdminLeagueListDtoPagedResultResult](#schemaadminleaguelistdtopagedresultresult)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

## get__api_admin_leagues_{leagueId}

> Code samples

```shell
# You can also use wget
curl -X GET /api/admin/leagues/{leagueId} \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET /api/admin/leagues/{leagueId} HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/admin/leagues/{leagueId}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get '/api/admin/leagues/{leagueId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('/api/admin/leagues/{leagueId}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/api/admin/leagues/{leagueId}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/admin/leagues/{leagueId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/admin/leagues/{leagueId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/admin/leagues/{leagueId}`

<h3 id="get__api_admin_leagues_{leagueid}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|leagueId|path|string(uuid)|true|none|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "name": "string",
    "description": "string",
    "tournamentId": "4a951104-9f98-4996-b388-a0ef2c00bb2a",
    "tournamentName": "string",
    "ownerId": "4d206909-730f-409a-88f6-dcfaa8fc28cc",
    "ownerUsername": "string",
    "inviteCode": "string",
    "isPublic": true,
    "isGlobal": true,
    "isSystemCreated": true,
    "maxMembers": 0,
    "imageUrl": "string",
    "createdAt": "2019-08-24T14:15:22Z",
    "updatedAt": "2019-08-24T14:15:22Z",
    "memberCount": 0,
    "predictionCount": 0
  }
}
```

<h3 id="get__api_admin_leagues_{leagueid}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[AdminLeagueDtoResult](#schemaadminleaguedtoresult)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

## put__api_admin_leagues_{leagueId}

> Code samples

```shell
# You can also use wget
curl -X PUT /api/admin/leagues/{leagueId} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
PUT /api/admin/leagues/{leagueId} HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```javascript
const inputBody = '{
  "name": "string",
  "description": "string",
  "isPublic": true,
  "isGlobal": true,
  "maxMembers": 0,
  "imageUrl": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/admin/leagues/{leagueId}',
{
  method: 'PUT',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.put '/api/admin/leagues/{leagueId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.put('/api/admin/leagues/{leagueId}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('PUT','/api/admin/leagues/{leagueId}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/admin/leagues/{leagueId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "/api/admin/leagues/{leagueId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /api/admin/leagues/{leagueId}`

> Body parameter

```json
{
  "name": "string",
  "description": "string",
  "isPublic": true,
  "isGlobal": true,
  "maxMembers": 0,
  "imageUrl": "string"
}
```

<h3 id="put__api_admin_leagues_{leagueid}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|leagueId|path|string(uuid)|true|none|
|body|body|[UpdateAdminLeagueRequest](#schemaupdateadminleaguerequest)|false|none|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "name": "string",
    "description": "string",
    "tournamentId": "4a951104-9f98-4996-b388-a0ef2c00bb2a",
    "tournamentName": "string",
    "ownerId": "4d206909-730f-409a-88f6-dcfaa8fc28cc",
    "ownerUsername": "string",
    "inviteCode": "string",
    "isPublic": true,
    "isGlobal": true,
    "isSystemCreated": true,
    "maxMembers": 0,
    "imageUrl": "string",
    "createdAt": "2019-08-24T14:15:22Z",
    "updatedAt": "2019-08-24T14:15:22Z",
    "memberCount": 0,
    "predictionCount": 0
  }
}
```

<h3 id="put__api_admin_leagues_{leagueid}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[AdminLeagueDtoResult](#schemaadminleaguedtoresult)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

## delete__api_admin_leagues_{leagueId}

> Code samples

```shell
# You can also use wget
curl -X DELETE /api/admin/leagues/{leagueId} \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
DELETE /api/admin/leagues/{leagueId} HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/admin/leagues/{leagueId}',
{
  method: 'DELETE',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.delete '/api/admin/leagues/{leagueId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.delete('/api/admin/leagues/{leagueId}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('DELETE','/api/admin/leagues/{leagueId}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/admin/leagues/{leagueId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "/api/admin/leagues/{leagueId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /api/admin/leagues/{leagueId}`

<h3 id="delete__api_admin_leagues_{leagueid}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|leagueId|path|string(uuid)|true|none|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": true
}
```

<h3 id="delete__api_admin_leagues_{leagueid}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[BooleanResult](#schemabooleanresult)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

## post__api_admin_leagues_{leagueId}_invite-code_regenerate

> Code samples

```shell
# You can also use wget
curl -X POST /api/admin/leagues/{leagueId}/invite-code/regenerate \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST /api/admin/leagues/{leagueId}/invite-code/regenerate HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/admin/leagues/{leagueId}/invite-code/regenerate',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post '/api/admin/leagues/{leagueId}/invite-code/regenerate',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('/api/admin/leagues/{leagueId}/invite-code/regenerate', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/api/admin/leagues/{leagueId}/invite-code/regenerate', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/admin/leagues/{leagueId}/invite-code/regenerate");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/api/admin/leagues/{leagueId}/invite-code/regenerate", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api/admin/leagues/{leagueId}/invite-code/regenerate`

<h3 id="post__api_admin_leagues_{leagueid}_invite-code_regenerate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|leagueId|path|string(uuid)|true|none|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": "string"
}
```

<h3 id="post__api_admin_leagues_{leagueid}_invite-code_regenerate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[StringResult](#schemastringresult)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

## get__api_admin_leagues_{leagueId}_members

> Code samples

```shell
# You can also use wget
curl -X GET /api/admin/leagues/{leagueId}/members \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET /api/admin/leagues/{leagueId}/members HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/admin/leagues/{leagueId}/members',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get '/api/admin/leagues/{leagueId}/members',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('/api/admin/leagues/{leagueId}/members', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/api/admin/leagues/{leagueId}/members', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/admin/leagues/{leagueId}/members");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/admin/leagues/{leagueId}/members", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/admin/leagues/{leagueId}/members`

<h3 id="get__api_admin_leagues_{leagueid}_members-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|leagueId|path|string(uuid)|true|none|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "leagueId": "58549e12-c6e6-4e03-99d1-6e916f71ce9a",
      "userId": "2c4a230c-5085-4924-a3e1-25fb4fc5965b",
      "username": "string",
      "displayName": "string",
      "email": "string",
      "avatarUrl": "string",
      "joinedAt": "2019-08-24T14:15:22Z",
      "isAdmin": true,
      "isMuted": true,
      "totalPoints": 0,
      "rank": 0
    }
  ]
}
```

<h3 id="get__api_admin_leagues_{leagueid}_members-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[AdminLeagueMemberDtoIReadOnlyListResult](#schemaadminleaguememberdtoireadonlylistresult)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

## post__api_admin_leagues_{leagueId}_members

> Code samples

```shell
# You can also use wget
curl -X POST /api/admin/leagues/{leagueId}/members \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST /api/admin/leagues/{leagueId}/members HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```javascript
const inputBody = '{
  "userId": "2c4a230c-5085-4924-a3e1-25fb4fc5965b",
  "isAdmin": true
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/admin/leagues/{leagueId}/members',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post '/api/admin/leagues/{leagueId}/members',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('/api/admin/leagues/{leagueId}/members', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/api/admin/leagues/{leagueId}/members', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/admin/leagues/{leagueId}/members");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/api/admin/leagues/{leagueId}/members", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api/admin/leagues/{leagueId}/members`

> Body parameter

```json
{
  "userId": "2c4a230c-5085-4924-a3e1-25fb4fc5965b",
  "isAdmin": true
}
```

<h3 id="post__api_admin_leagues_{leagueid}_members-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|leagueId|path|string(uuid)|true|none|
|body|body|[AddLeagueMemberRequest](#schemaaddleaguememberrequest)|false|none|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": "808ac6e4-93ed-4040-85a5-6c71a2444e90"
}
```

<h3 id="post__api_admin_leagues_{leagueid}_members-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[GuidResult](#schemaguidresult)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

## delete__api_admin_leagues_{leagueId}_members_{userId}

> Code samples

```shell
# You can also use wget
curl -X DELETE /api/admin/leagues/{leagueId}/members/{userId} \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
DELETE /api/admin/leagues/{leagueId}/members/{userId} HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/admin/leagues/{leagueId}/members/{userId}',
{
  method: 'DELETE',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.delete '/api/admin/leagues/{leagueId}/members/{userId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.delete('/api/admin/leagues/{leagueId}/members/{userId}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('DELETE','/api/admin/leagues/{leagueId}/members/{userId}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/admin/leagues/{leagueId}/members/{userId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "/api/admin/leagues/{leagueId}/members/{userId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /api/admin/leagues/{leagueId}/members/{userId}`

<h3 id="delete__api_admin_leagues_{leagueid}_members_{userid}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|leagueId|path|string(uuid)|true|none|
|userId|path|string(uuid)|true|none|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": true
}
```

<h3 id="delete__api_admin_leagues_{leagueid}_members_{userid}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[BooleanResult](#schemabooleanresult)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

## put__api_admin_leagues_{leagueId}_members_{userId}

> Code samples

```shell
# You can also use wget
curl -X PUT /api/admin/leagues/{leagueId}/members/{userId} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
PUT /api/admin/leagues/{leagueId}/members/{userId} HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```javascript
const inputBody = '{
  "isAdmin": true,
  "isMuted": true
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/admin/leagues/{leagueId}/members/{userId}',
{
  method: 'PUT',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.put '/api/admin/leagues/{leagueId}/members/{userId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.put('/api/admin/leagues/{leagueId}/members/{userId}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('PUT','/api/admin/leagues/{leagueId}/members/{userId}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/admin/leagues/{leagueId}/members/{userId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "/api/admin/leagues/{leagueId}/members/{userId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /api/admin/leagues/{leagueId}/members/{userId}`

> Body parameter

```json
{
  "isAdmin": true,
  "isMuted": true
}
```

<h3 id="put__api_admin_leagues_{leagueid}_members_{userid}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|leagueId|path|string(uuid)|true|none|
|userId|path|string(uuid)|true|none|
|body|body|[UpdateLeagueMemberRequest](#schemaupdateleaguememberrequest)|false|none|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": true
}
```

<h3 id="put__api_admin_leagues_{leagueid}_members_{userid}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[BooleanResult](#schemabooleanresult)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

## post__api_admin_leagues_{leagueId}_standings_recalculate

> Code samples

```shell
# You can also use wget
curl -X POST /api/admin/leagues/{leagueId}/standings/recalculate \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST /api/admin/leagues/{leagueId}/standings/recalculate HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/admin/leagues/{leagueId}/standings/recalculate',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post '/api/admin/leagues/{leagueId}/standings/recalculate',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('/api/admin/leagues/{leagueId}/standings/recalculate', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/api/admin/leagues/{leagueId}/standings/recalculate', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/admin/leagues/{leagueId}/standings/recalculate");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/api/admin/leagues/{leagueId}/standings/recalculate", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api/admin/leagues/{leagueId}/standings/recalculate`

<h3 id="post__api_admin_leagues_{leagueid}_standings_recalculate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|leagueId|path|string(uuid)|true|none|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": true
}
```

<h3 id="post__api_admin_leagues_{leagueid}_standings_recalculate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[BooleanResult](#schemabooleanresult)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

<h1 id="tippr-api-adminmatches">AdminMatches</h1>

## post__api_admin_matches

> Code samples

```shell
# You can also use wget
curl -X POST /api/admin/matches \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST /api/admin/matches HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```javascript
const inputBody = '{
  "tournamentId": "4a951104-9f98-4996-b388-a0ef2c00bb2a",
  "homeTeamId": "fb7b8236-8f4a-4255-b25d-a64d7c4d6968",
  "awayTeamId": "aa1734e3-668a-43b1-918b-ecab48ec02f9",
  "matchDate": "2019-08-24T14:15:22Z",
  "stage": 0,
  "venue": "string",
  "apiFootballId": 0
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/admin/matches',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post '/api/admin/matches',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('/api/admin/matches', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/api/admin/matches', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/admin/matches");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/api/admin/matches", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api/admin/matches`

> Body parameter

```json
{
  "tournamentId": "4a951104-9f98-4996-b388-a0ef2c00bb2a",
  "homeTeamId": "fb7b8236-8f4a-4255-b25d-a64d7c4d6968",
  "awayTeamId": "aa1734e3-668a-43b1-918b-ecab48ec02f9",
  "matchDate": "2019-08-24T14:15:22Z",
  "stage": 0,
  "venue": "string",
  "apiFootballId": 0
}
```

<h3 id="post__api_admin_matches-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[CreateMatchRequest](#schemacreatematchrequest)|false|none|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": "808ac6e4-93ed-4040-85a5-6c71a2444e90"
}
```

<h3 id="post__api_admin_matches-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[GuidResult](#schemaguidresult)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

## put__api_admin_matches_{matchId}

> Code samples

```shell
# You can also use wget
curl -X PUT /api/admin/matches/{matchId} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
PUT /api/admin/matches/{matchId} HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```javascript
const inputBody = '{
  "matchDate": "2019-08-24T14:15:22Z",
  "stage": 0,
  "status": 0,
  "venue": "string",
  "apiFootballId": 0
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/admin/matches/{matchId}',
{
  method: 'PUT',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.put '/api/admin/matches/{matchId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.put('/api/admin/matches/{matchId}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('PUT','/api/admin/matches/{matchId}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/admin/matches/{matchId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "/api/admin/matches/{matchId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /api/admin/matches/{matchId}`

> Body parameter

```json
{
  "matchDate": "2019-08-24T14:15:22Z",
  "stage": 0,
  "status": 0,
  "venue": "string",
  "apiFootballId": 0
}
```

<h3 id="put__api_admin_matches_{matchid}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|matchId|path|string(uuid)|true|none|
|body|body|[UpdateMatchRequest](#schemaupdatematchrequest)|false|none|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "tournamentId": "4a951104-9f98-4996-b388-a0ef2c00bb2a",
    "tournamentName": "string",
    "homeTeamId": "fb7b8236-8f4a-4255-b25d-a64d7c4d6968",
    "homeTeamName": "string",
    "homeTeamCode": "string",
    "homeTeamLogoUrl": "string",
    "awayTeamId": "aa1734e3-668a-43b1-918b-ecab48ec02f9",
    "awayTeamName": "string",
    "awayTeamCode": "string",
    "awayTeamLogoUrl": "string",
    "matchDate": "2019-08-24T14:15:22Z",
    "stage": 0,
    "homeScore": 0,
    "awayScore": 0,
    "status": 0,
    "venue": "string",
    "apiFootballId": 0,
    "resultVersion": 0,
    "createdAt": "2019-08-24T14:15:22Z",
    "updatedAt": "2019-08-24T14:15:22Z",
    "predictionCount": 0
  }
}
```

<h3 id="put__api_admin_matches_{matchid}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[AdminMatchDtoResult](#schemaadminmatchdtoresult)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

## put__api_admin_matches_{matchId}_result

> Code samples

```shell
# You can also use wget
curl -X PUT /api/admin/matches/{matchId}/result \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
PUT /api/admin/matches/{matchId}/result HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```javascript
const inputBody = '{
  "homeScore": 0,
  "awayScore": 0,
  "status": 0
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/admin/matches/{matchId}/result',
{
  method: 'PUT',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.put '/api/admin/matches/{matchId}/result',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.put('/api/admin/matches/{matchId}/result', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('PUT','/api/admin/matches/{matchId}/result', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/admin/matches/{matchId}/result");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "/api/admin/matches/{matchId}/result", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /api/admin/matches/{matchId}/result`

> Body parameter

```json
{
  "homeScore": 0,
  "awayScore": 0,
  "status": 0
}
```

<h3 id="put__api_admin_matches_{matchid}_result-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|matchId|path|string(uuid)|true|none|
|body|body|[UpdateMatchResultRequest](#schemaupdatematchresultrequest)|false|none|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": true
}
```

<h3 id="put__api_admin_matches_{matchid}_result-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[BooleanResult](#schemabooleanresult)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

## post__api_admin_matches_bulk

> Code samples

```shell
# You can also use wget
curl -X POST /api/admin/matches/bulk \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST /api/admin/matches/bulk HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```javascript
const inputBody = '{
  "tournamentId": "4a951104-9f98-4996-b388-a0ef2c00bb2a",
  "matches": [
    {
      "homeTeamId": "fb7b8236-8f4a-4255-b25d-a64d7c4d6968",
      "awayTeamId": "aa1734e3-668a-43b1-918b-ecab48ec02f9",
      "matchDate": "2019-08-24T14:15:22Z",
      "stage": 0,
      "venue": "string",
      "apiFootballId": 0
    }
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/admin/matches/bulk',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post '/api/admin/matches/bulk',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('/api/admin/matches/bulk', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/api/admin/matches/bulk', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/admin/matches/bulk");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/api/admin/matches/bulk", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api/admin/matches/bulk`

> Body parameter

```json
{
  "tournamentId": "4a951104-9f98-4996-b388-a0ef2c00bb2a",
  "matches": [
    {
      "homeTeamId": "fb7b8236-8f4a-4255-b25d-a64d7c4d6968",
      "awayTeamId": "aa1734e3-668a-43b1-918b-ecab48ec02f9",
      "matchDate": "2019-08-24T14:15:22Z",
      "stage": 0,
      "venue": "string",
      "apiFootballId": 0
    }
  ]
}
```

<h3 id="post__api_admin_matches_bulk-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[BulkCreateMatchesRequest](#schemabulkcreatematchesrequest)|false|none|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": {
    "createdCount": 0,
    "failedCount": 0,
    "errors": [
      "string"
    ],
    "createdIds": [
      "497f6eca-6276-4993-bfeb-53cbbbba6f08"
    ]
  }
}
```

<h3 id="post__api_admin_matches_bulk-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[BulkCreateMatchesResultResult](#schemabulkcreatematchesresultresult)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

## post__api_admin_matches_{matchId}_recalculate

> Code samples

```shell
# You can also use wget
curl -X POST /api/admin/matches/{matchId}/recalculate \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST /api/admin/matches/{matchId}/recalculate HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/admin/matches/{matchId}/recalculate',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post '/api/admin/matches/{matchId}/recalculate',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('/api/admin/matches/{matchId}/recalculate', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/api/admin/matches/{matchId}/recalculate', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/admin/matches/{matchId}/recalculate");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/api/admin/matches/{matchId}/recalculate", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api/admin/matches/{matchId}/recalculate`

<h3 id="post__api_admin_matches_{matchid}_recalculate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|matchId|path|string(uuid)|true|none|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": {
    "predictionsUpdated": 0,
    "leaguesAffected": 0
  }
}
```

<h3 id="post__api_admin_matches_{matchid}_recalculate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[RecalculateMatchPointsResultResult](#schemarecalculatematchpointsresultresult)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

<h1 id="tippr-api-adminpredictions">AdminPredictions</h1>

## get__api_admin_predictions

> Code samples

```shell
# You can also use wget
curl -X GET /api/admin/predictions \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET /api/admin/predictions HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/admin/predictions',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get '/api/admin/predictions',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('/api/admin/predictions', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/api/admin/predictions', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/admin/predictions");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/admin/predictions", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/admin/predictions`

<h3 id="get__api_admin_predictions-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|leagueId|query|string(uuid)|false|none|
|matchId|query|string(uuid)|false|none|
|userId|query|string(uuid)|false|none|
|tournamentId|query|string(uuid)|false|none|
|page|query|integer(int32)|false|none|
|pageSize|query|integer(int32)|false|none|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": {
    "items": [
      {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "userId": "2c4a230c-5085-4924-a3e1-25fb4fc5965b",
        "username": "string",
        "matchId": "685569fd-95e6-4335-9aa5-fdd22382bd9e",
        "matchDescription": "string",
        "leagueId": "58549e12-c6e6-4e03-99d1-6e916f71ce9a",
        "leagueName": "string",
        "homeScore": 0,
        "awayScore": 0,
        "pointsEarned": 0,
        "isScored": true
      }
    ],
    "totalCount": 0,
    "page": 0,
    "pageSize": 0,
    "totalPages": 0,
    "hasNextPage": true,
    "hasPreviousPage": true
  }
}
```

<h3 id="get__api_admin_predictions-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[AdminPredictionListDtoPagedResultResult](#schemaadminpredictionlistdtopagedresultresult)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

## get__api_admin_predictions_{predictionId}

> Code samples

```shell
# You can also use wget
curl -X GET /api/admin/predictions/{predictionId} \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET /api/admin/predictions/{predictionId} HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/admin/predictions/{predictionId}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get '/api/admin/predictions/{predictionId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('/api/admin/predictions/{predictionId}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/api/admin/predictions/{predictionId}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/admin/predictions/{predictionId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/admin/predictions/{predictionId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/admin/predictions/{predictionId}`

<h3 id="get__api_admin_predictions_{predictionid}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|predictionId|path|string(uuid)|true|none|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "userId": "2c4a230c-5085-4924-a3e1-25fb4fc5965b",
    "username": "string",
    "userDisplayName": "string",
    "matchId": "685569fd-95e6-4335-9aa5-fdd22382bd9e",
    "matchDescription": "string",
    "leagueId": "58549e12-c6e6-4e03-99d1-6e916f71ce9a",
    "leagueName": "string",
    "homeScore": 0,
    "awayScore": 0,
    "actualHomeScore": 0,
    "actualAwayScore": 0,
    "pointsEarned": 0,
    "isScored": true,
    "scoredResultVersion": 0,
    "scoredAt": "2019-08-24T14:15:22Z",
    "createdAt": "2019-08-24T14:15:22Z",
    "updatedAt": "2019-08-24T14:15:22Z"
  }
}
```

<h3 id="get__api_admin_predictions_{predictionid}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[AdminPredictionDtoResult](#schemaadminpredictiondtoresult)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

## delete__api_admin_predictions_{predictionId}

> Code samples

```shell
# You can also use wget
curl -X DELETE /api/admin/predictions/{predictionId} \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
DELETE /api/admin/predictions/{predictionId} HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/admin/predictions/{predictionId}',
{
  method: 'DELETE',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.delete '/api/admin/predictions/{predictionId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.delete('/api/admin/predictions/{predictionId}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('DELETE','/api/admin/predictions/{predictionId}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/admin/predictions/{predictionId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "/api/admin/predictions/{predictionId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /api/admin/predictions/{predictionId}`

<h3 id="delete__api_admin_predictions_{predictionid}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|predictionId|path|string(uuid)|true|none|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": true
}
```

<h3 id="delete__api_admin_predictions_{predictionid}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[BooleanResult](#schemabooleanresult)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

## post__api_admin_predictions_recalculate

> Code samples

```shell
# You can also use wget
curl -X POST /api/admin/predictions/recalculate \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST /api/admin/predictions/recalculate HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/admin/predictions/recalculate',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post '/api/admin/predictions/recalculate',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('/api/admin/predictions/recalculate', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/api/admin/predictions/recalculate', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/admin/predictions/recalculate");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/api/admin/predictions/recalculate", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api/admin/predictions/recalculate`

<h3 id="post__api_admin_predictions_recalculate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|leagueId|query|string(uuid)|false|none|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": {
    "predictionsUpdated": 0,
    "totalPoints": 0
  }
}
```

<h3 id="post__api_admin_predictions_recalculate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[RecalculateLeaguePredictionsResultResult](#schemarecalculateleaguepredictionsresultresult)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

<h1 id="tippr-api-adminteams">AdminTeams</h1>

## post__api_admin_teams

> Code samples

```shell
# You can also use wget
curl -X POST /api/admin/teams \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST /api/admin/teams HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```javascript
const inputBody = '{
  "tournamentId": "4a951104-9f98-4996-b388-a0ef2c00bb2a",
  "name": "string",
  "code": "string",
  "flagUrl": "string",
  "groupName": "string",
  "fifaRank": 0,
  "fifaPoints": 0.1,
  "apiFootballId": 0
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/admin/teams',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post '/api/admin/teams',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('/api/admin/teams', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/api/admin/teams', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/admin/teams");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/api/admin/teams", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api/admin/teams`

> Body parameter

```json
{
  "tournamentId": "4a951104-9f98-4996-b388-a0ef2c00bb2a",
  "name": "string",
  "code": "string",
  "flagUrl": "string",
  "groupName": "string",
  "fifaRank": 0,
  "fifaPoints": 0.1,
  "apiFootballId": 0
}
```

<h3 id="post__api_admin_teams-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[CreateTeamRequest](#schemacreateteamrequest)|false|none|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": "808ac6e4-93ed-4040-85a5-6c71a2444e90"
}
```

<h3 id="post__api_admin_teams-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[GuidResult](#schemaguidresult)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

## put__api_admin_teams_{teamId}

> Code samples

```shell
# You can also use wget
curl -X PUT /api/admin/teams/{teamId} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
PUT /api/admin/teams/{teamId} HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```javascript
const inputBody = '{
  "name": "string",
  "code": "string",
  "flagUrl": "string",
  "groupName": "string",
  "fifaRank": 0,
  "fifaPoints": 0.1,
  "apiFootballId": 0
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/admin/teams/{teamId}',
{
  method: 'PUT',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.put '/api/admin/teams/{teamId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.put('/api/admin/teams/{teamId}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('PUT','/api/admin/teams/{teamId}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/admin/teams/{teamId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "/api/admin/teams/{teamId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /api/admin/teams/{teamId}`

> Body parameter

```json
{
  "name": "string",
  "code": "string",
  "flagUrl": "string",
  "groupName": "string",
  "fifaRank": 0,
  "fifaPoints": 0.1,
  "apiFootballId": 0
}
```

<h3 id="put__api_admin_teams_{teamid}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|teamId|path|string(uuid)|true|none|
|body|body|[UpdateTeamRequest](#schemaupdateteamrequest)|false|none|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "tournamentId": "4a951104-9f98-4996-b388-a0ef2c00bb2a",
    "tournamentName": "string",
    "name": "string",
    "code": "string",
    "logoUrl": "string",
    "groupName": "string",
    "fifaRank": 0,
    "fifaPoints": 0.1,
    "fifaRankingUpdatedAt": "2019-08-24T14:15:22Z",
    "apiFootballId": 0,
    "createdAt": "2019-08-24T14:15:22Z",
    "updatedAt": "2019-08-24T14:15:22Z"
  }
}
```

<h3 id="put__api_admin_teams_{teamid}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[AdminTeamDtoResult](#schemaadminteamdtoresult)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

## delete__api_admin_teams_{teamId}

> Code samples

```shell
# You can also use wget
curl -X DELETE /api/admin/teams/{teamId} \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
DELETE /api/admin/teams/{teamId} HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/admin/teams/{teamId}',
{
  method: 'DELETE',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.delete '/api/admin/teams/{teamId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.delete('/api/admin/teams/{teamId}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('DELETE','/api/admin/teams/{teamId}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/admin/teams/{teamId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "/api/admin/teams/{teamId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /api/admin/teams/{teamId}`

<h3 id="delete__api_admin_teams_{teamid}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|teamId|path|string(uuid)|true|none|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": true
}
```

<h3 id="delete__api_admin_teams_{teamid}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[BooleanResult](#schemabooleanresult)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

## post__api_admin_teams_bulk

> Code samples

```shell
# You can also use wget
curl -X POST /api/admin/teams/bulk \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST /api/admin/teams/bulk HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```javascript
const inputBody = '{
  "tournamentId": "4a951104-9f98-4996-b388-a0ef2c00bb2a",
  "teams": [
    {
      "name": "string",
      "code": "string",
      "flagUrl": "string",
      "groupName": "string",
      "fifaRank": 0,
      "fifaPoints": 0.1,
      "apiFootballId": 0
    }
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/admin/teams/bulk',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post '/api/admin/teams/bulk',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('/api/admin/teams/bulk', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/api/admin/teams/bulk', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/admin/teams/bulk");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/api/admin/teams/bulk", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api/admin/teams/bulk`

> Body parameter

```json
{
  "tournamentId": "4a951104-9f98-4996-b388-a0ef2c00bb2a",
  "teams": [
    {
      "name": "string",
      "code": "string",
      "flagUrl": "string",
      "groupName": "string",
      "fifaRank": 0,
      "fifaPoints": 0.1,
      "apiFootballId": 0
    }
  ]
}
```

<h3 id="post__api_admin_teams_bulk-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[BulkCreateTeamsRequest](#schemabulkcreateteamsrequest)|false|none|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": {
    "createdCount": 0,
    "skippedCount": 0,
    "skippedTeams": [
      "string"
    ],
    "createdIds": [
      "497f6eca-6276-4993-bfeb-53cbbbba6f08"
    ]
  }
}
```

<h3 id="post__api_admin_teams_bulk-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[BulkCreateTeamsResultResult](#schemabulkcreateteamsresultresult)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

<h1 id="tippr-api-admintournaments">AdminTournaments</h1>

## put__api_admin_tournaments_{tournamentId}

> Code samples

```shell
# You can also use wget
curl -X PUT /api/admin/tournaments/{tournamentId} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
PUT /api/admin/tournaments/{tournamentId} HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```javascript
const inputBody = '{
  "name": "string",
  "year": 0,
  "type": 0,
  "startDate": "2019-08-24T14:15:22Z",
  "endDate": "2019-08-24T14:15:22Z",
  "logoUrl": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/admin/tournaments/{tournamentId}',
{
  method: 'PUT',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.put '/api/admin/tournaments/{tournamentId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.put('/api/admin/tournaments/{tournamentId}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('PUT','/api/admin/tournaments/{tournamentId}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/admin/tournaments/{tournamentId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "/api/admin/tournaments/{tournamentId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /api/admin/tournaments/{tournamentId}`

> Body parameter

```json
{
  "name": "string",
  "year": 0,
  "type": 0,
  "startDate": "2019-08-24T14:15:22Z",
  "endDate": "2019-08-24T14:15:22Z",
  "logoUrl": "string"
}
```

<h3 id="put__api_admin_tournaments_{tournamentid}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|tournamentId|path|string(uuid)|true|none|
|body|body|[UpdateTournamentRequest](#schemaupdatetournamentrequest)|false|none|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "name": "string",
    "year": 0,
    "type": 0,
    "startDate": "2019-08-24T14:15:22Z",
    "endDate": "2019-08-24T14:15:22Z",
    "logoUrl": "string",
    "isActive": true,
    "createdAt": "2019-08-24T14:15:22Z",
    "updatedAt": "2019-08-24T14:15:22Z",
    "teamCount": 0,
    "matchCount": 0,
    "leagueCount": 0,
    "bonusQuestionCount": 0
  }
}
```

<h3 id="put__api_admin_tournaments_{tournamentid}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[AdminTournamentDtoResult](#schemaadmintournamentdtoresult)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

## delete__api_admin_tournaments_{tournamentId}

> Code samples

```shell
# You can also use wget
curl -X DELETE /api/admin/tournaments/{tournamentId} \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
DELETE /api/admin/tournaments/{tournamentId} HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/admin/tournaments/{tournamentId}',
{
  method: 'DELETE',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.delete '/api/admin/tournaments/{tournamentId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.delete('/api/admin/tournaments/{tournamentId}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('DELETE','/api/admin/tournaments/{tournamentId}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/admin/tournaments/{tournamentId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "/api/admin/tournaments/{tournamentId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /api/admin/tournaments/{tournamentId}`

<h3 id="delete__api_admin_tournaments_{tournamentid}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|tournamentId|path|string(uuid)|true|none|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": true
}
```

<h3 id="delete__api_admin_tournaments_{tournamentid}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[BooleanResult](#schemabooleanresult)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

## post__api_admin_tournaments_{tournamentId}_activate

> Code samples

```shell
# You can also use wget
curl -X POST /api/admin/tournaments/{tournamentId}/activate \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST /api/admin/tournaments/{tournamentId}/activate HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/admin/tournaments/{tournamentId}/activate',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post '/api/admin/tournaments/{tournamentId}/activate',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('/api/admin/tournaments/{tournamentId}/activate', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/api/admin/tournaments/{tournamentId}/activate', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/admin/tournaments/{tournamentId}/activate");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/api/admin/tournaments/{tournamentId}/activate", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api/admin/tournaments/{tournamentId}/activate`

<h3 id="post__api_admin_tournaments_{tournamentid}_activate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|tournamentId|path|string(uuid)|true|none|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": true
}
```

<h3 id="post__api_admin_tournaments_{tournamentid}_activate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[BooleanResult](#schemabooleanresult)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

## post__api_admin_tournaments_{tournamentId}_deactivate

> Code samples

```shell
# You can also use wget
curl -X POST /api/admin/tournaments/{tournamentId}/deactivate \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST /api/admin/tournaments/{tournamentId}/deactivate HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/admin/tournaments/{tournamentId}/deactivate',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post '/api/admin/tournaments/{tournamentId}/deactivate',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('/api/admin/tournaments/{tournamentId}/deactivate', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/api/admin/tournaments/{tournamentId}/deactivate', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/admin/tournaments/{tournamentId}/deactivate");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/api/admin/tournaments/{tournamentId}/deactivate", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api/admin/tournaments/{tournamentId}/deactivate`

<h3 id="post__api_admin_tournaments_{tournamentid}_deactivate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|tournamentId|path|string(uuid)|true|none|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": true
}
```

<h3 id="post__api_admin_tournaments_{tournamentid}_deactivate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[BooleanResult](#schemabooleanresult)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

## post__api_admin_tournaments_{tournamentId}_standings_recalculate

> Code samples

```shell
# You can also use wget
curl -X POST /api/admin/tournaments/{tournamentId}/standings/recalculate \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST /api/admin/tournaments/{tournamentId}/standings/recalculate HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/admin/tournaments/{tournamentId}/standings/recalculate',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post '/api/admin/tournaments/{tournamentId}/standings/recalculate',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('/api/admin/tournaments/{tournamentId}/standings/recalculate', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/api/admin/tournaments/{tournamentId}/standings/recalculate', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/admin/tournaments/{tournamentId}/standings/recalculate");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/api/admin/tournaments/{tournamentId}/standings/recalculate", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api/admin/tournaments/{tournamentId}/standings/recalculate`

<h3 id="post__api_admin_tournaments_{tournamentid}_standings_recalculate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|tournamentId|path|string(uuid)|true|none|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": {
    "leaguesUpdated": 0,
    "totalMembersUpdated": 0
  }
}
```

<h3 id="post__api_admin_tournaments_{tournamentid}_standings_recalculate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[RecalculateTournamentStandingsResultResult](#schemarecalculatetournamentstandingsresultresult)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

<h1 id="tippr-api-adminusers">AdminUsers</h1>

## get__api_admin_users

> Code samples

```shell
# You can also use wget
curl -X GET /api/admin/users \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET /api/admin/users HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/admin/users',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get '/api/admin/users',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('/api/admin/users', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/api/admin/users', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/admin/users");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/admin/users", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/admin/users`

<h3 id="get__api_admin_users-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|search|query|string|false|none|
|page|query|integer(int32)|false|none|
|pageSize|query|integer(int32)|false|none|
|sort|query|string|false|none|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": {
    "items": [
      {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "username": "string",
        "displayName": "string",
        "email": "string",
        "avatarUrl": "string",
        "role": 0,
        "isBanned": true,
        "lastLoginAt": "2019-08-24T14:15:22Z",
        "createdAt": "2019-08-24T14:15:22Z"
      }
    ],
    "totalCount": 0,
    "page": 0,
    "pageSize": 0,
    "totalPages": 0,
    "hasNextPage": true,
    "hasPreviousPage": true
  }
}
```

<h3 id="get__api_admin_users-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[AdminUserListDtoPagedResultResult](#schemaadminuserlistdtopagedresultresult)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

## get__api_admin_users_{userId}

> Code samples

```shell
# You can also use wget
curl -X GET /api/admin/users/{userId} \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET /api/admin/users/{userId} HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/admin/users/{userId}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get '/api/admin/users/{userId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('/api/admin/users/{userId}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/api/admin/users/{userId}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/admin/users/{userId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/admin/users/{userId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/admin/users/{userId}`

<h3 id="get__api_admin_users_{userid}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|userId|path|string(uuid)|true|none|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "authUserId": "5a3cace6-919f-4109-8313-c3a2264a4134",
    "username": "string",
    "displayName": "string",
    "email": "string",
    "avatarUrl": "string",
    "bio": "string",
    "role": 0,
    "isBanned": true,
    "favoriteTeamId": "d03f4e26-a6b7-4158-9c97-87bb7dc42e8b",
    "favoriteTeamName": "string",
    "lastLoginAt": "2019-08-24T14:15:22Z",
    "createdAt": "2019-08-24T14:15:22Z",
    "updatedAt": "2019-08-24T14:15:22Z",
    "leagueCount": 0,
    "ownedLeagueCount": 0,
    "predictionCount": 0
  }
}
```

<h3 id="get__api_admin_users_{userid}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[AdminUserDtoResult](#schemaadminuserdtoresult)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

## put__api_admin_users_{userId}

> Code samples

```shell
# You can also use wget
curl -X PUT /api/admin/users/{userId} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
PUT /api/admin/users/{userId} HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```javascript
const inputBody = '{
  "username": "string",
  "displayName": "string",
  "email": "string",
  "bio": "string",
  "avatarUrl": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/admin/users/{userId}',
{
  method: 'PUT',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.put '/api/admin/users/{userId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.put('/api/admin/users/{userId}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('PUT','/api/admin/users/{userId}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/admin/users/{userId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "/api/admin/users/{userId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /api/admin/users/{userId}`

> Body parameter

```json
{
  "username": "string",
  "displayName": "string",
  "email": "string",
  "bio": "string",
  "avatarUrl": "string"
}
```

<h3 id="put__api_admin_users_{userid}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|userId|path|string(uuid)|true|none|
|body|body|[UpdateAdminUserRequest](#schemaupdateadminuserrequest)|false|none|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "authUserId": "5a3cace6-919f-4109-8313-c3a2264a4134",
    "username": "string",
    "displayName": "string",
    "email": "string",
    "avatarUrl": "string",
    "bio": "string",
    "role": 0,
    "isBanned": true,
    "favoriteTeamId": "d03f4e26-a6b7-4158-9c97-87bb7dc42e8b",
    "favoriteTeamName": "string",
    "lastLoginAt": "2019-08-24T14:15:22Z",
    "createdAt": "2019-08-24T14:15:22Z",
    "updatedAt": "2019-08-24T14:15:22Z",
    "leagueCount": 0,
    "ownedLeagueCount": 0,
    "predictionCount": 0
  }
}
```

<h3 id="put__api_admin_users_{userid}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[AdminUserDtoResult](#schemaadminuserdtoresult)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

## post__api_admin_users_{userId}_roles

> Code samples

```shell
# You can also use wget
curl -X POST /api/admin/users/{userId}/roles \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST /api/admin/users/{userId}/roles HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```javascript
const inputBody = '{
  "role": 0
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/admin/users/{userId}/roles',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post '/api/admin/users/{userId}/roles',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('/api/admin/users/{userId}/roles', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/api/admin/users/{userId}/roles', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/admin/users/{userId}/roles");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/api/admin/users/{userId}/roles", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api/admin/users/{userId}/roles`

> Body parameter

```json
{
  "role": 0
}
```

<h3 id="post__api_admin_users_{userid}_roles-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|userId|path|string(uuid)|true|none|
|body|body|[UpdateUserRoleRequest](#schemaupdateuserrolerequest)|false|none|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": true
}
```

<h3 id="post__api_admin_users_{userid}_roles-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[BooleanResult](#schemabooleanresult)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

## post__api_admin_users_{userId}_ban

> Code samples

```shell
# You can also use wget
curl -X POST /api/admin/users/{userId}/ban \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST /api/admin/users/{userId}/ban HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/admin/users/{userId}/ban',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post '/api/admin/users/{userId}/ban',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('/api/admin/users/{userId}/ban', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/api/admin/users/{userId}/ban', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/admin/users/{userId}/ban");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/api/admin/users/{userId}/ban", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api/admin/users/{userId}/ban`

<h3 id="post__api_admin_users_{userid}_ban-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|userId|path|string(uuid)|true|none|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": true
}
```

<h3 id="post__api_admin_users_{userid}_ban-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[BooleanResult](#schemabooleanresult)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

## post__api_admin_users_{userId}_unban

> Code samples

```shell
# You can also use wget
curl -X POST /api/admin/users/{userId}/unban \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST /api/admin/users/{userId}/unban HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/admin/users/{userId}/unban',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post '/api/admin/users/{userId}/unban',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('/api/admin/users/{userId}/unban', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/api/admin/users/{userId}/unban', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/admin/users/{userId}/unban");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/api/admin/users/{userId}/unban", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api/admin/users/{userId}/unban`

<h3 id="post__api_admin_users_{userid}_unban-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|userId|path|string(uuid)|true|none|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": true
}
```

<h3 id="post__api_admin_users_{userid}_unban-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[BooleanResult](#schemabooleanresult)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

<h1 id="tippr-api-auth">Auth</h1>

## get__api_auth_me

> Code samples

```shell
# You can also use wget
curl -X GET /api/auth/me \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET /api/auth/me HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/auth/me',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get '/api/auth/me',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('/api/auth/me', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/api/auth/me', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/auth/me");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/auth/me", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/auth/me`

*Retrieves the current authenticated user's profile information.*

  <b>Auth:</b> JWT Bearer token required

  <b>Side Effects:</b> Updates the user's LastLoginAt timestamp

  <b>Example Request:</b>

```
             GET /api/auth/me
             Authorization: Bearer <access_token>
             ```

  <b>Example Response:</b>

```
             {
               "isSuccess": true,
               "data": {
                 "userId": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
                 "email": "user@example.com",
                 "username": "johndoe",
                 "displayName": "John Doe",
                 "avatarUrl": "https://storage.example.com/avatars/user.jpg",
                 "bio": "Football enthusiast",
                 "favoriteTeamId": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
                 "favoriteTeamName": "Manchester United",
                 "lastLoginAt": "2024-01-15T10:30:00Z",
                 "role": "User"
               },
               "error": null
             }
             ```

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": {
    "userId": "2c4a230c-5085-4924-a3e1-25fb4fc5965b",
    "email": "string",
    "username": "string",
    "displayName": "string",
    "avatarUrl": "string",
    "bio": "string",
    "favoriteTeamId": "d03f4e26-a6b7-4158-9c97-87bb7dc42e8b",
    "favoriteTeamName": "string",
    "lastLoginAt": "2019-08-24T14:15:22Z",
    "role": 0
  }
}
```

<h3 id="get__api_auth_me-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Returns the current user's profile|[CurrentUserResponseResult](#schemacurrentuserresponseresult)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|JWT token is missing or invalid|[ErrorResponse](#schemaerrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|User has not been synced (should not occur with middleware)|[ErrorResponse](#schemaerrorresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

<h1 id="tippr-api-bonusprediction">BonusPrediction</h1>

## post__api_bonus-predictions

> Code samples

```shell
# You can also use wget
curl -X POST /api/bonus-predictions \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST /api/bonus-predictions HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```javascript
const inputBody = '{
  "leagueId": "58549e12-c6e6-4e03-99d1-6e916f71ce9a",
  "bonusQuestionId": "a0b61934-6fef-4d97-866d-54f4b60aee83",
  "answerTeamId": "ab2250dd-c194-4fab-a78b-360f3b350150",
  "answerText": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/bonus-predictions',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post '/api/bonus-predictions',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('/api/bonus-predictions', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/api/bonus-predictions', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/bonus-predictions");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/api/bonus-predictions", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api/bonus-predictions`

*Submits a prediction for a bonus question within a league.*

  <b>Auth:</b> JWT Bearer token required

  <b>Rules:</b>

<list type="bullet">
  <item>
    <description>User must be a member of the specified league</description>
  </item>
  <item>
    <description>BonusQuestion must belong to the league's tournament</description>
  </item>
  <item>
    <description>Cannot submit after the bonus question is resolved</description>
  </item>
  <item>
    <description>Submitting again will update the existing prediction</description>
  </item>
</list>

  <b>Example Request (Team answer):</b>

```
             POST /api/bonus-predictions
             Authorization: Bearer <access_token>
             Content-Type: application/json
            
             {
               "leagueId": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
               "bonusQuestionId": "4fb96f75-6818-5673-c4gd-3d074g77bfb7",
               "answerTeamId": "5gc07h86-7929-6784-d5he-4e185h88cgc8",
               "answerText": null
             }
             ```

  <b>Example Request (Text answer):</b>

```
             POST /api/bonus-predictions
             Authorization: Bearer <access_token>
             Content-Type: application/json
            
             {
               "leagueId": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
               "bonusQuestionId": "4fb96f75-6818-5673-c4gd-3d074g77bfb7",
               "answerTeamId": null,
               "answerText": "Kylian Mbappe"
             }
             ```

  <b>Example Response:</b>

```
             {
               "isSuccess": true,
               "data": "6hd18i97-8030-7895-e6if-5f296i99dhd9",
               "error": null
             }
             ```

> Body parameter

```json
{
  "leagueId": "58549e12-c6e6-4e03-99d1-6e916f71ce9a",
  "bonusQuestionId": "a0b61934-6fef-4d97-866d-54f4b60aee83",
  "answerTeamId": "ab2250dd-c194-4fab-a78b-360f3b350150",
  "answerText": "string"
}
```

<h3 id="post__api_bonus-predictions-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[SubmitBonusPredictionRequest](#schemasubmitbonuspredictionrequest)|false|The bonus prediction details|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": "808ac6e4-93ed-4040-85a5-6c71a2444e90"
}
```

<h3 id="post__api_bonus-predictions-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Bonus prediction submitted successfully|[GuidResult](#schemaguidresult)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Question already resolved or invalid answer type|[ErrorResponse](#schemaerrorresponse)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|JWT token is missing or invalid|[ErrorResponse](#schemaerrorresponse)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|User is not a member of the league|[ErrorResponse](#schemaerrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|League or bonus question not found|[ErrorResponse](#schemaerrorresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

## get__api_bonus-predictions

> Code samples

```shell
# You can also use wget
curl -X GET /api/bonus-predictions \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET /api/bonus-predictions HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/bonus-predictions',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get '/api/bonus-predictions',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('/api/bonus-predictions', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/api/bonus-predictions', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/bonus-predictions");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/bonus-predictions", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/bonus-predictions`

*Retrieves the current user's bonus predictions for a league.*

  <b>Auth:</b> JWT Bearer token required

  <b>Example Request:</b>

```
             GET /api/bonus-predictions?leagueId=3fa85f64-5717-4562-b3fc-2c963f66afa6
             Authorization: Bearer <access_token>
             ```

  <b>Example Response:</b>

```
             {
               "isSuccess": true,
               "data": [
                 {
                   "id": "...",
                   "bonusQuestionId": "...",
                   "question": "Who will win the World Cup?",
                   "questionType": "Winner",
                   "answerTeamId": "...",
                   "answerTeamName": "Brazil",
                   "answerText": null,
                   "points": 10,
                   "isCorrect": true,
                   "isResolved": true
                 },
                 {
                   "id": "...",
                   "bonusQuestionId": "...",
                   "question": "Who will be the top scorer?",
                   "questionType": "TopScorer",
                   "answerTeamId": null,
                   "answerTeamName": null,
                   "answerText": "Kylian Mbappe",
                   "points": null,
                   "isCorrect": null,
                   "isResolved": false
                 }
               ],
               "error": null
             }
             ```

<h3 id="get__api_bonus-predictions-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|leagueId|query|string(uuid)|false|The league ID to get bonus predictions for|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "userId": "2c4a230c-5085-4924-a3e1-25fb4fc5965b",
      "leagueId": "58549e12-c6e6-4e03-99d1-6e916f71ce9a",
      "bonusQuestionId": "a0b61934-6fef-4d97-866d-54f4b60aee83",
      "answerTeamId": "ab2250dd-c194-4fab-a78b-360f3b350150",
      "answerText": "string",
      "createdAt": "2019-08-24T14:15:22Z"
    }
  ]
}
```

<h3 id="get__api_bonus-predictions-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Returns the user's bonus predictions|[BonusPredictionDtoListResult](#schemabonuspredictiondtolistresult)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|JWT token is missing or invalid|[ErrorResponse](#schemaerrorresponse)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|User is not a member of the league|[ErrorResponse](#schemaerrorresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

<h1 id="tippr-api-bonusquestion">BonusQuestion</h1>

## get__api_bonus-questions

> Code samples

```shell
# You can also use wget
curl -X GET /api/bonus-questions \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET /api/bonus-questions HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/bonus-questions',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get '/api/bonus-questions',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('/api/bonus-questions', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/api/bonus-questions', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/bonus-questions");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/bonus-questions", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/bonus-questions`

*Retrieves all bonus questions for a tournament.*

  <b>Auth:</b> JWT Bearer token required

  <b>Example Request:</b>

```
             GET /api/bonus-questions?tournamentId=3fa85f64-5717-4562-b3fc-2c963f66afa6
             Authorization: Bearer <access_token>
             ```

  <b>Example Response:</b>

```
             {
               "isSuccess": true,
               "data": [
                 {
                   "id": "...",
                   "tournamentId": "...",
                   "questionType": "Winner",
                   "question": "Who will win the World Cup?",
                   "points": 10,
                   "isResolved": false,
                   "answerTeamId": null,
                   "answerText": null
                 },
                 {
                   "id": "...",
                   "tournamentId": "...",
                   "questionType": "TopScorer",
                   "question": "Who will be the top scorer?",
                   "points": 5,
                   "isResolved": false,
                   "answerTeamId": null,
                   "answerText": null
                 }
               ],
               "error": null
             }
             ```

<h3 id="get__api_bonus-questions-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|tournamentId|query|string(uuid)|false|The tournament ID to get questions for|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "tournamentId": "4a951104-9f98-4996-b388-a0ef2c00bb2a",
      "questionType": 0,
      "question": "string",
      "points": 0,
      "isResolved": true,
      "answerTeamId": "ab2250dd-c194-4fab-a78b-360f3b350150",
      "answerText": "string"
    }
  ]
}
```

<h3 id="get__api_bonus-questions-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Returns the list of bonus questions|[BonusQuestionDtoIReadOnlyListResult](#schemabonusquestiondtoireadonlylistresult)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|JWT token is missing or invalid|[ErrorResponse](#schemaerrorresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

## post__api_bonus-questions

> Code samples

```shell
# You can also use wget
curl -X POST /api/bonus-questions \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST /api/bonus-questions HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```javascript
const inputBody = '{
  "tournamentId": "4a951104-9f98-4996-b388-a0ef2c00bb2a",
  "questionType": 0,
  "question": "string",
  "points": 0
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/bonus-questions',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post '/api/bonus-questions',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('/api/bonus-questions', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/api/bonus-questions', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/bonus-questions");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/api/bonus-questions", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api/bonus-questions`

*Creates a new bonus question for a tournament (Admin only).*

  <b>Auth:</b> JWT Bearer token required (Admin role)

  <b>Example Request:</b>

```
             POST /api/bonus-questions
             Authorization: Bearer <access_token>
             Content-Type: application/json
            
             {
               "tournamentId": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
               "questionType": "Winner",
               "question": "Who will win the World Cup 2026?",
               "points": 10
             }
             ```

  <b>Example Response:</b>

```
             {
               "isSuccess": true,
               "data": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
               "error": null
             }
             ```

> Body parameter

```json
{
  "tournamentId": "4a951104-9f98-4996-b388-a0ef2c00bb2a",
  "questionType": 0,
  "question": "string",
  "points": 0
}
```

<h3 id="post__api_bonus-questions-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[CreateBonusQuestionRequest](#schemacreatebonusquestionrequest)|false|The bonus question details|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": "808ac6e4-93ed-4040-85a5-6c71a2444e90"
}
```

<h3 id="post__api_bonus-questions-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Returns the ID of the created bonus question|[GuidResult](#schemaguidresult)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Validation error (invalid question type or points)|[ErrorResponse](#schemaerrorresponse)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|JWT token is missing or invalid|[ErrorResponse](#schemaerrorresponse)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|User does not have Admin role|[ErrorResponse](#schemaerrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Tournament not found|[ErrorResponse](#schemaerrorresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

## put__api_bonus-questions_{id}_resolve

> Code samples

```shell
# You can also use wget
curl -X PUT /api/bonus-questions/{id}/resolve \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
PUT /api/bonus-questions/{id}/resolve HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```javascript
const inputBody = '{
  "answerTeamId": "ab2250dd-c194-4fab-a78b-360f3b350150",
  "answerText": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/bonus-questions/{id}/resolve',
{
  method: 'PUT',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.put '/api/bonus-questions/{id}/resolve',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.put('/api/bonus-questions/{id}/resolve', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('PUT','/api/bonus-questions/{id}/resolve', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/bonus-questions/{id}/resolve");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "/api/bonus-questions/{id}/resolve", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /api/bonus-questions/{id}/resolve`

*Resolves a bonus question with the correct answer and awards points (Admin only).*

  <b>Auth:</b> JWT Bearer token required (Admin role)

  <b>Side Effects:</b>

<list type="bullet">
  <item>
    <description>Marks the question as resolved with the correct answer</description>
  </item>
  <item>
    <description>Awards points to all users who predicted correctly</description>
  </item>
  <item>
    <description>Updates league standings for affected leagues</description>
  </item>
</list>

  <b>Example Request (Team answer):</b>

```
             PUT /api/bonus-questions/3fa85f64-5717-4562-b3fc-2c963f66afa6/resolve
             Authorization: Bearer <access_token>
             Content-Type: application/json
            
             {
               "answerTeamId": "4fb96f75-6818-5673-c4gd-3d074g77bfb7",
               "answerText": null
             }
             ```

  <b>Example Request (Text answer):</b>

```
             PUT /api/bonus-questions/3fa85f64-5717-4562-b3fc-2c963f66afa6/resolve
             Authorization: Bearer <access_token>
             Content-Type: application/json
            
             {
               "answerTeamId": null,
               "answerText": "Kylian Mbappe"
             }
             ```

  <b>Example Response:</b>

```
             {
               "isSuccess": true,
               "data": 15,
               "error": null
             }
             ```

> Body parameter

```json
{
  "answerTeamId": "ab2250dd-c194-4fab-a78b-360f3b350150",
  "answerText": "string"
}
```

<h3 id="put__api_bonus-questions_{id}_resolve-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|The bonus question ID to resolve|
|body|body|[ResolveBonusQuestionRequest](#schemaresolvebonusquestionrequest)|false|The correct answer (team ID or text)|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": 0
}
```

<h3 id="put__api_bonus-questions_{id}_resolve-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Question resolved and points awarded|[Int32Result](#schemaint32result)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Question already resolved or invalid answer|[ErrorResponse](#schemaerrorresponse)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|JWT token is missing or invalid|[ErrorResponse](#schemaerrorresponse)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|User does not have Admin role|[ErrorResponse](#schemaerrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Bonus question not found|[ErrorResponse](#schemaerrorresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

<h1 id="tippr-api-chat">Chat</h1>

## get__api_chat_messages

> Code samples

```shell
# You can also use wget
curl -X GET /api/chat/messages \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET /api/chat/messages HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/chat/messages',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get '/api/chat/messages',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('/api/chat/messages', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/api/chat/messages', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/chat/messages");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/chat/messages", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/chat/messages`

*Retrieves chat messages for a league with cursor-based pagination.*

  <b>Auth:</b> JWT Bearer token required

  <b>Pagination:</b> Uses cursor-based pagination for efficient scrolling through message history

  <b>Example Request (first page):</b>

```
             GET /api/chat/messages?leagueId=3fa85f64-5717-4562-b3fc-2c963f66afa6&take=50
             Authorization: Bearer <access_token>
             ```

  <b>Example Request (next page):</b>

```
             GET /api/chat/messages?leagueId=3fa85f64-5717-4562-b3fc-2c963f66afa6&cursor=2024-01-15T10:30:00Z&take=50
             Authorization: Bearer <access_token>
             ```

  <b>Example Response:</b>

```
             {
               "isSuccess": true,
               "data": {
                 "messages": [
                   {
                     "id": "...",
                     "userId": "...",
                     "displayName": "John Doe",
                     "avatarUrl": "https://...",
                     "content": "Great prediction on the Brazil game!",
                     "createdAt": "2024-01-15T10:30:00Z"
                   },
                   {
                     "id": "...",
                     "userId": "...",
                     "displayName": "Jane Smith",
                     "avatarUrl": "https://...",
                     "content": "Thanks! I had a feeling about that one.",
                     "createdAt": "2024-01-15T10:28:00Z"
                   }
                 ],
                 "nextCursor": "2024-01-15T10:25:00Z",
                 "hasMore": true
               },
               "error": null
             }
             ```

<h3 id="get__api_chat_messages-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|leagueId|query|string(uuid)|false|The league ID to get messages for|
|cursor|query|string(date-time)|false|Optional cursor (CreatedAt timestamp) to fetch messages before this point|
|take|query|integer(int32)|false|Number of messages to retrieve (default: 50, max: 100)|

> Example responses

> 401 Response

```json
{
  "type": "string",
  "title": "string",
  "status": 0,
  "errors": {
    "property1": [
      "string"
    ],
    "property2": [
      "string"
    ]
  }
}
```

<h3 id="get__api_chat_messages-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Returns the chat messages|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|JWT token is missing or invalid|[ErrorResponse](#schemaerrorresponse)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|User is not a member of the league|[ErrorResponse](#schemaerrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|League not found|[ErrorResponse](#schemaerrorresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

<h1 id="tippr-api-leagues">Leagues</h1>

## post__api_leagues

> Code samples

```shell
# You can also use wget
curl -X POST /api/leagues \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST /api/leagues HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```javascript
const inputBody = '{
  "name": "string",
  "description": "string",
  "tournamentId": "4a951104-9f98-4996-b388-a0ef2c00bb2a",
  "isPublic": true,
  "maxMembers": 0,
  "imageUrl": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/leagues',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post '/api/leagues',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('/api/leagues', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/api/leagues', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/leagues");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/api/leagues", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api/leagues`

*Creates a new prediction league.*

  <b>Auth:</b> JWT Bearer token required

  <b>Side Effects:</b>

<list type="bullet">
  <item>
    <description>Creates the league with default scoring settings</description>
  </item>
  <item>
    <description>Automatically adds the creator as owner and first member</description>
  </item>
  <item>
    <description>Generates a unique invite code for private leagues</description>
  </item>
</list>

  <b>Example Request:</b>

```
             POST /api/leagues
             Authorization: Bearer <access_token>
             Content-Type: application/json
            
             {
               "name": "Office Champions",
               "description": "Our office prediction league",
               "tournamentId": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
               "isPublic": false,
               "maxMembers": 50,
               "imageUrl": "https://example.com/league.png"
             }
             ```

  <b>Example Response:</b>

```
             {
               "isSuccess": true,
               "data": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
               "error": null
             }
             ```

> Body parameter

```json
{
  "name": "string",
  "description": "string",
  "tournamentId": "4a951104-9f98-4996-b388-a0ef2c00bb2a",
  "isPublic": true,
  "maxMembers": 0,
  "imageUrl": "string"
}
```

<h3 id="post__api_leagues-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[CreateLeagueRequest](#schemacreateleaguerequest)|false|The league creation details|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": "808ac6e4-93ed-4040-85a5-6c71a2444e90"
}
```

<h3 id="post__api_leagues-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Returns the ID of the created league|[GuidResult](#schemaguidresult)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Validation error (e.g., name too long, invalid tournament)|[ErrorResponse](#schemaerrorresponse)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|JWT token is missing or invalid|[ErrorResponse](#schemaerrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Tournament not found|[ErrorResponse](#schemaerrorresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

## get__api_leagues

> Code samples

```shell
# You can also use wget
curl -X GET /api/leagues \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET /api/leagues HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/leagues',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get '/api/leagues',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('/api/leagues', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/api/leagues', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/leagues");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/leagues", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/leagues`

*Retrieves all leagues the current user is a member of.*

  <b>Auth:</b> JWT Bearer token required

  <b>Example Request:</b>

```
             GET /api/leagues
             Authorization: Bearer <access_token>
             ```

  <b>Example Response:</b>

```
             {
               "isSuccess": true,
               "data": [
                 {
                   "id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
                   "name": "Office Champions",
                   "tournamentName": "FIFA World Cup 2026",
                   "memberCount": 12,
                   "isOwner": true,
                   "imageUrl": "https://example.com/league.png"
                 }
               ],
               "error": null
             }
             ```

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "name": "string",
      "description": "string",
      "tournamentId": "4a951104-9f98-4996-b388-a0ef2c00bb2a",
      "ownerId": "4d206909-730f-409a-88f6-dcfaa8fc28cc",
      "inviteCode": "string",
      "isPublic": true,
      "isGlobal": true,
      "maxMembers": 0,
      "imageUrl": "string",
      "memberCount": 0,
      "myRank": 0,
      "myTotalPoints": 0
    }
  ]
}
```

<h3 id="get__api_leagues-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Returns the user's leagues|[LeagueListDtoIReadOnlyListResult](#schemaleaguelistdtoireadonlylistresult)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|JWT token is missing or invalid|[ErrorResponse](#schemaerrorresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

## get__api_leagues_{id}

> Code samples

```shell
# You can also use wget
curl -X GET /api/leagues/{id} \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET /api/leagues/{id} HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/leagues/{id}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get '/api/leagues/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('/api/leagues/{id}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/api/leagues/{id}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/leagues/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/leagues/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/leagues/{id}`

*Retrieves detailed information for a specific league.*

  <b>Auth:</b> JWT Bearer token required

  <b>Access:</b> User must be a member of the league to view details

  <b>Example Request:</b>

```
             GET /api/leagues/3fa85f64-5717-4562-b3fc-2c963f66afa6
             Authorization: Bearer <access_token>
             ```

  <b>Example Response:</b>

```
             {
               "isSuccess": true,
               "data": {
                 "id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
                 "name": "Office Champions",
                 "description": "Our office prediction league",
                 "tournament": { "id": "...", "name": "FIFA World Cup 2026" },
                 "owner": { "id": "...", "displayName": "John Doe" },
                 "memberCount": 12,
                 "maxMembers": 50,
                 "isPublic": false,
                 "inviteCode": "ABC123",
                 "settings": {
                   "predictionMode": "BeforeKickoff",
                   "deadlineMinutes": 15,
                   "pointsCorrectScore": 3,
                   "pointsCorrectOutcome": 1
                 }
               },
               "error": null
             }
             ```

<h3 id="get__api_leagues_{id}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|The league ID|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "name": "string",
    "description": "string",
    "tournamentId": "4a951104-9f98-4996-b388-a0ef2c00bb2a",
    "ownerId": "4d206909-730f-409a-88f6-dcfaa8fc28cc",
    "inviteCode": "string",
    "isPublic": true,
    "isGlobal": true,
    "maxMembers": 0,
    "imageUrl": "string",
    "settings": {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "leagueId": "58549e12-c6e6-4e03-99d1-6e916f71ce9a",
      "predictionMode": "string",
      "deadlineMinutes": 0,
      "pointsCorrectScore": 0,
      "pointsCorrectOutcome": 0,
      "pointsCorrectGoals": 0,
      "pointsRoundOf16Team": 0,
      "pointsQuarterFinalTeam": 0,
      "pointsSemiFinalTeam": 0,
      "pointsFinalTeam": 0,
      "pointsTopScorer": 0,
      "pointsWinner": 0,
      "pointsMostGoalsGroup": 0,
      "pointsMostConcededGroup": 0,
      "allowLateEdits": true
    },
    "members": [
      {
        "userId": "2c4a230c-5085-4924-a3e1-25fb4fc5965b",
        "username": "string",
        "avatarUrl": "string",
        "joinedAt": "2019-08-24T14:15:22Z",
        "isAdmin": true,
        "isMuted": true
      }
    ],
    "memberCount": 0,
    "myRank": 0,
    "myTotalPoints": 0,
    "isOwner": true
  }
}
```

<h3 id="get__api_leagues_{id}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Returns the league details|[LeagueDtoResult](#schemaleaguedtoresult)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|JWT token is missing or invalid|[ErrorResponse](#schemaerrorresponse)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|User is not a member of this league|[ErrorResponse](#schemaerrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|League not found|[ErrorResponse](#schemaerrorresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

## delete__api_leagues_{id}

> Code samples

```shell
# You can also use wget
curl -X DELETE /api/leagues/{id} \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
DELETE /api/leagues/{id} HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/leagues/{id}',
{
  method: 'DELETE',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.delete '/api/leagues/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.delete('/api/leagues/{id}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('DELETE','/api/leagues/{id}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/leagues/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "/api/leagues/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /api/leagues/{id}`

*Deletes a league and all associated data (Owner only).*

  <b>Auth:</b> JWT Bearer token required (must be league owner)

  <b>Warning:</b> This is a destructive operation and cannot be undone

  <b>Side Effects:</b> Deletes the league, all memberships, predictions, standings, and chat messages

  <b>Example Request:</b>

```
             DELETE /api/leagues/3fa85f64-5717-4562-b3fc-2c963f66afa6
             Authorization: Bearer <access_token>
             ```

  <b>Example Response:</b>

```
             {
               "isSuccess": true,
               "data": true,
               "error": null
             }
             ```

<h3 id="delete__api_leagues_{id}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|The league ID to delete|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": true
}
```

<h3 id="delete__api_leagues_{id}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|League deleted successfully|[BooleanResult](#schemabooleanresult)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|JWT token is missing or invalid|[ErrorResponse](#schemaerrorresponse)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|User is not the owner of this league|[ErrorResponse](#schemaerrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|League not found|[ErrorResponse](#schemaerrorresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

## post__api_leagues_{id}_join

> Code samples

```shell
# You can also use wget
curl -X POST /api/leagues/{id}/join \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST /api/leagues/{id}/join HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```javascript
const inputBody = '{
  "inviteCode": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/leagues/{id}/join',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post '/api/leagues/{id}/join',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('/api/leagues/{id}/join', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/api/leagues/{id}/join', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/leagues/{id}/join");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/api/leagues/{id}/join", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api/leagues/{id}/join`

*Joins an existing league using an optional invite code.*

  <b>Auth:</b> JWT Bearer token required

  <b>Rules:</b>

<list type="bullet">
  <item>
    <description>Public leagues: No invite code required</description>
  </item>
  <item>
    <description>Private leagues: Valid invite code is required</description>
  </item>
  <item>
    <description>Cannot join if already a member</description>
  </item>
  <item>
    <description>Cannot join if league is at max capacity</description>
  </item>
</list>

  <b>Side Effects:</b> Creates a LeagueMember entry for the user

  <b>Example Request:</b>

```
             POST /api/leagues/3fa85f64-5717-4562-b3fc-2c963f66afa6/join
             Authorization: Bearer <access_token>
             Content-Type: application/json
            
             {
               "inviteCode": "ABC123"
             }
             ```

  <b>Example Response:</b>

```
             {
               "isSuccess": true,
               "data": true,
               "error": null
             }
             ```

> Body parameter

```json
{
  "inviteCode": "string"
}
```

<h3 id="post__api_leagues_{id}_join-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|The league ID to join|
|body|body|[JoinLeagueRequest](#schemajoinleaguerequest)|false|The invite code (required for private leagues)|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": true
}
```

<h3 id="post__api_leagues_{id}_join-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successfully joined the league|[BooleanResult](#schemabooleanresult)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid invite code or league is full|[ErrorResponse](#schemaerrorresponse)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|JWT token is missing or invalid|[ErrorResponse](#schemaerrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|League not found|[ErrorResponse](#schemaerrorresponse)|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|User is already a member of this league|[ErrorResponse](#schemaerrorresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

## post__api_leagues_{id}_leave

> Code samples

```shell
# You can also use wget
curl -X POST /api/leagues/{id}/leave \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST /api/leagues/{id}/leave HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/leagues/{id}/leave',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post '/api/leagues/{id}/leave',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('/api/leagues/{id}/leave', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/api/leagues/{id}/leave', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/leagues/{id}/leave");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/api/leagues/{id}/leave", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api/leagues/{id}/leave`

*Leaves a league the current user is a member of.*

  <b>Auth:</b> JWT Bearer token required

  <b>Rules:</b>

<list type="bullet">
  <item>
    <description>League owner cannot leave (must delete or transfer ownership)</description>
  </item>
  <item>
    <description>User must be a member to leave</description>
  </item>
</list>

  <b>Side Effects:</b>

<list type="bullet">
  <item>
    <description>Removes LeagueMember entry</description>
  </item>
  <item>
    <description>User's predictions and standings remain for historical purposes</description>
  </item>
</list>

  <b>Example Request:</b>

```
             POST /api/leagues/3fa85f64-5717-4562-b3fc-2c963f66afa6/leave
             Authorization: Bearer <access_token>
             ```

  <b>Example Response:</b>

```
             {
               "isSuccess": true,
               "data": true,
               "error": null
             }
             ```

<h3 id="post__api_leagues_{id}_leave-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|The league ID to leave|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": true
}
```

<h3 id="post__api_leagues_{id}_leave-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successfully left the league|[BooleanResult](#schemabooleanresult)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Owner cannot leave the league|[ErrorResponse](#schemaerrorresponse)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|JWT token is missing or invalid|[ErrorResponse](#schemaerrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|League not found or user is not a member|[ErrorResponse](#schemaerrorresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

## put__api_leagues_{id}_settings

> Code samples

```shell
# You can also use wget
curl -X PUT /api/leagues/{id}/settings \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
PUT /api/leagues/{id}/settings HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```javascript
const inputBody = '{
  "predictionMode": "string",
  "deadlineMinutes": 0,
  "pointsCorrectScore": 0,
  "pointsCorrectOutcome": 0,
  "pointsCorrectGoals": 0,
  "pointsRoundOf16Team": 0,
  "pointsQuarterFinalTeam": 0,
  "pointsSemiFinalTeam": 0,
  "pointsFinalTeam": 0,
  "pointsTopScorer": 0,
  "pointsWinner": 0,
  "pointsMostGoalsGroup": 0,
  "pointsMostConcededGroup": 0,
  "allowLateEdits": true
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/leagues/{id}/settings',
{
  method: 'PUT',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.put '/api/leagues/{id}/settings',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.put('/api/leagues/{id}/settings', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('PUT','/api/leagues/{id}/settings', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/leagues/{id}/settings");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "/api/leagues/{id}/settings", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /api/leagues/{id}/settings`

*Updates the settings for a league (Owner only).*

  <b>Auth:</b> JWT Bearer token required (must be league owner)

  <b>Partial Update:</b> All fields are optional; only provided values are updated

  <b>Settings:</b>

<list type="bullet">
  <item>
    <description>predictionMode: "BeforeKickoff" or "BeforeMatchday"</description>
  </item>
  <item>
    <description>deadlineMinutes: Minutes before kickoff when predictions lock</description>
  </item>
  <item>
    <description>pointsCorrectScore: Points for exact score prediction (default: 3)</description>
  </item>
  <item>
    <description>pointsCorrectOutcome: Points for correct outcome only (default: 1)</description>
  </item>
  <item>
    <description>pointsCorrectGoals: Points for correct total goals</description>
  </item>
  <item>
    <description>Bonus points for bracket predictions (round of 16, quarters, etc.)</description>
  </item>
</list>

  <b>Example Request:</b>

```
             PUT /api/leagues/3fa85f64-5717-4562-b3fc-2c963f66afa6/settings
             Authorization: Bearer <access_token>
             Content-Type: application/json
            
             {
               "predictionMode": "BeforeKickoff",
               "deadlineMinutes": 15,
               "pointsCorrectScore": 3,
               "pointsCorrectOutcome": 1,
               "allowLateEdits": false
             }
             ```

  <b>Example Response:</b>

```
             {
               "isSuccess": true,
               "data": {
                 "predictionMode": "BeforeKickoff",
                 "deadlineMinutes": 15,
                 "pointsCorrectScore": 3,
                 "pointsCorrectOutcome": 1,
                 "pointsCorrectGoals": 0,
                 "allowLateEdits": false
               },
               "error": null
             }
             ```

> Body parameter

```json
{
  "predictionMode": "string",
  "deadlineMinutes": 0,
  "pointsCorrectScore": 0,
  "pointsCorrectOutcome": 0,
  "pointsCorrectGoals": 0,
  "pointsRoundOf16Team": 0,
  "pointsQuarterFinalTeam": 0,
  "pointsSemiFinalTeam": 0,
  "pointsFinalTeam": 0,
  "pointsTopScorer": 0,
  "pointsWinner": 0,
  "pointsMostGoalsGroup": 0,
  "pointsMostConcededGroup": 0,
  "allowLateEdits": true
}
```

<h3 id="put__api_leagues_{id}_settings-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|The league ID|
|body|body|[UpdateLeagueSettingsRequest](#schemaupdateleaguesettingsrequest)|false|The settings to update|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "leagueId": "58549e12-c6e6-4e03-99d1-6e916f71ce9a",
    "predictionMode": "string",
    "deadlineMinutes": 0,
    "pointsCorrectScore": 0,
    "pointsCorrectOutcome": 0,
    "pointsCorrectGoals": 0,
    "pointsRoundOf16Team": 0,
    "pointsQuarterFinalTeam": 0,
    "pointsSemiFinalTeam": 0,
    "pointsFinalTeam": 0,
    "pointsTopScorer": 0,
    "pointsWinner": 0,
    "pointsMostGoalsGroup": 0,
    "pointsMostConcededGroup": 0,
    "allowLateEdits": true
  }
}
```

<h3 id="put__api_leagues_{id}_settings-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Settings updated successfully|[LeagueSettingsDtoResult](#schemaleaguesettingsdtoresult)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid prediction mode or settings values|[ErrorResponse](#schemaerrorresponse)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|JWT token is missing or invalid|[ErrorResponse](#schemaerrorresponse)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|User is not the owner of this league|[ErrorResponse](#schemaerrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|League not found|[ErrorResponse](#schemaerrorresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

## get__api_leagues_{id}_standings

> Code samples

```shell
# You can also use wget
curl -X GET /api/leagues/{id}/standings \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET /api/leagues/{id}/standings HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/leagues/{id}/standings',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get '/api/leagues/{id}/standings',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('/api/leagues/{id}/standings', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/api/leagues/{id}/standings', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/leagues/{id}/standings");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/leagues/{id}/standings", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/leagues/{id}/standings`

*Retrieves the current standings (leaderboard) for a league.*

  <b>Auth:</b> JWT Bearer token required

  <b>Access:</b> User must be a member of the league

  <b>Example Request:</b>

```
             GET /api/leagues/3fa85f64-5717-4562-b3fc-2c963f66afa6/standings
             Authorization: Bearer <access_token>
             ```

  <b>Example Response:</b>

```
             {
               "isSuccess": true,
               "data": [
                 {
                   "rank": 1,
                   "userId": "...",
                   "displayName": "John Doe",
                   "avatarUrl": "...",
                   "totalPoints": 45,
                   "correctScores": 5,
                   "correctOutcomes": 10,
                   "bonusPoints": 15
                 },
                 {
                   "rank": 2,
                   "userId": "...",
                   "displayName": "Jane Smith",
                   "avatarUrl": "...",
                   "totalPoints": 42,
                   "correctScores": 4,
                   "correctOutcomes": 12,
                   "bonusPoints": 10
                 }
               ],
               "error": null
             }
             ```

<h3 id="get__api_leagues_{id}_standings-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|The league ID|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": [
    {
      "userId": "2c4a230c-5085-4924-a3e1-25fb4fc5965b",
      "username": "string",
      "avatarUrl": "string",
      "rank": 0,
      "previousRank": 0,
      "rankChange": 0,
      "totalPoints": 0,
      "matchPoints": 0,
      "bonusPoints": 0
    }
  ]
}
```

<h3 id="get__api_leagues_{id}_standings-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Returns the standings|[LeagueStandingDtoIReadOnlyListResult](#schemaleaguestandingdtoireadonlylistresult)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|JWT token is missing or invalid|[ErrorResponse](#schemaerrorresponse)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|User is not a member of this league|[ErrorResponse](#schemaerrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|League not found|[ErrorResponse](#schemaerrorresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

## post__api_leagues_{id}_standings_recalculate

> Code samples

```shell
# You can also use wget
curl -X POST /api/leagues/{id}/standings/recalculate \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST /api/leagues/{id}/standings/recalculate HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/leagues/{id}/standings/recalculate',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post '/api/leagues/{id}/standings/recalculate',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('/api/leagues/{id}/standings/recalculate', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/api/leagues/{id}/standings/recalculate', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/leagues/{id}/standings/recalculate");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/api/leagues/{id}/standings/recalculate", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api/leagues/{id}/standings/recalculate`

*Triggers a full recalculation of standings for a league.*

  <b>Auth:</b> JWT Bearer token required

  <b>Use Case:</b> Data integrity checks or after manual corrections to predictions/matches

  <b>Side Effects:</b> Recalculates all points for all members based on current match results

  <b>Example Request:</b>

```
             POST /api/leagues/3fa85f64-5717-4562-b3fc-2c963f66afa6/standings/recalculate
             Authorization: Bearer <access_token>
             ```

  <b>Example Response:</b>

```
             {
               "isSuccess": true,
               "data": true,
               "error": null
             }
             ```

<h3 id="post__api_leagues_{id}_standings_recalculate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|The league ID|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": true
}
```

<h3 id="post__api_leagues_{id}_standings_recalculate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Standings recalculated successfully|[BooleanResult](#schemabooleanresult)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|JWT token is missing or invalid|[ErrorResponse](#schemaerrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|League not found|[ErrorResponse](#schemaerrorresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

<h1 id="tippr-api-matches">Matches</h1>

## get__api_matches

> Code samples

```shell
# You can also use wget
curl -X GET /api/matches \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET /api/matches HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/matches',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get '/api/matches',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('/api/matches', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/api/matches', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/matches");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/matches", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/matches`

*Retrieves matches filtered by tournament ID or date.*

  <b>Auth:</b> JWT Bearer token required

  <b>Filter:</b> Either tournamentId OR date must be provided (not both, not neither)

  <b>Example Request (by tournament):</b>

```
             GET /api/matches?tournamentId=3fa85f64-5717-4562-b3fc-2c963f66afa6
             Authorization: Bearer <access_token>
             ```

  <b>Example Request (by date):</b>

```
             GET /api/matches?date=2026-06-15
             Authorization: Bearer <access_token>
             ```

  <b>Example Response:</b>

```
             {
               "isSuccess": true,
               "data": [
                 {
                   "id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
                   "homeTeam": { "id": "...", "name": "Brazil", "shortName": "BRA" },
                   "awayTeam": { "id": "...", "name": "Germany", "shortName": "GER" },
                   "kickoffTime": "2026-06-15T18:00:00Z",
                   "status": "Scheduled",
                   "homeScore": null,
                   "awayScore": null,
                   "round": "Group A"
                 }
               ],
               "error": null
             }
             ```

<h3 id="get__api_matches-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|tournamentId|query|string(uuid)|false|Filter by tournament ID|
|date|query|string(date)|false|Filter by match date (format: yyyy-MM-dd)|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "tournamentId": "4a951104-9f98-4996-b388-a0ef2c00bb2a",
      "homeTeamId": "fb7b8236-8f4a-4255-b25d-a64d7c4d6968",
      "homeTeamName": "string",
      "homeTeamLogoUrl": "string",
      "homeTeamFifaRank": 0,
      "awayTeamId": "aa1734e3-668a-43b1-918b-ecab48ec02f9",
      "awayTeamName": "string",
      "awayTeamLogoUrl": "string",
      "awayTeamFifaRank": 0,
      "groupName": "string",
      "venue": "string",
      "matchDate": "2019-08-24T14:15:22Z",
      "stage": 0,
      "status": 0,
      "homeScore": 0,
      "awayScore": 0
    }
  ]
}
```

<h3 id="get__api_matches-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Returns the list of matches|[MatchListItemDtoIReadOnlyListResult](#schemamatchlistitemdtoireadonlylistresult)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Neither tournamentId nor date was provided|[ErrorResponse](#schemaerrorresponse)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|JWT token is missing or invalid|[ErrorResponse](#schemaerrorresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

## get__api_matches_{id}

> Code samples

```shell
# You can also use wget
curl -X GET /api/matches/{id} \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET /api/matches/{id} HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/matches/{id}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get '/api/matches/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('/api/matches/{id}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/api/matches/{id}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/matches/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/matches/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/matches/{id}`

*Retrieves detailed information for a specific match.*

  <b>Auth:</b> JWT Bearer token required

  <b>Example Request:</b>

```
             GET /api/matches/3fa85f64-5717-4562-b3fc-2c963f66afa6
             Authorization: Bearer <access_token>
             ```

  <b>Example Response:</b>

```
             {
               "isSuccess": true,
               "data": {
                 "id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
                 "tournamentId": "...",
                 "homeTeam": { "id": "...", "name": "Brazil", "shortName": "BRA", "logoUrl": "..." },
                 "awayTeam": { "id": "...", "name": "Germany", "shortName": "GER", "logoUrl": "..." },
                 "venue": { "id": "...", "name": "Maracana", "city": "Rio de Janeiro" },
                 "kickoffTime": "2026-06-15T18:00:00Z",
                 "status": "Finished",
                 "homeScore": 2,
                 "awayScore": 1,
                 "round": "Final"
               },
               "error": null
             }
             ```

<h3 id="get__api_matches_{id}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|The unique identifier of the match|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "tournamentId": "4a951104-9f98-4996-b388-a0ef2c00bb2a",
    "homeTeamId": "fb7b8236-8f4a-4255-b25d-a64d7c4d6968",
    "homeTeam": {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "tournamentId": "4a951104-9f98-4996-b388-a0ef2c00bb2a",
      "name": "string",
      "displayName": "string",
      "code": "string",
      "logoUrl": "string",
      "groupName": "string",
      "fifaRank": 0,
      "apiFootballId": 0
    },
    "awayTeamId": "aa1734e3-668a-43b1-918b-ecab48ec02f9",
    "awayTeam": {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "tournamentId": "4a951104-9f98-4996-b388-a0ef2c00bb2a",
      "name": "string",
      "displayName": "string",
      "code": "string",
      "logoUrl": "string",
      "groupName": "string",
      "fifaRank": 0,
      "apiFootballId": 0
    },
    "matchDate": "2019-08-24T14:15:22Z",
    "stage": 0,
    "status": 0,
    "homeScore": 0,
    "awayScore": 0,
    "venue": "string",
    "updatedAt": "2019-08-24T14:15:22Z"
  }
}
```

<h3 id="get__api_matches_{id}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Returns the match details|[MatchDetailDtoResult](#schemamatchdetaildtoresult)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|JWT token is missing or invalid|[ErrorResponse](#schemaerrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Match not found|[ErrorResponse](#schemaerrorresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

## get__api_matches_by-team_{teamId}

> Code samples

```shell
# You can also use wget
curl -X GET /api/matches/by-team/{teamId} \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET /api/matches/by-team/{teamId} HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/matches/by-team/{teamId}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get '/api/matches/by-team/{teamId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('/api/matches/by-team/{teamId}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/api/matches/by-team/{teamId}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/matches/by-team/{teamId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/matches/by-team/{teamId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/matches/by-team/{teamId}`

*Retrieves all matches for a specific team (home and away).*

  <b>Auth:</b> JWT Bearer token required

  <b>Example Request:</b>

```
             GET /api/matches/by-team/3fa85f64-5717-4562-b3fc-2c963f66afa6
             Authorization: Bearer <access_token>
             ```

  <b>Example Response:</b>

```
             {
               "isSuccess": true,
               "data": [
                 {
                   "id": "...",
                   "homeTeam": { "id": "...", "name": "Brazil" },
                   "awayTeam": { "id": "...", "name": "Germany" },
                   "kickoffTime": "2026-06-15T18:00:00Z",
                   "status": "Finished",
                   "homeScore": 2,
                   "awayScore": 1
                 }
               ],
               "error": null
             }
             ```

<h3 id="get__api_matches_by-team_{teamid}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|teamId|path|string(uuid)|true|The team ID to get matches for|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "tournamentId": "4a951104-9f98-4996-b388-a0ef2c00bb2a",
      "homeTeamId": "fb7b8236-8f4a-4255-b25d-a64d7c4d6968",
      "homeTeamName": "string",
      "homeTeamLogoUrl": "string",
      "homeTeamFifaRank": 0,
      "awayTeamId": "aa1734e3-668a-43b1-918b-ecab48ec02f9",
      "awayTeamName": "string",
      "awayTeamLogoUrl": "string",
      "awayTeamFifaRank": 0,
      "groupName": "string",
      "venue": "string",
      "matchDate": "2019-08-24T14:15:22Z",
      "stage": 0,
      "status": 0,
      "homeScore": 0,
      "awayScore": 0
    }
  ]
}
```

<h3 id="get__api_matches_by-team_{teamid}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Returns the list of matches|[MatchListItemDtoIReadOnlyListResult](#schemamatchlistitemdtoireadonlylistresult)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|JWT token is missing or invalid|[ErrorResponse](#schemaerrorresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

## put__api_matches_{id}_result

> Code samples

```shell
# You can also use wget
curl -X PUT /api/matches/{id}/result \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
PUT /api/matches/{id}/result HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```javascript
const inputBody = '{
  "homeScore": 0,
  "awayScore": 0,
  "status": 0
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/matches/{id}/result',
{
  method: 'PUT',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.put '/api/matches/{id}/result',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.put('/api/matches/{id}/result', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('PUT','/api/matches/{id}/result', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/matches/{id}/result");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "/api/matches/{id}/result", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /api/matches/{id}/result`

*Updates the result (score and status) of a match (Admin only).*

  <b>Auth:</b> JWT Bearer token required (Admin role)

  <b>Side Effects:</b>

<list type="bullet">
  <item>
    <description>Triggers scoring of predictions when status becomes "Finished"</description>
  </item>
  <item>
    <description>Updates league standings for all leagues with predictions on this match</description>
  </item>
</list>

  <b>Example Request:</b>

```
             PUT /api/matches/3fa85f64-5717-4562-b3fc-2c963f66afa6/result
             Authorization: Bearer <access_token>
             Content-Type: application/json
            
             {
               "homeScore": 2,
               "awayScore": 1,
               "status": "Finished"
             }
             ```

  <b>Example Response:</b>

```
             {
               "isSuccess": true,
               "data": true,
               "error": null
             }
             ```

> Body parameter

```json
{
  "homeScore": 0,
  "awayScore": 0,
  "status": 0
}
```

<h3 id="put__api_matches_{id}_result-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|The match ID to update|
|body|body|[UpdateMatchResultRequest](#schemaupdatematchresultrequest)|false|The new score and status|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": true
}
```

<h3 id="put__api_matches_{id}_result-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Match result updated successfully|[BooleanResult](#schemabooleanresult)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid score or status value|[ErrorResponse](#schemaerrorresponse)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|JWT token is missing or invalid|[ErrorResponse](#schemaerrorresponse)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|User does not have Admin role|[ErrorResponse](#schemaerrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Match not found|[ErrorResponse](#schemaerrorresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

<h1 id="tippr-api-players">Players</h1>

## get__api_players

> Code samples

```shell
# You can also use wget
curl -X GET /api/players \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET /api/players HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/players',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get '/api/players',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('/api/players', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/api/players', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/players");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/players", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/players`

*Retrieves all players for a tournament with optional filtering.*

  <b>Auth:</b> JWT Bearer token required

  <b>Example Request:</b>

```
             GET /api/players?tournamentId=3fa85f64-5717-4562-b3fc-2c963f66afa6&position=Attacker&search=Mbappe
             Authorization: Bearer <access_token>
             ```

  <b>Example Response:</b>

```
             {
               "isSuccess": true,
               "data": [
                 {
                   "id": "...",
                   "name": "Kylian Mbappe",
                   "position": "Attacker",
                   "number": 10,
                   "photoUrl": "https://...",
                   "teamId": "...",
                   "teamName": "France",
                   "teamLogoUrl": "https://..."
                 }
               ],
               "error": null
             }
             ```

<h3 id="get__api_players-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|tournamentId|query|string(uuid)|false|The tournament ID to get players for (required)|
|position|query|string|false|Optional filter by position (Goalkeeper, Defender, Midfielder, Attacker)|
|search|query|string|false|Optional search term to filter by player name|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "teamId": "a4ede8ba-7c0a-4485-8763-cbd9b282fbec",
      "teamName": "string",
      "teamDisplayName": "string",
      "teamLogoUrl": "string",
      "name": "string",
      "firstName": "string",
      "lastName": "string",
      "number": 0,
      "position": "string",
      "photoUrl": "string",
      "dateOfBirth": "2019-08-24T14:15:22Z",
      "age": 0,
      "nationality": "string",
      "height": 0,
      "weight": 0,
      "injured": true,
      "apiFootballId": 0
    }
  ]
}
```

<h3 id="get__api_players-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Returns the list of players|[PlayerWithTeamDtoIReadOnlyListResult](#schemaplayerwithteamdtoireadonlylistresult)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|JWT token is missing or invalid|[ErrorResponse](#schemaerrorresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

## get__api_players_{id}

> Code samples

```shell
# You can also use wget
curl -X GET /api/players/{id} \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET /api/players/{id} HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/players/{id}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get '/api/players/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('/api/players/{id}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/api/players/{id}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/players/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/players/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/players/{id}`

*Retrieves a specific player by their unique identifier.*

  <b>Auth:</b> JWT Bearer token required

  <b>Example Request:</b>

```
             GET /api/players/3fa85f64-5717-4562-b3fc-2c963f66afa6
             Authorization: Bearer <access_token>
             ```

  <b>Example Response:</b>

```
             {
               "isSuccess": true,
               "data": {
                 "id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
                 "name": "Kylian Mbappe",
                 "position": "Attacker",
                 "number": 10,
                 "photoUrl": "https://...",
                 "teamId": "...",
                 "teamName": "France",
                 "teamLogoUrl": "https://..."
               },
               "error": null
             }
             ```

<h3 id="get__api_players_{id}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|The unique identifier of the player|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "teamId": "a4ede8ba-7c0a-4485-8763-cbd9b282fbec",
    "teamName": "string",
    "teamDisplayName": "string",
    "teamLogoUrl": "string",
    "name": "string",
    "firstName": "string",
    "lastName": "string",
    "number": 0,
    "position": "string",
    "photoUrl": "string",
    "dateOfBirth": "2019-08-24T14:15:22Z",
    "age": 0,
    "nationality": "string",
    "height": 0,
    "weight": 0,
    "injured": true,
    "apiFootballId": 0
  }
}
```

<h3 id="get__api_players_{id}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Returns the player|[PlayerWithTeamDtoResult](#schemaplayerwithteamdtoresult)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|JWT token is missing or invalid|[ErrorResponse](#schemaerrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Player not found|[ErrorResponse](#schemaerrorresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

## get__api_players_by-team_{teamId}

> Code samples

```shell
# You can also use wget
curl -X GET /api/players/by-team/{teamId} \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET /api/players/by-team/{teamId} HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/players/by-team/{teamId}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get '/api/players/by-team/{teamId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('/api/players/by-team/{teamId}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/api/players/by-team/{teamId}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/players/by-team/{teamId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/players/by-team/{teamId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/players/by-team/{teamId}`

*Retrieves all players for a specific team.*

  <b>Auth:</b> JWT Bearer token required

  <b>Example Request:</b>

```
             GET /api/players/by-team/3fa85f64-5717-4562-b3fc-2c963f66afa6
             Authorization: Bearer <access_token>
             ```

  <b>Example Response:</b>

```
             {
               "isSuccess": true,
               "data": [
                 {
                   "id": "...",
                   "name": "Kylian Mbappe",
                   "position": "Attacker",
                   "number": 10,
                   "photoUrl": "https://..."
                 },
                 {
                   "id": "...",
                   "name": "Antoine Griezmann",
                   "position": "Attacker",
                   "number": 7,
                   "photoUrl": "https://..."
                 }
               ],
               "error": null
             }
             ```

<h3 id="get__api_players_by-team_{teamid}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|teamId|path|string(uuid)|true|The team ID to get players for|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "teamId": "a4ede8ba-7c0a-4485-8763-cbd9b282fbec",
      "name": "string",
      "firstName": "string",
      "lastName": "string",
      "number": 0,
      "position": "string",
      "photoUrl": "string",
      "dateOfBirth": "2019-08-24T14:15:22Z",
      "age": 0,
      "nationality": "string",
      "height": 0,
      "weight": 0,
      "injured": true,
      "apiFootballId": 0
    }
  ]
}
```

<h3 id="get__api_players_by-team_{teamid}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Returns the list of players|[PlayerDtoIReadOnlyListResult](#schemaplayerdtoireadonlylistresult)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|JWT token is missing or invalid|[ErrorResponse](#schemaerrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Team not found|[ErrorResponse](#schemaerrorresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

<h1 id="tippr-api-predictions">Predictions</h1>

## post__api_predictions

> Code samples

```shell
# You can also use wget
curl -X POST /api/predictions \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST /api/predictions HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```javascript
const inputBody = '{
  "leagueId": "58549e12-c6e6-4e03-99d1-6e916f71ce9a",
  "matchId": "685569fd-95e6-4335-9aa5-fdd22382bd9e",
  "homeScore": 0,
  "awayScore": 0
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/predictions',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post '/api/predictions',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('/api/predictions', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/api/predictions', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/predictions");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/api/predictions", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api/predictions`

*Submits a new prediction for a match within a league.*

  <b>Auth:</b> JWT Bearer token required

  <b>Rules:</b>

<list type="bullet">
  <item>
    <description>User must be a member of the specified league</description>
  </item>
  <item>
    <description>Match must belong to the league's tournament</description>
  </item>
  <item>
    <description>Must be submitted before the league's deadline</description>
  </item>
  <item>
    <description>Cannot create duplicate predictions (use PUT to update)</description>
  </item>
</list>

  <b>Side Effects:</b> Creates a Prediction record; points calculated when match finishes

  <b>Example Request:</b>

```
             POST /api/predictions
             Authorization: Bearer <access_token>
             Content-Type: application/json
            
             {
               "leagueId": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
               "matchId": "4fb96f75-6818-5673-c4gd-3d074g77bfb7",
               "homeScore": 2,
               "awayScore": 1
             }
             ```

  <b>Example Response:</b>

```
             {
               "isSuccess": true,
               "data": "5gc07h86-7929-6784-d5he-4e185h88cgc8",
               "error": null
             }
             ```

> Body parameter

```json
{
  "leagueId": "58549e12-c6e6-4e03-99d1-6e916f71ce9a",
  "matchId": "685569fd-95e6-4335-9aa5-fdd22382bd9e",
  "homeScore": 0,
  "awayScore": 0
}
```

<h3 id="post__api_predictions-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[SubmitPredictionRequest](#schemasubmitpredictionrequest)|false|The prediction details|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": "808ac6e4-93ed-4040-85a5-6c71a2444e90"
}
```

<h3 id="post__api_predictions-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Prediction created successfully|[GuidResult](#schemaguidresult)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Deadline has passed or validation error|[ErrorResponse](#schemaerrorresponse)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|JWT token is missing or invalid|[ErrorResponse](#schemaerrorresponse)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|User is not a member of the league|[ErrorResponse](#schemaerrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|League or match not found|[ErrorResponse](#schemaerrorresponse)|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|Prediction already exists for this match|[ErrorResponse](#schemaerrorresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

## get__api_predictions

> Code samples

```shell
# You can also use wget
curl -X GET /api/predictions \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET /api/predictions HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/predictions',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get '/api/predictions',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('/api/predictions', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/api/predictions', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/predictions");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/predictions", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/predictions`

*Retrieves all predictions for the current user in a specific league.*

  <b>Auth:</b> JWT Bearer token required

  <b>Example Request:</b>

```
             GET /api/predictions?leagueId=3fa85f64-5717-4562-b3fc-2c963f66afa6
             Authorization: Bearer <access_token>
             ```

  <b>Example Response:</b>

```
             {
               "isSuccess": true,
               "data": [
                 {
                   "id": "...",
                   "matchId": "...",
                   "homeTeam": "Brazil",
                   "awayTeam": "Germany",
                   "homeScore": 2,
                   "awayScore": 1,
                   "points": 3,
                   "isCorrectScore": true,
                   "isCorrectOutcome": true,
                   "matchStatus": "Finished",
                   "actualHomeScore": 2,
                   "actualAwayScore": 1
                 }
               ],
               "error": null
             }
             ```

<h3 id="get__api_predictions-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|leagueId|query|string(uuid)|false|The league ID to get predictions for|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "userId": "2c4a230c-5085-4924-a3e1-25fb4fc5965b",
      "leagueId": "58549e12-c6e6-4e03-99d1-6e916f71ce9a",
      "matchId": "685569fd-95e6-4335-9aa5-fdd22382bd9e",
      "homeScore": 0,
      "awayScore": 0,
      "pointsEarned": 0,
      "createdAt": "2019-08-24T14:15:22Z",
      "updatedAt": "2019-08-24T14:15:22Z"
    }
  ]
}
```

<h3 id="get__api_predictions-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Returns the user's predictions|[PredictionDtoListResult](#schemapredictiondtolistresult)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|JWT token is missing or invalid|[ErrorResponse](#schemaerrorresponse)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|User is not a member of the league|[ErrorResponse](#schemaerrorresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

## post__api_predictions_bulk

> Code samples

```shell
# You can also use wget
curl -X POST /api/predictions/bulk \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST /api/predictions/bulk HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```javascript
const inputBody = '{
  "leagueId": "58549e12-c6e6-4e03-99d1-6e916f71ce9a",
  "predictions": [
    {
      "matchId": "685569fd-95e6-4335-9aa5-fdd22382bd9e",
      "homeScore": 0,
      "awayScore": 0
    }
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/predictions/bulk',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post '/api/predictions/bulk',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('/api/predictions/bulk', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/api/predictions/bulk', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/predictions/bulk");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/api/predictions/bulk", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api/predictions/bulk`

*Submits multiple predictions at once for a league.*

  <b>Auth:</b> JWT Bearer token required

  <b>Behavior:</b>

<list type="bullet">
  <item>
    <description>Creates new predictions or updates existing ones</description>
  </item>
  <item>
    <description>Processes all predictions in a single transaction</description>
  </item>
  <item>
    <description>Returns count of created, updated, and failed predictions</description>
  </item>
  <item>
    <description>Individual failures do not roll back successful predictions</description>
  </item>
</list>

  <b>Example Request:</b>

```
             POST /api/predictions/bulk
             Authorization: Bearer <access_token>
             Content-Type: application/json
            
             {
               "leagueId": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
               "predictions": [
                 { "matchId": "...", "homeScore": 2, "awayScore": 1 },
                 { "matchId": "...", "homeScore": 0, "awayScore": 0 },
                 { "matchId": "...", "homeScore": 3, "awayScore": 2 }
               ]
             }
             ```

  <b>Example Response:</b>

```
             {
               "isSuccess": true,
               "data": {
                 "created": 2,
                 "updated": 1,
                 "failed": 0,
                 "errors": []
               },
               "error": null
             }
             ```

> Body parameter

```json
{
  "leagueId": "58549e12-c6e6-4e03-99d1-6e916f71ce9a",
  "predictions": [
    {
      "matchId": "685569fd-95e6-4335-9aa5-fdd22382bd9e",
      "homeScore": 0,
      "awayScore": 0
    }
  ]
}
```

<h3 id="post__api_predictions_bulk-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[BulkSubmitPredictionsRequest](#schemabulksubmitpredictionsrequest)|false|The league ID and list of predictions|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": {
    "successCount": 0,
    "failedCount": 0,
    "results": [
      {
        "matchId": "685569fd-95e6-4335-9aa5-fdd22382bd9e",
        "predictionId": "07ef3e55-acee-4631-909a-2d5902a608e6",
        "success": true,
        "errorMessage": "string",
        "errorCode": "string"
      }
    ]
  }
}
```

<h3 id="post__api_predictions_bulk-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Bulk operation completed (check result for individual failures)|[BulkSubmitPredictionsResultResult](#schemabulksubmitpredictionsresultresult)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Validation error in request structure|[ErrorResponse](#schemaerrorresponse)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|JWT token is missing or invalid|[ErrorResponse](#schemaerrorresponse)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|User is not a member of the league|[ErrorResponse](#schemaerrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|League not found|[ErrorResponse](#schemaerrorresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

## put__api_predictions_{id}

> Code samples

```shell
# You can also use wget
curl -X PUT /api/predictions/{id} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
PUT /api/predictions/{id} HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```javascript
const inputBody = '{
  "homeScore": 0,
  "awayScore": 0
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/predictions/{id}',
{
  method: 'PUT',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.put '/api/predictions/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.put('/api/predictions/{id}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('PUT','/api/predictions/{id}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/predictions/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "/api/predictions/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /api/predictions/{id}`

*Updates an existing prediction's score.*

  <b>Auth:</b> JWT Bearer token required

  <b>Rules:</b>

<list type="bullet">
  <item>
    <description>User must own the prediction</description>
  </item>
  <item>
    <description>Must be updated before the league's deadline</description>
  </item>
  <item>
    <description>Cannot update after match has started (unless AllowLateEdits is enabled)</description>
  </item>
</list>

  <b>Example Request:</b>

```
             PUT /api/predictions/3fa85f64-5717-4562-b3fc-2c963f66afa6
             Authorization: Bearer <access_token>
             Content-Type: application/json
            
             {
               "homeScore": 3,
               "awayScore": 1
             }
             ```

  <b>Example Response:</b>

```
             {
               "isSuccess": true,
               "data": true,
               "error": null
             }
             ```

> Body parameter

```json
{
  "homeScore": 0,
  "awayScore": 0
}
```

<h3 id="put__api_predictions_{id}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|The prediction ID to update|
|body|body|[UpdatePredictionRequest](#schemaupdatepredictionrequest)|false|The new score prediction|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": true
}
```

<h3 id="put__api_predictions_{id}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Prediction updated successfully|[BooleanResult](#schemabooleanresult)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Deadline has passed or match already started|[ErrorResponse](#schemaerrorresponse)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|JWT token is missing or invalid|[ErrorResponse](#schemaerrorresponse)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|User does not own this prediction|[ErrorResponse](#schemaerrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Prediction not found|[ErrorResponse](#schemaerrorresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

## get__api_predictions_match_{matchId}

> Code samples

```shell
# You can also use wget
curl -X GET /api/predictions/match/{matchId} \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET /api/predictions/match/{matchId} HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/predictions/match/{matchId}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get '/api/predictions/match/{matchId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('/api/predictions/match/{matchId}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/api/predictions/match/{matchId}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/predictions/match/{matchId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/predictions/match/{matchId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/predictions/match/{matchId}`

*Retrieves the current user's prediction for a specific match in a league.*

  <b>Auth:</b> JWT Bearer token required

  <b>Example Request:</b>

```
             GET /api/predictions/match/3fa85f64-5717-4562-b3fc-2c963f66afa6?leagueId=4fb96f75-6818-5673-c4gd-3d074g77bfb7
             Authorization: Bearer <access_token>
             ```

  <b>Example Response:</b>

```
             {
               "isSuccess": true,
               "data": {
                 "id": "...",
                 "matchId": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
                 "homeScore": 2,
                 "awayScore": 1,
                 "points": null,
                 "matchStatus": "Scheduled"
               },
               "error": null
             }
             ```

<h3 id="get__api_predictions_match_{matchid}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|matchId|path|string(uuid)|true|The match ID|
|leagueId|query|string(uuid)|false|The league ID|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "userId": "2c4a230c-5085-4924-a3e1-25fb4fc5965b",
    "leagueId": "58549e12-c6e6-4e03-99d1-6e916f71ce9a",
    "matchId": "685569fd-95e6-4335-9aa5-fdd22382bd9e",
    "homeScore": 0,
    "awayScore": 0,
    "pointsEarned": 0,
    "createdAt": "2019-08-24T14:15:22Z",
    "updatedAt": "2019-08-24T14:15:22Z"
  }
}
```

<h3 id="get__api_predictions_match_{matchid}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Returns the prediction or null if not found|[PredictionDtoResult](#schemapredictiondtoresult)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|JWT token is missing or invalid|[ErrorResponse](#schemaerrorresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

<h1 id="tippr-api-teams">Teams</h1>

## get__api_teams

> Code samples

```shell
# You can also use wget
curl -X GET /api/teams \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET /api/teams HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/teams',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get '/api/teams',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('/api/teams', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/api/teams', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/teams");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/teams", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/teams`

*Retrieves all teams participating in a specific tournament.*

  <b>Auth:</b> JWT Bearer token required

  <b>Example Request:</b>

```
             GET /api/teams?tournamentId=3fa85f64-5717-4562-b3fc-2c963f66afa6
             Authorization: Bearer <access_token>
             ```

  <b>Example Response:</b>

```
             {
               "isSuccess": true,
               "data": [
                 {
                   "id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
                   "name": "Brazil",
                   "shortName": "BRA",
                   "logoUrl": "https://example.com/brazil.png",
                   "group": "A"
                 },
                 {
                   "id": "4fb96f75-6818-5673-c4gd-3d074g77bfb7",
                   "name": "Germany",
                   "shortName": "GER",
                   "logoUrl": "https://example.com/germany.png",
                   "group": "A"
                 }
               ],
               "error": null
             }
             ```

<h3 id="get__api_teams-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|tournamentId|query|string(uuid)|false|The tournament ID to filter teams by (required)|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "tournamentId": "4a951104-9f98-4996-b388-a0ef2c00bb2a",
      "name": "string",
      "displayName": "string",
      "code": "string",
      "logoUrl": "string",
      "groupName": "string",
      "fifaRank": 0,
      "apiFootballId": 0
    }
  ]
}
```

<h3 id="get__api_teams-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Returns the list of teams|[TeamDtoIReadOnlyListResult](#schemateamdtoireadonlylistresult)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|JWT token is missing or invalid|[ErrorResponse](#schemaerrorresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

## get__api_teams_{id}

> Code samples

```shell
# You can also use wget
curl -X GET /api/teams/{id} \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET /api/teams/{id} HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/teams/{id}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get '/api/teams/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('/api/teams/{id}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/api/teams/{id}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/teams/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/teams/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/teams/{id}`

*Retrieves a specific team by its unique identifier.*

  <b>Auth:</b> JWT Bearer token required

  <b>Example Request:</b>

```
             GET /api/teams/3fa85f64-5717-4562-b3fc-2c963f66afa6
             Authorization: Bearer <access_token>
             ```

  <b>Example Response:</b>

```
             {
               "isSuccess": true,
               "data": {
                 "id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
                 "name": "Brazil",
                 "shortName": "BRA",
                 "logoUrl": "https://example.com/brazil.png",
                 "group": "A"
               },
               "error": null
             }
             ```

<h3 id="get__api_teams_{id}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|The unique identifier of the team|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "tournamentId": "4a951104-9f98-4996-b388-a0ef2c00bb2a",
    "name": "string",
    "displayName": "string",
    "code": "string",
    "logoUrl": "string",
    "groupName": "string",
    "fifaRank": 0,
    "apiFootballId": 0
  }
}
```

<h3 id="get__api_teams_{id}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Returns the team|[TeamDtoResult](#schemateamdtoresult)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|JWT token is missing or invalid|[ErrorResponse](#schemaerrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Team not found|[ErrorResponse](#schemaerrorresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

<h1 id="tippr-api-tournaments">Tournaments</h1>

## get__api_tournaments

> Code samples

```shell
# You can also use wget
curl -X GET /api/tournaments \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET /api/tournaments HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/tournaments',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get '/api/tournaments',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('/api/tournaments', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/api/tournaments', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/tournaments");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/tournaments", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/tournaments`

*Retrieves all tournaments, optionally filtered to only active ones.*

  <b>Auth:</b> JWT Bearer token required

  <b>Example Request:</b>

```
             GET /api/tournaments?onlyActive=true
             Authorization: Bearer <access_token>
             ```

  <b>Example Response:</b>

```
             {
               "isSuccess": true,
               "data": [
                 {
                   "id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
                   "name": "FIFA World Cup 2026",
                   "startDate": "2026-06-11",
                   "endDate": "2026-07-19",
                   "isActive": true,
                   "logoUrl": "https://example.com/wc2026.png"
                 }
               ],
               "error": null
             }
             ```

<h3 id="get__api_tournaments-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|onlyActive|query|boolean|false|If true, returns only tournaments where IsActive = true|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "name": "string",
      "year": 0,
      "type": 0,
      "startDate": "2019-08-24T14:15:22Z",
      "endDate": "2019-08-24T14:15:22Z",
      "country": "string",
      "logoUrl": "string",
      "isActive": true
    }
  ]
}
```

<h3 id="get__api_tournaments-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Returns the list of tournaments|[TournamentDtoIReadOnlyListResult](#schematournamentdtoireadonlylistresult)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|JWT token is missing or invalid|[ErrorResponse](#schemaerrorresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

## post__api_tournaments

> Code samples

```shell
# You can also use wget
curl -X POST /api/tournaments \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST /api/tournaments HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```javascript
const inputBody = '{
  "name": "string",
  "year": 0,
  "type": 0,
  "startDate": "2019-08-24T14:15:22Z",
  "endDate": "2019-08-24T14:15:22Z",
  "country": "string",
  "logoUrl": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/tournaments',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post '/api/tournaments',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('/api/tournaments', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/api/tournaments', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/tournaments");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/api/tournaments", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api/tournaments`

*Creates a new tournament (Admin only).*

  <b>Auth:</b> JWT Bearer token required (Admin role)

  <b>Example Request:</b>

```
             POST /api/tournaments
             Authorization: Bearer <access_token>
             Content-Type: application/json
            
             {
               "name": "FIFA World Cup 2026",
               "startDate": "2026-06-11",
               "endDate": "2026-07-19",
               "isActive": true,
               "logoUrl": "https://example.com/wc2026.png"
             }
             ```

  <b>Example Response:</b>

```
             {
               "isSuccess": true,
               "data": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
               "error": null
             }
             ```

> Body parameter

```json
{
  "name": "string",
  "year": 0,
  "type": 0,
  "startDate": "2019-08-24T14:15:22Z",
  "endDate": "2019-08-24T14:15:22Z",
  "country": "string",
  "logoUrl": "string"
}
```

<h3 id="post__api_tournaments-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[CreateTournamentCommand](#schemacreatetournamentcommand)|false|The tournament creation details|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": "808ac6e4-93ed-4040-85a5-6c71a2444e90"
}
```

<h3 id="post__api_tournaments-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Returns the ID of the created tournament|[GuidResult](#schemaguidresult)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Validation error in request body|[ErrorResponse](#schemaerrorresponse)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|JWT token is missing or invalid|[ErrorResponse](#schemaerrorresponse)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|User does not have Admin role|[ErrorResponse](#schemaerrorresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

## get__api_tournaments_{id}

> Code samples

```shell
# You can also use wget
curl -X GET /api/tournaments/{id} \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET /api/tournaments/{id} HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/tournaments/{id}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get '/api/tournaments/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('/api/tournaments/{id}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/api/tournaments/{id}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/tournaments/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/tournaments/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/tournaments/{id}`

*Retrieves a specific tournament by its unique identifier.*

  <b>Auth:</b> JWT Bearer token required

  <b>Example Request:</b>

```
             GET /api/tournaments/3fa85f64-5717-4562-b3fc-2c963f66afa6
             Authorization: Bearer <access_token>
             ```

  <b>Example Response:</b>

```
             {
               "isSuccess": true,
               "data": {
                 "id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
                 "name": "FIFA World Cup 2026",
                 "startDate": "2026-06-11",
                 "endDate": "2026-07-19",
                 "isActive": true,
                 "logoUrl": "https://example.com/wc2026.png"
               },
               "error": null
             }
             ```

<h3 id="get__api_tournaments_{id}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|The unique identifier of the tournament|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "name": "string",
    "year": 0,
    "type": 0,
    "startDate": "2019-08-24T14:15:22Z",
    "endDate": "2019-08-24T14:15:22Z",
    "country": "string",
    "logoUrl": "string",
    "isActive": true
  }
}
```

<h3 id="get__api_tournaments_{id}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Returns the tournament|[TournamentDtoResult](#schematournamentdtoresult)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|JWT token is missing or invalid|[ErrorResponse](#schemaerrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Tournament not found|[ErrorResponse](#schemaerrorresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

<h1 id="tippr-api-users">Users</h1>

## post__api_users_avatar

> Code samples

```shell
# You can also use wget
curl -X POST /api/users/avatar \
  -H 'Content-Type: multipart/form-data' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST /api/users/avatar HTTP/1.1

Content-Type: multipart/form-data
Accept: application/json

```

```javascript
const inputBody = '{
  "File": "string"
}';
const headers = {
  'Content-Type':'multipart/form-data',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/users/avatar',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'multipart/form-data',
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post '/api/users/avatar',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'multipart/form-data',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('/api/users/avatar', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'multipart/form-data',
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/api/users/avatar', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/users/avatar");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"multipart/form-data"},
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/api/users/avatar", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api/users/avatar`

*Uploads a new avatar image for the current user.*

  <b>Auth:</b> JWT Bearer token required

  <b>Content-Type:</b> multipart/form-data

  <b>Max File Size:</b> 2 MB

  <b>Supported Formats:</b> JPEG, PNG, GIF, WebP

  <b>Side Effects:</b> Uploads image to Supabase Storage and updates user's AvatarUrl

  <b>Example Request:</b>

```
             POST /api/users/avatar
             Authorization: Bearer <access_token>
             Content-Type: multipart/form-data
            
             file: [binary image data]
             ```

  <b>Example Response:</b>

```
             {
               "isSuccess": true,
               "data": "https://storage.supabase.co/avatars/user-id/avatar.jpg",
               "error": null
             }
             ```

> Body parameter

```yaml
File: string

```

<h3 id="post__api_users_avatar-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|false|none|
|» File|body|string(binary)|false|none|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": "string"
}
```

<h3 id="post__api_users_avatar-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Returns the URL of the uploaded avatar|[StringResult](#schemastringresult)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|File is missing, too large, or invalid format|[ErrorResponse](#schemaerrorresponse)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|JWT token is missing or invalid|[ErrorResponse](#schemaerrorresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

## patch__api_users_profile

> Code samples

```shell
# You can also use wget
curl -X PATCH /api/users/profile \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
PATCH /api/users/profile HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```javascript
const inputBody = '{
  "displayName": "string",
  "bio": "string",
  "favoriteTeamId": "d03f4e26-a6b7-4158-9c97-87bb7dc42e8b"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/users/profile',
{
  method: 'PATCH',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.patch '/api/users/profile',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.patch('/api/users/profile', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('PATCH','/api/users/profile', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/users/profile");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PATCH");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PATCH", "/api/users/profile", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PATCH /api/users/profile`

*Updates the current user's profile information.*

  <b>Auth:</b> JWT Bearer token required

  <b>Partial Update:</b> Only provided fields are updated; null/omitted fields are ignored

  <b>Field Constraints:</b>

<list type="bullet">
  <item>
    <description>displayName: max 100 characters</description>
  </item>
  <item>
    <description>bio: max 500 characters (send empty string to clear)</description>
  </item>
  <item>
    <description>favoriteTeamId: must reference an existing team</description>
  </item>
</list>

  <b>Example Request:</b>

```
             PATCH /api/users/profile
             Authorization: Bearer <access_token>
             Content-Type: application/json
            
             {
               "displayName": "John Doe",
               "bio": "Football enthusiast since 1990",
               "favoriteTeamId": "3fa85f64-5717-4562-b3fc-2c963f66afa6"
             }
             ```

  <b>Example Response:</b>

```
             {
               "isSuccess": true,
               "data": {
                 "id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
                 "username": "johndoe",
                 "displayName": "John Doe",
                 "avatarUrl": "https://storage.example.com/avatars/user.jpg",
                 "bio": "Football enthusiast since 1990",
                 "favoriteTeamId": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
                 "favoriteTeamName": "Manchester United",
                 "createdAt": "2024-01-01T00:00:00Z",
                 "updatedAt": "2024-01-15T10:30:00Z"
               },
               "error": null
             }
             ```

> Body parameter

```json
{
  "displayName": "string",
  "bio": "string",
  "favoriteTeamId": "d03f4e26-a6b7-4158-9c97-87bb7dc42e8b"
}
```

<h3 id="patch__api_users_profile-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[UpdateProfileRequest](#schemaupdateprofilerequest)|false|The profile fields to update|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "username": "string",
    "displayName": "string",
    "avatarUrl": "string",
    "bio": "string",
    "favoriteTeamId": "d03f4e26-a6b7-4158-9c97-87bb7dc42e8b",
    "favoriteTeamName": "string",
    "createdAt": "2019-08-24T14:15:22Z",
    "updatedAt": "2019-08-24T14:15:22Z"
  }
}
```

<h3 id="patch__api_users_profile-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Returns the updated user profile|[UserProfileDtoResult](#schemauserprofiledtoresult)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Validation error (e.g., field too long)|[ErrorResponse](#schemaerrorresponse)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|JWT token is missing or invalid|[ErrorResponse](#schemaerrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Referenced team does not exist|[ErrorResponse](#schemaerrorresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

<h1 id="tippr-api-venues">Venues</h1>

## get__api_venues

> Code samples

```shell
# You can also use wget
curl -X GET /api/venues \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET /api/venues HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/venues',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get '/api/venues',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('/api/venues', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/api/venues', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/venues");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/venues", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/venues`

*Retrieves all venues, optionally filtered by tournament.*

  <b>Auth:</b> JWT Bearer token required

  <b>Example Request:</b>

```
             GET /api/venues?tournamentId=3fa85f64-5717-4562-b3fc-2c963f66afa6
             Authorization: Bearer <access_token>
             ```

  <b>Example Response:</b>

```
             {
               "isSuccess": true,
               "data": [
                 {
                   "id": "...",
                   "name": "Maracana",
                   "city": "Rio de Janeiro",
                   "country": "Brazil",
                   "capacity": 78838,
                   "imageUrl": "https://..."
                 },
                 {
                   "id": "...",
                   "name": "Wembley Stadium",
                   "city": "London",
                   "country": "England",
                   "capacity": 90000,
                   "imageUrl": "https://..."
                 }
               ],
               "error": null
             }
             ```

<h3 id="get__api_venues-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|tournamentId|query|string(uuid)|false|Optional tournament ID to filter venues by|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "name": "string",
      "address": "string",
      "city": "string",
      "capacity": 0,
      "surface": "string",
      "imageUrl": "string",
      "apiFootballId": 0
    }
  ]
}
```

<h3 id="get__api_venues-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Returns the list of venues|[VenueDtoIReadOnlyListResult](#schemavenuedtoireadonlylistresult)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|JWT token is missing or invalid|[ErrorResponse](#schemaerrorresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

## get__api_venues_{id}

> Code samples

```shell
# You can also use wget
curl -X GET /api/venues/{id} \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET /api/venues/{id} HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/venues/{id}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get '/api/venues/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('/api/venues/{id}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/api/venues/{id}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/venues/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/venues/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/venues/{id}`

*Retrieves a specific venue by its unique identifier.*

  <b>Auth:</b> JWT Bearer token required

  <b>Example Request:</b>

```
             GET /api/venues/3fa85f64-5717-4562-b3fc-2c963f66afa6
             Authorization: Bearer <access_token>
             ```

  <b>Example Response:</b>

```
             {
               "isSuccess": true,
               "data": {
                 "id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
                 "name": "Maracana",
                 "city": "Rio de Janeiro",
                 "country": "Brazil",
                 "capacity": 78838,
                 "imageUrl": "https://..."
               },
               "error": null
             }
             ```

<h3 id="get__api_venues_{id}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|The unique identifier of the venue|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "name": "string",
    "address": "string",
    "city": "string",
    "capacity": 0,
    "surface": "string",
    "imageUrl": "string",
    "apiFootballId": 0
  }
}
```

<h3 id="get__api_venues_{id}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Returns the venue|[VenueDtoResult](#schemavenuedtoresult)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|JWT token is missing or invalid|[ErrorResponse](#schemaerrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Venue not found|[ErrorResponse](#schemaerrorresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

## get__api_venues_by-team_{teamId}

> Code samples

```shell
# You can also use wget
curl -X GET /api/venues/by-team/{teamId} \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET /api/venues/by-team/{teamId} HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/venues/by-team/{teamId}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get '/api/venues/by-team/{teamId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('/api/venues/by-team/{teamId}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/api/venues/by-team/{teamId}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/venues/by-team/{teamId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/venues/by-team/{teamId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/venues/by-team/{teamId}`

*Retrieves the home venue for a specific team.*

  <b>Auth:</b> JWT Bearer token required

  <b>Example Request:</b>

```
             GET /api/venues/by-team/3fa85f64-5717-4562-b3fc-2c963f66afa6
             Authorization: Bearer <access_token>
             ```

  <b>Example Response:</b>

```
             {
               "isSuccess": true,
               "data": {
                 "id": "...",
                 "name": "Maracana",
                 "city": "Rio de Janeiro",
                 "country": "Brazil",
                 "capacity": 78838,
                 "imageUrl": "https://..."
               },
               "error": null
             }
             ```

<h3 id="get__api_venues_by-team_{teamid}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|teamId|path|string(uuid)|true|The team ID to get the home venue for|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "name": "string",
    "address": "string",
    "city": "string",
    "capacity": 0,
    "surface": "string",
    "imageUrl": "string",
    "apiFootballId": 0
  }
}
```

<h3 id="get__api_venues_by-team_{teamid}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Returns the venue|[VenueDtoResult](#schemavenuedtoresult)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|JWT token is missing or invalid|[ErrorResponse](#schemaerrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Team or venue not found|[ErrorResponse](#schemaerrorresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

## get__api_venues_by-match_{matchId}

> Code samples

```shell
# You can also use wget
curl -X GET /api/venues/by-match/{matchId} \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET /api/venues/by-match/{matchId} HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/venues/by-match/{matchId}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get '/api/venues/by-match/{matchId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('/api/venues/by-match/{matchId}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/api/venues/by-match/{matchId}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/api/venues/by-match/{matchId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/venues/by-match/{matchId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/venues/by-match/{matchId}`

*Retrieves the venue for a specific match.*

  <b>Auth:</b> JWT Bearer token required

  <b>Example Request:</b>

```
             GET /api/venues/by-match/3fa85f64-5717-4562-b3fc-2c963f66afa6
             Authorization: Bearer <access_token>
             ```

  <b>Example Response:</b>

```
             {
               "isSuccess": true,
               "data": {
                 "id": "...",
                 "name": "Wembley Stadium",
                 "city": "London",
                 "country": "England",
                 "capacity": 90000,
                 "imageUrl": "https://..."
               },
               "error": null
             }
             ```

<h3 id="get__api_venues_by-match_{matchid}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|matchId|path|string(uuid)|true|The match ID to get the venue for|

> Example responses

> 200 Response

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "name": "string",
    "address": "string",
    "city": "string",
    "capacity": 0,
    "surface": "string",
    "imageUrl": "string",
    "apiFootballId": 0
  }
}
```

<h3 id="get__api_venues_by-match_{matchid}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Returns the venue|[VenueDtoResult](#schemavenuedtoresult)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|JWT token is missing or invalid|[ErrorResponse](#schemaerrorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Match or venue not found|[ErrorResponse](#schemaerrorresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

# Schemas

<h2 id="tocS_AddLeagueMemberRequest">AddLeagueMemberRequest</h2>
<!-- backwards compatibility -->
<a id="schemaaddleaguememberrequest"></a>
<a id="schema_AddLeagueMemberRequest"></a>
<a id="tocSaddleaguememberrequest"></a>
<a id="tocsaddleaguememberrequest"></a>

```json
{
  "userId": "2c4a230c-5085-4924-a3e1-25fb4fc5965b",
  "isAdmin": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|userId|string(uuid)|false|none|none|
|isAdmin|boolean|false|none|none|

<h2 id="tocS_AdminBonusPredictionListDto">AdminBonusPredictionListDto</h2>
<!-- backwards compatibility -->
<a id="schemaadminbonuspredictionlistdto"></a>
<a id="schema_AdminBonusPredictionListDto"></a>
<a id="tocSadminbonuspredictionlistdto"></a>
<a id="tocsadminbonuspredictionlistdto"></a>

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "userId": "2c4a230c-5085-4924-a3e1-25fb4fc5965b",
  "username": "string",
  "bonusQuestionId": "a0b61934-6fef-4d97-866d-54f4b60aee83",
  "leagueId": "58549e12-c6e6-4e03-99d1-6e916f71ce9a",
  "leagueName": "string",
  "answerTeamId": "ab2250dd-c194-4fab-a78b-360f3b350150",
  "answerTeamName": "string",
  "answerText": "string",
  "pointsEarned": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|false|none|none|
|userId|string(uuid)|false|none|none|
|username|string¦null|false|none|none|
|bonusQuestionId|string(uuid)|false|none|none|
|leagueId|string(uuid)|false|none|none|
|leagueName|string¦null|false|none|none|
|answerTeamId|string(uuid)¦null|false|none|none|
|answerTeamName|string¦null|false|none|none|
|answerText|string¦null|false|none|none|
|pointsEarned|integer(int32)¦null|false|none|none|

<h2 id="tocS_AdminBonusPredictionListDtoPagedResult">AdminBonusPredictionListDtoPagedResult</h2>
<!-- backwards compatibility -->
<a id="schemaadminbonuspredictionlistdtopagedresult"></a>
<a id="schema_AdminBonusPredictionListDtoPagedResult"></a>
<a id="tocSadminbonuspredictionlistdtopagedresult"></a>
<a id="tocsadminbonuspredictionlistdtopagedresult"></a>

```json
{
  "items": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "userId": "2c4a230c-5085-4924-a3e1-25fb4fc5965b",
      "username": "string",
      "bonusQuestionId": "a0b61934-6fef-4d97-866d-54f4b60aee83",
      "leagueId": "58549e12-c6e6-4e03-99d1-6e916f71ce9a",
      "leagueName": "string",
      "answerTeamId": "ab2250dd-c194-4fab-a78b-360f3b350150",
      "answerTeamName": "string",
      "answerText": "string",
      "pointsEarned": 0
    }
  ],
  "totalCount": 0,
  "page": 0,
  "pageSize": 0,
  "totalPages": 0,
  "hasNextPage": true,
  "hasPreviousPage": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|items|[[AdminBonusPredictionListDto](#schemaadminbonuspredictionlistdto)]¦null|false|none|none|
|totalCount|integer(int32)|false|none|none|
|page|integer(int32)|false|none|none|
|pageSize|integer(int32)|false|none|none|
|totalPages|integer(int32)|false|read-only|none|
|hasNextPage|boolean|false|read-only|none|
|hasPreviousPage|boolean|false|read-only|none|

<h2 id="tocS_AdminBonusPredictionListDtoPagedResultResult">AdminBonusPredictionListDtoPagedResultResult</h2>
<!-- backwards compatibility -->
<a id="schemaadminbonuspredictionlistdtopagedresultresult"></a>
<a id="schema_AdminBonusPredictionListDtoPagedResultResult"></a>
<a id="tocSadminbonuspredictionlistdtopagedresultresult"></a>
<a id="tocsadminbonuspredictionlistdtopagedresultresult"></a>

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": {
    "items": [
      {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "userId": "2c4a230c-5085-4924-a3e1-25fb4fc5965b",
        "username": "string",
        "bonusQuestionId": "a0b61934-6fef-4d97-866d-54f4b60aee83",
        "leagueId": "58549e12-c6e6-4e03-99d1-6e916f71ce9a",
        "leagueName": "string",
        "answerTeamId": "ab2250dd-c194-4fab-a78b-360f3b350150",
        "answerTeamName": "string",
        "answerText": "string",
        "pointsEarned": 0
      }
    ],
    "totalCount": 0,
    "page": 0,
    "pageSize": 0,
    "totalPages": 0,
    "hasNextPage": true,
    "hasPreviousPage": true
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|isSuccess|boolean|false|read-only|none|
|error|[Error](#schemaerror)|false|none|none|
|data|[AdminBonusPredictionListDtoPagedResult](#schemaadminbonuspredictionlistdtopagedresult)|false|none|none|

<h2 id="tocS_AdminBonusQuestionDto">AdminBonusQuestionDto</h2>
<!-- backwards compatibility -->
<a id="schemaadminbonusquestiondto"></a>
<a id="schema_AdminBonusQuestionDto"></a>
<a id="tocSadminbonusquestiondto"></a>
<a id="tocsadminbonusquestiondto"></a>

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "tournamentId": "4a951104-9f98-4996-b388-a0ef2c00bb2a",
  "tournamentName": "string",
  "questionType": 0,
  "question": "string",
  "answerTeamId": "ab2250dd-c194-4fab-a78b-360f3b350150",
  "answerTeamName": "string",
  "answerText": "string",
  "isResolved": true,
  "points": 0,
  "createdAt": "2019-08-24T14:15:22Z",
  "updatedAt": "2019-08-24T14:15:22Z",
  "predictionCount": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|false|none|none|
|tournamentId|string(uuid)|false|none|none|
|tournamentName|string¦null|false|none|none|
|questionType|[BonusQuestionType](#schemabonusquestiontype)|false|none|none|
|question|string¦null|false|none|none|
|answerTeamId|string(uuid)¦null|false|none|none|
|answerTeamName|string¦null|false|none|none|
|answerText|string¦null|false|none|none|
|isResolved|boolean|false|none|none|
|points|integer(int32)|false|none|none|
|createdAt|string(date-time)|false|none|none|
|updatedAt|string(date-time)|false|none|none|
|predictionCount|integer(int32)|false|none|none|

<h2 id="tocS_AdminBonusQuestionDtoResult">AdminBonusQuestionDtoResult</h2>
<!-- backwards compatibility -->
<a id="schemaadminbonusquestiondtoresult"></a>
<a id="schema_AdminBonusQuestionDtoResult"></a>
<a id="tocSadminbonusquestiondtoresult"></a>
<a id="tocsadminbonusquestiondtoresult"></a>

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "tournamentId": "4a951104-9f98-4996-b388-a0ef2c00bb2a",
    "tournamentName": "string",
    "questionType": 0,
    "question": "string",
    "answerTeamId": "ab2250dd-c194-4fab-a78b-360f3b350150",
    "answerTeamName": "string",
    "answerText": "string",
    "isResolved": true,
    "points": 0,
    "createdAt": "2019-08-24T14:15:22Z",
    "updatedAt": "2019-08-24T14:15:22Z",
    "predictionCount": 0
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|isSuccess|boolean|false|read-only|none|
|error|[Error](#schemaerror)|false|none|none|
|data|[AdminBonusQuestionDto](#schemaadminbonusquestiondto)|false|none|none|

<h2 id="tocS_AdminChatMessageDto">AdminChatMessageDto</h2>
<!-- backwards compatibility -->
<a id="schemaadminchatmessagedto"></a>
<a id="schema_AdminChatMessageDto"></a>
<a id="tocSadminchatmessagedto"></a>
<a id="tocsadminchatmessagedto"></a>

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "leagueId": "58549e12-c6e6-4e03-99d1-6e916f71ce9a",
  "leagueName": "string",
  "userId": "2c4a230c-5085-4924-a3e1-25fb4fc5965b",
  "username": "string",
  "userDisplayName": "string",
  "userAvatarUrl": "string",
  "message": "string",
  "isEdited": true,
  "editedAt": "2019-08-24T14:15:22Z",
  "isDeleted": true,
  "createdAt": "2019-08-24T14:15:22Z"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|false|none|none|
|leagueId|string(uuid)|false|none|none|
|leagueName|string¦null|false|none|none|
|userId|string(uuid)|false|none|none|
|username|string¦null|false|none|none|
|userDisplayName|string¦null|false|none|none|
|userAvatarUrl|string¦null|false|none|none|
|message|string¦null|false|none|none|
|isEdited|boolean|false|none|none|
|editedAt|string(date-time)¦null|false|none|none|
|isDeleted|boolean|false|none|none|
|createdAt|string(date-time)|false|none|none|

<h2 id="tocS_AdminChatMessagesResponse">AdminChatMessagesResponse</h2>
<!-- backwards compatibility -->
<a id="schemaadminchatmessagesresponse"></a>
<a id="schema_AdminChatMessagesResponse"></a>
<a id="tocSadminchatmessagesresponse"></a>
<a id="tocsadminchatmessagesresponse"></a>

```json
{
  "messages": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "leagueId": "58549e12-c6e6-4e03-99d1-6e916f71ce9a",
      "leagueName": "string",
      "userId": "2c4a230c-5085-4924-a3e1-25fb4fc5965b",
      "username": "string",
      "userDisplayName": "string",
      "userAvatarUrl": "string",
      "message": "string",
      "isEdited": true,
      "editedAt": "2019-08-24T14:15:22Z",
      "isDeleted": true,
      "createdAt": "2019-08-24T14:15:22Z"
    }
  ],
  "nextCursor": "2019-08-24T14:15:22Z",
  "hasMore": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|messages|[[AdminChatMessageDto](#schemaadminchatmessagedto)]¦null|false|none|none|
|nextCursor|string(date-time)¦null|false|none|none|
|hasMore|boolean|false|none|none|

<h2 id="tocS_AdminChatMessagesResponseResult">AdminChatMessagesResponseResult</h2>
<!-- backwards compatibility -->
<a id="schemaadminchatmessagesresponseresult"></a>
<a id="schema_AdminChatMessagesResponseResult"></a>
<a id="tocSadminchatmessagesresponseresult"></a>
<a id="tocsadminchatmessagesresponseresult"></a>

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": {
    "messages": [
      {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "leagueId": "58549e12-c6e6-4e03-99d1-6e916f71ce9a",
        "leagueName": "string",
        "userId": "2c4a230c-5085-4924-a3e1-25fb4fc5965b",
        "username": "string",
        "userDisplayName": "string",
        "userAvatarUrl": "string",
        "message": "string",
        "isEdited": true,
        "editedAt": "2019-08-24T14:15:22Z",
        "isDeleted": true,
        "createdAt": "2019-08-24T14:15:22Z"
      }
    ],
    "nextCursor": "2019-08-24T14:15:22Z",
    "hasMore": true
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|isSuccess|boolean|false|read-only|none|
|error|[Error](#schemaerror)|false|none|none|
|data|[AdminChatMessagesResponse](#schemaadminchatmessagesresponse)|false|none|none|

<h2 id="tocS_AdminLeagueDto">AdminLeagueDto</h2>
<!-- backwards compatibility -->
<a id="schemaadminleaguedto"></a>
<a id="schema_AdminLeagueDto"></a>
<a id="tocSadminleaguedto"></a>
<a id="tocsadminleaguedto"></a>

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "name": "string",
  "description": "string",
  "tournamentId": "4a951104-9f98-4996-b388-a0ef2c00bb2a",
  "tournamentName": "string",
  "ownerId": "4d206909-730f-409a-88f6-dcfaa8fc28cc",
  "ownerUsername": "string",
  "inviteCode": "string",
  "isPublic": true,
  "isGlobal": true,
  "isSystemCreated": true,
  "maxMembers": 0,
  "imageUrl": "string",
  "createdAt": "2019-08-24T14:15:22Z",
  "updatedAt": "2019-08-24T14:15:22Z",
  "memberCount": 0,
  "predictionCount": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|false|none|none|
|name|string¦null|false|none|none|
|description|string¦null|false|none|none|
|tournamentId|string(uuid)|false|none|none|
|tournamentName|string¦null|false|none|none|
|ownerId|string(uuid)¦null|false|none|none|
|ownerUsername|string¦null|false|none|none|
|inviteCode|string¦null|false|none|none|
|isPublic|boolean|false|none|none|
|isGlobal|boolean|false|none|none|
|isSystemCreated|boolean|false|none|none|
|maxMembers|integer(int32)¦null|false|none|none|
|imageUrl|string¦null|false|none|none|
|createdAt|string(date-time)|false|none|none|
|updatedAt|string(date-time)|false|none|none|
|memberCount|integer(int32)|false|none|none|
|predictionCount|integer(int32)|false|none|none|

<h2 id="tocS_AdminLeagueDtoResult">AdminLeagueDtoResult</h2>
<!-- backwards compatibility -->
<a id="schemaadminleaguedtoresult"></a>
<a id="schema_AdminLeagueDtoResult"></a>
<a id="tocSadminleaguedtoresult"></a>
<a id="tocsadminleaguedtoresult"></a>

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "name": "string",
    "description": "string",
    "tournamentId": "4a951104-9f98-4996-b388-a0ef2c00bb2a",
    "tournamentName": "string",
    "ownerId": "4d206909-730f-409a-88f6-dcfaa8fc28cc",
    "ownerUsername": "string",
    "inviteCode": "string",
    "isPublic": true,
    "isGlobal": true,
    "isSystemCreated": true,
    "maxMembers": 0,
    "imageUrl": "string",
    "createdAt": "2019-08-24T14:15:22Z",
    "updatedAt": "2019-08-24T14:15:22Z",
    "memberCount": 0,
    "predictionCount": 0
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|isSuccess|boolean|false|read-only|none|
|error|[Error](#schemaerror)|false|none|none|
|data|[AdminLeagueDto](#schemaadminleaguedto)|false|none|none|

<h2 id="tocS_AdminLeagueListDto">AdminLeagueListDto</h2>
<!-- backwards compatibility -->
<a id="schemaadminleaguelistdto"></a>
<a id="schema_AdminLeagueListDto"></a>
<a id="tocSadminleaguelistdto"></a>
<a id="tocsadminleaguelistdto"></a>

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "name": "string",
  "description": "string",
  "tournamentId": "4a951104-9f98-4996-b388-a0ef2c00bb2a",
  "tournamentName": "string",
  "ownerId": "4d206909-730f-409a-88f6-dcfaa8fc28cc",
  "ownerUsername": "string",
  "isPublic": true,
  "isGlobal": true,
  "maxMembers": 0,
  "createdAt": "2019-08-24T14:15:22Z",
  "memberCount": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|false|none|none|
|name|string¦null|false|none|none|
|description|string¦null|false|none|none|
|tournamentId|string(uuid)|false|none|none|
|tournamentName|string¦null|false|none|none|
|ownerId|string(uuid)¦null|false|none|none|
|ownerUsername|string¦null|false|none|none|
|isPublic|boolean|false|none|none|
|isGlobal|boolean|false|none|none|
|maxMembers|integer(int32)¦null|false|none|none|
|createdAt|string(date-time)|false|none|none|
|memberCount|integer(int32)|false|none|none|

<h2 id="tocS_AdminLeagueListDtoPagedResult">AdminLeagueListDtoPagedResult</h2>
<!-- backwards compatibility -->
<a id="schemaadminleaguelistdtopagedresult"></a>
<a id="schema_AdminLeagueListDtoPagedResult"></a>
<a id="tocSadminleaguelistdtopagedresult"></a>
<a id="tocsadminleaguelistdtopagedresult"></a>

```json
{
  "items": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "name": "string",
      "description": "string",
      "tournamentId": "4a951104-9f98-4996-b388-a0ef2c00bb2a",
      "tournamentName": "string",
      "ownerId": "4d206909-730f-409a-88f6-dcfaa8fc28cc",
      "ownerUsername": "string",
      "isPublic": true,
      "isGlobal": true,
      "maxMembers": 0,
      "createdAt": "2019-08-24T14:15:22Z",
      "memberCount": 0
    }
  ],
  "totalCount": 0,
  "page": 0,
  "pageSize": 0,
  "totalPages": 0,
  "hasNextPage": true,
  "hasPreviousPage": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|items|[[AdminLeagueListDto](#schemaadminleaguelistdto)]¦null|false|none|none|
|totalCount|integer(int32)|false|none|none|
|page|integer(int32)|false|none|none|
|pageSize|integer(int32)|false|none|none|
|totalPages|integer(int32)|false|read-only|none|
|hasNextPage|boolean|false|read-only|none|
|hasPreviousPage|boolean|false|read-only|none|

<h2 id="tocS_AdminLeagueListDtoPagedResultResult">AdminLeagueListDtoPagedResultResult</h2>
<!-- backwards compatibility -->
<a id="schemaadminleaguelistdtopagedresultresult"></a>
<a id="schema_AdminLeagueListDtoPagedResultResult"></a>
<a id="tocSadminleaguelistdtopagedresultresult"></a>
<a id="tocsadminleaguelistdtopagedresultresult"></a>

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": {
    "items": [
      {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "name": "string",
        "description": "string",
        "tournamentId": "4a951104-9f98-4996-b388-a0ef2c00bb2a",
        "tournamentName": "string",
        "ownerId": "4d206909-730f-409a-88f6-dcfaa8fc28cc",
        "ownerUsername": "string",
        "isPublic": true,
        "isGlobal": true,
        "maxMembers": 0,
        "createdAt": "2019-08-24T14:15:22Z",
        "memberCount": 0
      }
    ],
    "totalCount": 0,
    "page": 0,
    "pageSize": 0,
    "totalPages": 0,
    "hasNextPage": true,
    "hasPreviousPage": true
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|isSuccess|boolean|false|read-only|none|
|error|[Error](#schemaerror)|false|none|none|
|data|[AdminLeagueListDtoPagedResult](#schemaadminleaguelistdtopagedresult)|false|none|none|

<h2 id="tocS_AdminLeagueMemberDto">AdminLeagueMemberDto</h2>
<!-- backwards compatibility -->
<a id="schemaadminleaguememberdto"></a>
<a id="schema_AdminLeagueMemberDto"></a>
<a id="tocSadminleaguememberdto"></a>
<a id="tocsadminleaguememberdto"></a>

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "leagueId": "58549e12-c6e6-4e03-99d1-6e916f71ce9a",
  "userId": "2c4a230c-5085-4924-a3e1-25fb4fc5965b",
  "username": "string",
  "displayName": "string",
  "email": "string",
  "avatarUrl": "string",
  "joinedAt": "2019-08-24T14:15:22Z",
  "isAdmin": true,
  "isMuted": true,
  "totalPoints": 0,
  "rank": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|false|none|none|
|leagueId|string(uuid)|false|none|none|
|userId|string(uuid)|false|none|none|
|username|string¦null|false|none|none|
|displayName|string¦null|false|none|none|
|email|string¦null|false|none|none|
|avatarUrl|string¦null|false|none|none|
|joinedAt|string(date-time)|false|none|none|
|isAdmin|boolean|false|none|none|
|isMuted|boolean|false|none|none|
|totalPoints|integer(int32)|false|none|none|
|rank|integer(int32)|false|none|none|

<h2 id="tocS_AdminLeagueMemberDtoIReadOnlyListResult">AdminLeagueMemberDtoIReadOnlyListResult</h2>
<!-- backwards compatibility -->
<a id="schemaadminleaguememberdtoireadonlylistresult"></a>
<a id="schema_AdminLeagueMemberDtoIReadOnlyListResult"></a>
<a id="tocSadminleaguememberdtoireadonlylistresult"></a>
<a id="tocsadminleaguememberdtoireadonlylistresult"></a>

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "leagueId": "58549e12-c6e6-4e03-99d1-6e916f71ce9a",
      "userId": "2c4a230c-5085-4924-a3e1-25fb4fc5965b",
      "username": "string",
      "displayName": "string",
      "email": "string",
      "avatarUrl": "string",
      "joinedAt": "2019-08-24T14:15:22Z",
      "isAdmin": true,
      "isMuted": true,
      "totalPoints": 0,
      "rank": 0
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|isSuccess|boolean|false|read-only|none|
|error|[Error](#schemaerror)|false|none|none|
|data|[[AdminLeagueMemberDto](#schemaadminleaguememberdto)]¦null|false|read-only|none|

<h2 id="tocS_AdminMatchDto">AdminMatchDto</h2>
<!-- backwards compatibility -->
<a id="schemaadminmatchdto"></a>
<a id="schema_AdminMatchDto"></a>
<a id="tocSadminmatchdto"></a>
<a id="tocsadminmatchdto"></a>

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "tournamentId": "4a951104-9f98-4996-b388-a0ef2c00bb2a",
  "tournamentName": "string",
  "homeTeamId": "fb7b8236-8f4a-4255-b25d-a64d7c4d6968",
  "homeTeamName": "string",
  "homeTeamCode": "string",
  "homeTeamLogoUrl": "string",
  "awayTeamId": "aa1734e3-668a-43b1-918b-ecab48ec02f9",
  "awayTeamName": "string",
  "awayTeamCode": "string",
  "awayTeamLogoUrl": "string",
  "matchDate": "2019-08-24T14:15:22Z",
  "stage": 0,
  "homeScore": 0,
  "awayScore": 0,
  "status": 0,
  "venue": "string",
  "apiFootballId": 0,
  "resultVersion": 0,
  "createdAt": "2019-08-24T14:15:22Z",
  "updatedAt": "2019-08-24T14:15:22Z",
  "predictionCount": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|false|none|none|
|tournamentId|string(uuid)|false|none|none|
|tournamentName|string¦null|false|none|none|
|homeTeamId|string(uuid)|false|none|none|
|homeTeamName|string¦null|false|none|none|
|homeTeamCode|string¦null|false|none|none|
|homeTeamLogoUrl|string¦null|false|none|none|
|awayTeamId|string(uuid)|false|none|none|
|awayTeamName|string¦null|false|none|none|
|awayTeamCode|string¦null|false|none|none|
|awayTeamLogoUrl|string¦null|false|none|none|
|matchDate|string(date-time)|false|none|none|
|stage|[MatchStage](#schemamatchstage)|false|none|none|
|homeScore|integer(int32)¦null|false|none|none|
|awayScore|integer(int32)¦null|false|none|none|
|status|[MatchStatus](#schemamatchstatus)|false|none|none|
|venue|string¦null|false|none|none|
|apiFootballId|integer(int32)¦null|false|none|none|
|resultVersion|integer(int32)|false|none|none|
|createdAt|string(date-time)|false|none|none|
|updatedAt|string(date-time)|false|none|none|
|predictionCount|integer(int32)|false|none|none|

<h2 id="tocS_AdminMatchDtoResult">AdminMatchDtoResult</h2>
<!-- backwards compatibility -->
<a id="schemaadminmatchdtoresult"></a>
<a id="schema_AdminMatchDtoResult"></a>
<a id="tocSadminmatchdtoresult"></a>
<a id="tocsadminmatchdtoresult"></a>

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "tournamentId": "4a951104-9f98-4996-b388-a0ef2c00bb2a",
    "tournamentName": "string",
    "homeTeamId": "fb7b8236-8f4a-4255-b25d-a64d7c4d6968",
    "homeTeamName": "string",
    "homeTeamCode": "string",
    "homeTeamLogoUrl": "string",
    "awayTeamId": "aa1734e3-668a-43b1-918b-ecab48ec02f9",
    "awayTeamName": "string",
    "awayTeamCode": "string",
    "awayTeamLogoUrl": "string",
    "matchDate": "2019-08-24T14:15:22Z",
    "stage": 0,
    "homeScore": 0,
    "awayScore": 0,
    "status": 0,
    "venue": "string",
    "apiFootballId": 0,
    "resultVersion": 0,
    "createdAt": "2019-08-24T14:15:22Z",
    "updatedAt": "2019-08-24T14:15:22Z",
    "predictionCount": 0
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|isSuccess|boolean|false|read-only|none|
|error|[Error](#schemaerror)|false|none|none|
|data|[AdminMatchDto](#schemaadminmatchdto)|false|none|none|

<h2 id="tocS_AdminPredictionDto">AdminPredictionDto</h2>
<!-- backwards compatibility -->
<a id="schemaadminpredictiondto"></a>
<a id="schema_AdminPredictionDto"></a>
<a id="tocSadminpredictiondto"></a>
<a id="tocsadminpredictiondto"></a>

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "userId": "2c4a230c-5085-4924-a3e1-25fb4fc5965b",
  "username": "string",
  "userDisplayName": "string",
  "matchId": "685569fd-95e6-4335-9aa5-fdd22382bd9e",
  "matchDescription": "string",
  "leagueId": "58549e12-c6e6-4e03-99d1-6e916f71ce9a",
  "leagueName": "string",
  "homeScore": 0,
  "awayScore": 0,
  "actualHomeScore": 0,
  "actualAwayScore": 0,
  "pointsEarned": 0,
  "isScored": true,
  "scoredResultVersion": 0,
  "scoredAt": "2019-08-24T14:15:22Z",
  "createdAt": "2019-08-24T14:15:22Z",
  "updatedAt": "2019-08-24T14:15:22Z"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|false|none|none|
|userId|string(uuid)|false|none|none|
|username|string¦null|false|none|none|
|userDisplayName|string¦null|false|none|none|
|matchId|string(uuid)|false|none|none|
|matchDescription|string¦null|false|none|none|
|leagueId|string(uuid)|false|none|none|
|leagueName|string¦null|false|none|none|
|homeScore|integer(int32)|false|none|none|
|awayScore|integer(int32)|false|none|none|
|actualHomeScore|integer(int32)¦null|false|none|none|
|actualAwayScore|integer(int32)¦null|false|none|none|
|pointsEarned|integer(int32)|false|none|none|
|isScored|boolean|false|none|none|
|scoredResultVersion|integer(int32)¦null|false|none|none|
|scoredAt|string(date-time)¦null|false|none|none|
|createdAt|string(date-time)|false|none|none|
|updatedAt|string(date-time)|false|none|none|

<h2 id="tocS_AdminPredictionDtoResult">AdminPredictionDtoResult</h2>
<!-- backwards compatibility -->
<a id="schemaadminpredictiondtoresult"></a>
<a id="schema_AdminPredictionDtoResult"></a>
<a id="tocSadminpredictiondtoresult"></a>
<a id="tocsadminpredictiondtoresult"></a>

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "userId": "2c4a230c-5085-4924-a3e1-25fb4fc5965b",
    "username": "string",
    "userDisplayName": "string",
    "matchId": "685569fd-95e6-4335-9aa5-fdd22382bd9e",
    "matchDescription": "string",
    "leagueId": "58549e12-c6e6-4e03-99d1-6e916f71ce9a",
    "leagueName": "string",
    "homeScore": 0,
    "awayScore": 0,
    "actualHomeScore": 0,
    "actualAwayScore": 0,
    "pointsEarned": 0,
    "isScored": true,
    "scoredResultVersion": 0,
    "scoredAt": "2019-08-24T14:15:22Z",
    "createdAt": "2019-08-24T14:15:22Z",
    "updatedAt": "2019-08-24T14:15:22Z"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|isSuccess|boolean|false|read-only|none|
|error|[Error](#schemaerror)|false|none|none|
|data|[AdminPredictionDto](#schemaadminpredictiondto)|false|none|none|

<h2 id="tocS_AdminPredictionListDto">AdminPredictionListDto</h2>
<!-- backwards compatibility -->
<a id="schemaadminpredictionlistdto"></a>
<a id="schema_AdminPredictionListDto"></a>
<a id="tocSadminpredictionlistdto"></a>
<a id="tocsadminpredictionlistdto"></a>

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "userId": "2c4a230c-5085-4924-a3e1-25fb4fc5965b",
  "username": "string",
  "matchId": "685569fd-95e6-4335-9aa5-fdd22382bd9e",
  "matchDescription": "string",
  "leagueId": "58549e12-c6e6-4e03-99d1-6e916f71ce9a",
  "leagueName": "string",
  "homeScore": 0,
  "awayScore": 0,
  "pointsEarned": 0,
  "isScored": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|false|none|none|
|userId|string(uuid)|false|none|none|
|username|string¦null|false|none|none|
|matchId|string(uuid)|false|none|none|
|matchDescription|string¦null|false|none|none|
|leagueId|string(uuid)|false|none|none|
|leagueName|string¦null|false|none|none|
|homeScore|integer(int32)|false|none|none|
|awayScore|integer(int32)|false|none|none|
|pointsEarned|integer(int32)|false|none|none|
|isScored|boolean|false|none|none|

<h2 id="tocS_AdminPredictionListDtoPagedResult">AdminPredictionListDtoPagedResult</h2>
<!-- backwards compatibility -->
<a id="schemaadminpredictionlistdtopagedresult"></a>
<a id="schema_AdminPredictionListDtoPagedResult"></a>
<a id="tocSadminpredictionlistdtopagedresult"></a>
<a id="tocsadminpredictionlistdtopagedresult"></a>

```json
{
  "items": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "userId": "2c4a230c-5085-4924-a3e1-25fb4fc5965b",
      "username": "string",
      "matchId": "685569fd-95e6-4335-9aa5-fdd22382bd9e",
      "matchDescription": "string",
      "leagueId": "58549e12-c6e6-4e03-99d1-6e916f71ce9a",
      "leagueName": "string",
      "homeScore": 0,
      "awayScore": 0,
      "pointsEarned": 0,
      "isScored": true
    }
  ],
  "totalCount": 0,
  "page": 0,
  "pageSize": 0,
  "totalPages": 0,
  "hasNextPage": true,
  "hasPreviousPage": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|items|[[AdminPredictionListDto](#schemaadminpredictionlistdto)]¦null|false|none|none|
|totalCount|integer(int32)|false|none|none|
|page|integer(int32)|false|none|none|
|pageSize|integer(int32)|false|none|none|
|totalPages|integer(int32)|false|read-only|none|
|hasNextPage|boolean|false|read-only|none|
|hasPreviousPage|boolean|false|read-only|none|

<h2 id="tocS_AdminPredictionListDtoPagedResultResult">AdminPredictionListDtoPagedResultResult</h2>
<!-- backwards compatibility -->
<a id="schemaadminpredictionlistdtopagedresultresult"></a>
<a id="schema_AdminPredictionListDtoPagedResultResult"></a>
<a id="tocSadminpredictionlistdtopagedresultresult"></a>
<a id="tocsadminpredictionlistdtopagedresultresult"></a>

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": {
    "items": [
      {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "userId": "2c4a230c-5085-4924-a3e1-25fb4fc5965b",
        "username": "string",
        "matchId": "685569fd-95e6-4335-9aa5-fdd22382bd9e",
        "matchDescription": "string",
        "leagueId": "58549e12-c6e6-4e03-99d1-6e916f71ce9a",
        "leagueName": "string",
        "homeScore": 0,
        "awayScore": 0,
        "pointsEarned": 0,
        "isScored": true
      }
    ],
    "totalCount": 0,
    "page": 0,
    "pageSize": 0,
    "totalPages": 0,
    "hasNextPage": true,
    "hasPreviousPage": true
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|isSuccess|boolean|false|read-only|none|
|error|[Error](#schemaerror)|false|none|none|
|data|[AdminPredictionListDtoPagedResult](#schemaadminpredictionlistdtopagedresult)|false|none|none|

<h2 id="tocS_AdminTeamDto">AdminTeamDto</h2>
<!-- backwards compatibility -->
<a id="schemaadminteamdto"></a>
<a id="schema_AdminTeamDto"></a>
<a id="tocSadminteamdto"></a>
<a id="tocsadminteamdto"></a>

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "tournamentId": "4a951104-9f98-4996-b388-a0ef2c00bb2a",
  "tournamentName": "string",
  "name": "string",
  "code": "string",
  "logoUrl": "string",
  "groupName": "string",
  "fifaRank": 0,
  "fifaPoints": 0.1,
  "fifaRankingUpdatedAt": "2019-08-24T14:15:22Z",
  "apiFootballId": 0,
  "createdAt": "2019-08-24T14:15:22Z",
  "updatedAt": "2019-08-24T14:15:22Z"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|false|none|none|
|tournamentId|string(uuid)|false|none|none|
|tournamentName|string¦null|false|none|none|
|name|string¦null|false|none|none|
|code|string¦null|false|none|none|
|logoUrl|string¦null|false|none|none|
|groupName|string¦null|false|none|none|
|fifaRank|integer(int32)¦null|false|none|none|
|fifaPoints|number(double)¦null|false|none|none|
|fifaRankingUpdatedAt|string(date-time)¦null|false|none|none|
|apiFootballId|integer(int32)¦null|false|none|none|
|createdAt|string(date-time)|false|none|none|
|updatedAt|string(date-time)|false|none|none|

<h2 id="tocS_AdminTeamDtoResult">AdminTeamDtoResult</h2>
<!-- backwards compatibility -->
<a id="schemaadminteamdtoresult"></a>
<a id="schema_AdminTeamDtoResult"></a>
<a id="tocSadminteamdtoresult"></a>
<a id="tocsadminteamdtoresult"></a>

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "tournamentId": "4a951104-9f98-4996-b388-a0ef2c00bb2a",
    "tournamentName": "string",
    "name": "string",
    "code": "string",
    "logoUrl": "string",
    "groupName": "string",
    "fifaRank": 0,
    "fifaPoints": 0.1,
    "fifaRankingUpdatedAt": "2019-08-24T14:15:22Z",
    "apiFootballId": 0,
    "createdAt": "2019-08-24T14:15:22Z",
    "updatedAt": "2019-08-24T14:15:22Z"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|isSuccess|boolean|false|read-only|none|
|error|[Error](#schemaerror)|false|none|none|
|data|[AdminTeamDto](#schemaadminteamdto)|false|none|none|

<h2 id="tocS_AdminTournamentDto">AdminTournamentDto</h2>
<!-- backwards compatibility -->
<a id="schemaadmintournamentdto"></a>
<a id="schema_AdminTournamentDto"></a>
<a id="tocSadmintournamentdto"></a>
<a id="tocsadmintournamentdto"></a>

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "name": "string",
  "year": 0,
  "type": 0,
  "startDate": "2019-08-24T14:15:22Z",
  "endDate": "2019-08-24T14:15:22Z",
  "logoUrl": "string",
  "isActive": true,
  "createdAt": "2019-08-24T14:15:22Z",
  "updatedAt": "2019-08-24T14:15:22Z",
  "teamCount": 0,
  "matchCount": 0,
  "leagueCount": 0,
  "bonusQuestionCount": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|false|none|none|
|name|string¦null|false|none|none|
|year|integer(int32)|false|none|none|
|type|[TournamentType](#schematournamenttype)|false|none|none|
|startDate|string(date-time)|false|none|none|
|endDate|string(date-time)|false|none|none|
|logoUrl|string¦null|false|none|none|
|isActive|boolean|false|none|none|
|createdAt|string(date-time)|false|none|none|
|updatedAt|string(date-time)|false|none|none|
|teamCount|integer(int32)|false|none|none|
|matchCount|integer(int32)|false|none|none|
|leagueCount|integer(int32)|false|none|none|
|bonusQuestionCount|integer(int32)|false|none|none|

<h2 id="tocS_AdminTournamentDtoResult">AdminTournamentDtoResult</h2>
<!-- backwards compatibility -->
<a id="schemaadmintournamentdtoresult"></a>
<a id="schema_AdminTournamentDtoResult"></a>
<a id="tocSadmintournamentdtoresult"></a>
<a id="tocsadmintournamentdtoresult"></a>

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "name": "string",
    "year": 0,
    "type": 0,
    "startDate": "2019-08-24T14:15:22Z",
    "endDate": "2019-08-24T14:15:22Z",
    "logoUrl": "string",
    "isActive": true,
    "createdAt": "2019-08-24T14:15:22Z",
    "updatedAt": "2019-08-24T14:15:22Z",
    "teamCount": 0,
    "matchCount": 0,
    "leagueCount": 0,
    "bonusQuestionCount": 0
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|isSuccess|boolean|false|read-only|none|
|error|[Error](#schemaerror)|false|none|none|
|data|[AdminTournamentDto](#schemaadmintournamentdto)|false|none|none|

<h2 id="tocS_AdminUserDto">AdminUserDto</h2>
<!-- backwards compatibility -->
<a id="schemaadminuserdto"></a>
<a id="schema_AdminUserDto"></a>
<a id="tocSadminuserdto"></a>
<a id="tocsadminuserdto"></a>

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "authUserId": "5a3cace6-919f-4109-8313-c3a2264a4134",
  "username": "string",
  "displayName": "string",
  "email": "string",
  "avatarUrl": "string",
  "bio": "string",
  "role": 0,
  "isBanned": true,
  "favoriteTeamId": "d03f4e26-a6b7-4158-9c97-87bb7dc42e8b",
  "favoriteTeamName": "string",
  "lastLoginAt": "2019-08-24T14:15:22Z",
  "createdAt": "2019-08-24T14:15:22Z",
  "updatedAt": "2019-08-24T14:15:22Z",
  "leagueCount": 0,
  "ownedLeagueCount": 0,
  "predictionCount": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|false|none|none|
|authUserId|string(uuid)|false|none|none|
|username|string¦null|false|none|none|
|displayName|string¦null|false|none|none|
|email|string¦null|false|none|none|
|avatarUrl|string¦null|false|none|none|
|bio|string¦null|false|none|none|
|role|[UserRole](#schemauserrole)|false|none|none|
|isBanned|boolean|false|none|none|
|favoriteTeamId|string(uuid)¦null|false|none|none|
|favoriteTeamName|string¦null|false|none|none|
|lastLoginAt|string(date-time)¦null|false|none|none|
|createdAt|string(date-time)|false|none|none|
|updatedAt|string(date-time)|false|none|none|
|leagueCount|integer(int32)|false|none|none|
|ownedLeagueCount|integer(int32)|false|none|none|
|predictionCount|integer(int32)|false|none|none|

<h2 id="tocS_AdminUserDtoResult">AdminUserDtoResult</h2>
<!-- backwards compatibility -->
<a id="schemaadminuserdtoresult"></a>
<a id="schema_AdminUserDtoResult"></a>
<a id="tocSadminuserdtoresult"></a>
<a id="tocsadminuserdtoresult"></a>

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "authUserId": "5a3cace6-919f-4109-8313-c3a2264a4134",
    "username": "string",
    "displayName": "string",
    "email": "string",
    "avatarUrl": "string",
    "bio": "string",
    "role": 0,
    "isBanned": true,
    "favoriteTeamId": "d03f4e26-a6b7-4158-9c97-87bb7dc42e8b",
    "favoriteTeamName": "string",
    "lastLoginAt": "2019-08-24T14:15:22Z",
    "createdAt": "2019-08-24T14:15:22Z",
    "updatedAt": "2019-08-24T14:15:22Z",
    "leagueCount": 0,
    "ownedLeagueCount": 0,
    "predictionCount": 0
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|isSuccess|boolean|false|read-only|none|
|error|[Error](#schemaerror)|false|none|none|
|data|[AdminUserDto](#schemaadminuserdto)|false|none|none|

<h2 id="tocS_AdminUserListDto">AdminUserListDto</h2>
<!-- backwards compatibility -->
<a id="schemaadminuserlistdto"></a>
<a id="schema_AdminUserListDto"></a>
<a id="tocSadminuserlistdto"></a>
<a id="tocsadminuserlistdto"></a>

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "username": "string",
  "displayName": "string",
  "email": "string",
  "avatarUrl": "string",
  "role": 0,
  "isBanned": true,
  "lastLoginAt": "2019-08-24T14:15:22Z",
  "createdAt": "2019-08-24T14:15:22Z"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|false|none|none|
|username|string¦null|false|none|none|
|displayName|string¦null|false|none|none|
|email|string¦null|false|none|none|
|avatarUrl|string¦null|false|none|none|
|role|[UserRole](#schemauserrole)|false|none|none|
|isBanned|boolean|false|none|none|
|lastLoginAt|string(date-time)¦null|false|none|none|
|createdAt|string(date-time)|false|none|none|

<h2 id="tocS_AdminUserListDtoPagedResult">AdminUserListDtoPagedResult</h2>
<!-- backwards compatibility -->
<a id="schemaadminuserlistdtopagedresult"></a>
<a id="schema_AdminUserListDtoPagedResult"></a>
<a id="tocSadminuserlistdtopagedresult"></a>
<a id="tocsadminuserlistdtopagedresult"></a>

```json
{
  "items": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "username": "string",
      "displayName": "string",
      "email": "string",
      "avatarUrl": "string",
      "role": 0,
      "isBanned": true,
      "lastLoginAt": "2019-08-24T14:15:22Z",
      "createdAt": "2019-08-24T14:15:22Z"
    }
  ],
  "totalCount": 0,
  "page": 0,
  "pageSize": 0,
  "totalPages": 0,
  "hasNextPage": true,
  "hasPreviousPage": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|items|[[AdminUserListDto](#schemaadminuserlistdto)]¦null|false|none|none|
|totalCount|integer(int32)|false|none|none|
|page|integer(int32)|false|none|none|
|pageSize|integer(int32)|false|none|none|
|totalPages|integer(int32)|false|read-only|none|
|hasNextPage|boolean|false|read-only|none|
|hasPreviousPage|boolean|false|read-only|none|

<h2 id="tocS_AdminUserListDtoPagedResultResult">AdminUserListDtoPagedResultResult</h2>
<!-- backwards compatibility -->
<a id="schemaadminuserlistdtopagedresultresult"></a>
<a id="schema_AdminUserListDtoPagedResultResult"></a>
<a id="tocSadminuserlistdtopagedresultresult"></a>
<a id="tocsadminuserlistdtopagedresultresult"></a>

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": {
    "items": [
      {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "username": "string",
        "displayName": "string",
        "email": "string",
        "avatarUrl": "string",
        "role": 0,
        "isBanned": true,
        "lastLoginAt": "2019-08-24T14:15:22Z",
        "createdAt": "2019-08-24T14:15:22Z"
      }
    ],
    "totalCount": 0,
    "page": 0,
    "pageSize": 0,
    "totalPages": 0,
    "hasNextPage": true,
    "hasPreviousPage": true
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|isSuccess|boolean|false|read-only|none|
|error|[Error](#schemaerror)|false|none|none|
|data|[AdminUserListDtoPagedResult](#schemaadminuserlistdtopagedresult)|false|none|none|

<h2 id="tocS_BonusPredictionDto">BonusPredictionDto</h2>
<!-- backwards compatibility -->
<a id="schemabonuspredictiondto"></a>
<a id="schema_BonusPredictionDto"></a>
<a id="tocSbonuspredictiondto"></a>
<a id="tocsbonuspredictiondto"></a>

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "userId": "2c4a230c-5085-4924-a3e1-25fb4fc5965b",
  "leagueId": "58549e12-c6e6-4e03-99d1-6e916f71ce9a",
  "bonusQuestionId": "a0b61934-6fef-4d97-866d-54f4b60aee83",
  "answerTeamId": "ab2250dd-c194-4fab-a78b-360f3b350150",
  "answerText": "string",
  "createdAt": "2019-08-24T14:15:22Z"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|false|none|none|
|userId|string(uuid)|false|none|none|
|leagueId|string(uuid)|false|none|none|
|bonusQuestionId|string(uuid)|false|none|none|
|answerTeamId|string(uuid)|false|none|none|
|answerText|string¦null|false|none|none|
|createdAt|string(date-time)|false|none|none|

<h2 id="tocS_BonusPredictionDtoListResult">BonusPredictionDtoListResult</h2>
<!-- backwards compatibility -->
<a id="schemabonuspredictiondtolistresult"></a>
<a id="schema_BonusPredictionDtoListResult"></a>
<a id="tocSbonuspredictiondtolistresult"></a>
<a id="tocsbonuspredictiondtolistresult"></a>

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "userId": "2c4a230c-5085-4924-a3e1-25fb4fc5965b",
      "leagueId": "58549e12-c6e6-4e03-99d1-6e916f71ce9a",
      "bonusQuestionId": "a0b61934-6fef-4d97-866d-54f4b60aee83",
      "answerTeamId": "ab2250dd-c194-4fab-a78b-360f3b350150",
      "answerText": "string",
      "createdAt": "2019-08-24T14:15:22Z"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|isSuccess|boolean|false|read-only|none|
|error|[Error](#schemaerror)|false|none|none|
|data|[[BonusPredictionDto](#schemabonuspredictiondto)]¦null|false|read-only|none|

<h2 id="tocS_BonusQuestionDto">BonusQuestionDto</h2>
<!-- backwards compatibility -->
<a id="schemabonusquestiondto"></a>
<a id="schema_BonusQuestionDto"></a>
<a id="tocSbonusquestiondto"></a>
<a id="tocsbonusquestiondto"></a>

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "tournamentId": "4a951104-9f98-4996-b388-a0ef2c00bb2a",
  "questionType": 0,
  "question": "string",
  "points": 0,
  "isResolved": true,
  "answerTeamId": "ab2250dd-c194-4fab-a78b-360f3b350150",
  "answerText": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|false|none|none|
|tournamentId|string(uuid)|false|none|none|
|questionType|[BonusQuestionType](#schemabonusquestiontype)|false|none|none|
|question|string¦null|false|none|none|
|points|integer(int32)|false|none|none|
|isResolved|boolean|false|none|none|
|answerTeamId|string(uuid)|false|none|none|
|answerText|string¦null|false|none|none|

<h2 id="tocS_BonusQuestionDtoIReadOnlyListResult">BonusQuestionDtoIReadOnlyListResult</h2>
<!-- backwards compatibility -->
<a id="schemabonusquestiondtoireadonlylistresult"></a>
<a id="schema_BonusQuestionDtoIReadOnlyListResult"></a>
<a id="tocSbonusquestiondtoireadonlylistresult"></a>
<a id="tocsbonusquestiondtoireadonlylistresult"></a>

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "tournamentId": "4a951104-9f98-4996-b388-a0ef2c00bb2a",
      "questionType": 0,
      "question": "string",
      "points": 0,
      "isResolved": true,
      "answerTeamId": "ab2250dd-c194-4fab-a78b-360f3b350150",
      "answerText": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|isSuccess|boolean|false|read-only|none|
|error|[Error](#schemaerror)|false|none|none|
|data|[[BonusQuestionDto](#schemabonusquestiondto)]¦null|false|read-only|none|

<h2 id="tocS_BonusQuestionType">BonusQuestionType</h2>
<!-- backwards compatibility -->
<a id="schemabonusquestiontype"></a>
<a id="schema_BonusQuestionType"></a>
<a id="tocSbonusquestiontype"></a>
<a id="tocsbonusquestiontype"></a>

```json
0

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|integer(int32)|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|*anonymous*|0|
|*anonymous*|1|
|*anonymous*|2|
|*anonymous*|3|
|*anonymous*|4|
|*anonymous*|5|
|*anonymous*|6|
|*anonymous*|7|

<h2 id="tocS_BooleanResult">BooleanResult</h2>
<!-- backwards compatibility -->
<a id="schemabooleanresult"></a>
<a id="schema_BooleanResult"></a>
<a id="tocSbooleanresult"></a>
<a id="tocsbooleanresult"></a>

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|isSuccess|boolean|false|read-only|none|
|error|[Error](#schemaerror)|false|none|none|
|data|boolean|false|read-only|none|

<h2 id="tocS_BulkCreateMatchesRequest">BulkCreateMatchesRequest</h2>
<!-- backwards compatibility -->
<a id="schemabulkcreatematchesrequest"></a>
<a id="schema_BulkCreateMatchesRequest"></a>
<a id="tocSbulkcreatematchesrequest"></a>
<a id="tocsbulkcreatematchesrequest"></a>

```json
{
  "tournamentId": "4a951104-9f98-4996-b388-a0ef2c00bb2a",
  "matches": [
    {
      "homeTeamId": "fb7b8236-8f4a-4255-b25d-a64d7c4d6968",
      "awayTeamId": "aa1734e3-668a-43b1-918b-ecab48ec02f9",
      "matchDate": "2019-08-24T14:15:22Z",
      "stage": 0,
      "venue": "string",
      "apiFootballId": 0
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|tournamentId|string(uuid)|false|none|none|
|matches|[[BulkMatchRequest](#schemabulkmatchrequest)]¦null|false|none|none|

<h2 id="tocS_BulkCreateMatchesResult">BulkCreateMatchesResult</h2>
<!-- backwards compatibility -->
<a id="schemabulkcreatematchesresult"></a>
<a id="schema_BulkCreateMatchesResult"></a>
<a id="tocSbulkcreatematchesresult"></a>
<a id="tocsbulkcreatematchesresult"></a>

```json
{
  "createdCount": 0,
  "failedCount": 0,
  "errors": [
    "string"
  ],
  "createdIds": [
    "497f6eca-6276-4993-bfeb-53cbbbba6f08"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|createdCount|integer(int32)|false|none|none|
|failedCount|integer(int32)|false|none|none|
|errors|[string]¦null|false|none|none|
|createdIds|[string]¦null|false|none|none|

<h2 id="tocS_BulkCreateMatchesResultResult">BulkCreateMatchesResultResult</h2>
<!-- backwards compatibility -->
<a id="schemabulkcreatematchesresultresult"></a>
<a id="schema_BulkCreateMatchesResultResult"></a>
<a id="tocSbulkcreatematchesresultresult"></a>
<a id="tocsbulkcreatematchesresultresult"></a>

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": {
    "createdCount": 0,
    "failedCount": 0,
    "errors": [
      "string"
    ],
    "createdIds": [
      "497f6eca-6276-4993-bfeb-53cbbbba6f08"
    ]
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|isSuccess|boolean|false|read-only|none|
|error|[Error](#schemaerror)|false|none|none|
|data|[BulkCreateMatchesResult](#schemabulkcreatematchesresult)|false|none|none|

<h2 id="tocS_BulkCreateTeamsRequest">BulkCreateTeamsRequest</h2>
<!-- backwards compatibility -->
<a id="schemabulkcreateteamsrequest"></a>
<a id="schema_BulkCreateTeamsRequest"></a>
<a id="tocSbulkcreateteamsrequest"></a>
<a id="tocsbulkcreateteamsrequest"></a>

```json
{
  "tournamentId": "4a951104-9f98-4996-b388-a0ef2c00bb2a",
  "teams": [
    {
      "name": "string",
      "code": "string",
      "flagUrl": "string",
      "groupName": "string",
      "fifaRank": 0,
      "fifaPoints": 0.1,
      "apiFootballId": 0
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|tournamentId|string(uuid)|false|none|none|
|teams|[[BulkTeamRequest](#schemabulkteamrequest)]¦null|false|none|none|

<h2 id="tocS_BulkCreateTeamsResult">BulkCreateTeamsResult</h2>
<!-- backwards compatibility -->
<a id="schemabulkcreateteamsresult"></a>
<a id="schema_BulkCreateTeamsResult"></a>
<a id="tocSbulkcreateteamsresult"></a>
<a id="tocsbulkcreateteamsresult"></a>

```json
{
  "createdCount": 0,
  "skippedCount": 0,
  "skippedTeams": [
    "string"
  ],
  "createdIds": [
    "497f6eca-6276-4993-bfeb-53cbbbba6f08"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|createdCount|integer(int32)|false|none|none|
|skippedCount|integer(int32)|false|none|none|
|skippedTeams|[string]¦null|false|none|none|
|createdIds|[string]¦null|false|none|none|

<h2 id="tocS_BulkCreateTeamsResultResult">BulkCreateTeamsResultResult</h2>
<!-- backwards compatibility -->
<a id="schemabulkcreateteamsresultresult"></a>
<a id="schema_BulkCreateTeamsResultResult"></a>
<a id="tocSbulkcreateteamsresultresult"></a>
<a id="tocsbulkcreateteamsresultresult"></a>

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": {
    "createdCount": 0,
    "skippedCount": 0,
    "skippedTeams": [
      "string"
    ],
    "createdIds": [
      "497f6eca-6276-4993-bfeb-53cbbbba6f08"
    ]
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|isSuccess|boolean|false|read-only|none|
|error|[Error](#schemaerror)|false|none|none|
|data|[BulkCreateTeamsResult](#schemabulkcreateteamsresult)|false|none|none|

<h2 id="tocS_BulkMatchRequest">BulkMatchRequest</h2>
<!-- backwards compatibility -->
<a id="schemabulkmatchrequest"></a>
<a id="schema_BulkMatchRequest"></a>
<a id="tocSbulkmatchrequest"></a>
<a id="tocsbulkmatchrequest"></a>

```json
{
  "homeTeamId": "fb7b8236-8f4a-4255-b25d-a64d7c4d6968",
  "awayTeamId": "aa1734e3-668a-43b1-918b-ecab48ec02f9",
  "matchDate": "2019-08-24T14:15:22Z",
  "stage": 0,
  "venue": "string",
  "apiFootballId": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|homeTeamId|string(uuid)|false|none|none|
|awayTeamId|string(uuid)|false|none|none|
|matchDate|string(date-time)|false|none|none|
|stage|[MatchStage](#schemamatchstage)|false|none|none|
|venue|string¦null|false|none|none|
|apiFootballId|integer(int32)¦null|false|none|none|

<h2 id="tocS_BulkPredictionItem">BulkPredictionItem</h2>
<!-- backwards compatibility -->
<a id="schemabulkpredictionitem"></a>
<a id="schema_BulkPredictionItem"></a>
<a id="tocSbulkpredictionitem"></a>
<a id="tocsbulkpredictionitem"></a>

```json
{
  "matchId": "685569fd-95e6-4335-9aa5-fdd22382bd9e",
  "homeScore": 0,
  "awayScore": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|matchId|string(uuid)|false|none|none|
|homeScore|integer(int32)|false|none|none|
|awayScore|integer(int32)|false|none|none|

<h2 id="tocS_BulkSubmitPredictionsRequest">BulkSubmitPredictionsRequest</h2>
<!-- backwards compatibility -->
<a id="schemabulksubmitpredictionsrequest"></a>
<a id="schema_BulkSubmitPredictionsRequest"></a>
<a id="tocSbulksubmitpredictionsrequest"></a>
<a id="tocsbulksubmitpredictionsrequest"></a>

```json
{
  "leagueId": "58549e12-c6e6-4e03-99d1-6e916f71ce9a",
  "predictions": [
    {
      "matchId": "685569fd-95e6-4335-9aa5-fdd22382bd9e",
      "homeScore": 0,
      "awayScore": 0
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|leagueId|string(uuid)|false|none|none|
|predictions|[[BulkPredictionItem](#schemabulkpredictionitem)]¦null|false|none|none|

<h2 id="tocS_BulkSubmitPredictionsResult">BulkSubmitPredictionsResult</h2>
<!-- backwards compatibility -->
<a id="schemabulksubmitpredictionsresult"></a>
<a id="schema_BulkSubmitPredictionsResult"></a>
<a id="tocSbulksubmitpredictionsresult"></a>
<a id="tocsbulksubmitpredictionsresult"></a>

```json
{
  "successCount": 0,
  "failedCount": 0,
  "results": [
    {
      "matchId": "685569fd-95e6-4335-9aa5-fdd22382bd9e",
      "predictionId": "07ef3e55-acee-4631-909a-2d5902a608e6",
      "success": true,
      "errorMessage": "string",
      "errorCode": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|successCount|integer(int32)|false|none|none|
|failedCount|integer(int32)|false|none|none|
|results|[[PredictionResult](#schemapredictionresult)]¦null|false|none|none|

<h2 id="tocS_BulkSubmitPredictionsResultResult">BulkSubmitPredictionsResultResult</h2>
<!-- backwards compatibility -->
<a id="schemabulksubmitpredictionsresultresult"></a>
<a id="schema_BulkSubmitPredictionsResultResult"></a>
<a id="tocSbulksubmitpredictionsresultresult"></a>
<a id="tocsbulksubmitpredictionsresultresult"></a>

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": {
    "successCount": 0,
    "failedCount": 0,
    "results": [
      {
        "matchId": "685569fd-95e6-4335-9aa5-fdd22382bd9e",
        "predictionId": "07ef3e55-acee-4631-909a-2d5902a608e6",
        "success": true,
        "errorMessage": "string",
        "errorCode": "string"
      }
    ]
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|isSuccess|boolean|false|read-only|none|
|error|[Error](#schemaerror)|false|none|none|
|data|[BulkSubmitPredictionsResult](#schemabulksubmitpredictionsresult)|false|none|none|

<h2 id="tocS_BulkTeamRequest">BulkTeamRequest</h2>
<!-- backwards compatibility -->
<a id="schemabulkteamrequest"></a>
<a id="schema_BulkTeamRequest"></a>
<a id="tocSbulkteamrequest"></a>
<a id="tocsbulkteamrequest"></a>

```json
{
  "name": "string",
  "code": "string",
  "flagUrl": "string",
  "groupName": "string",
  "fifaRank": 0,
  "fifaPoints": 0.1,
  "apiFootballId": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string¦null|false|none|none|
|code|string¦null|false|none|none|
|flagUrl|string¦null|false|none|none|
|groupName|string¦null|false|none|none|
|fifaRank|integer(int32)¦null|false|none|none|
|fifaPoints|number(double)¦null|false|none|none|
|apiFootballId|integer(int32)¦null|false|none|none|

<h2 id="tocS_CreateBonusQuestionRequest">CreateBonusQuestionRequest</h2>
<!-- backwards compatibility -->
<a id="schemacreatebonusquestionrequest"></a>
<a id="schema_CreateBonusQuestionRequest"></a>
<a id="tocScreatebonusquestionrequest"></a>
<a id="tocscreatebonusquestionrequest"></a>

```json
{
  "tournamentId": "4a951104-9f98-4996-b388-a0ef2c00bb2a",
  "questionType": 0,
  "question": "string",
  "points": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|tournamentId|string(uuid)|false|none|none|
|questionType|[BonusQuestionType](#schemabonusquestiontype)|false|none|none|
|question|string¦null|false|none|none|
|points|integer(int32)|false|none|none|

<h2 id="tocS_CreateLeagueRequest">CreateLeagueRequest</h2>
<!-- backwards compatibility -->
<a id="schemacreateleaguerequest"></a>
<a id="schema_CreateLeagueRequest"></a>
<a id="tocScreateleaguerequest"></a>
<a id="tocscreateleaguerequest"></a>

```json
{
  "name": "string",
  "description": "string",
  "tournamentId": "4a951104-9f98-4996-b388-a0ef2c00bb2a",
  "isPublic": true,
  "maxMembers": 0,
  "imageUrl": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string¦null|false|none|none|
|description|string¦null|false|none|none|
|tournamentId|string(uuid)|false|none|none|
|isPublic|boolean|false|none|none|
|maxMembers|integer(int32)¦null|false|none|none|
|imageUrl|string¦null|false|none|none|

<h2 id="tocS_CreateMatchRequest">CreateMatchRequest</h2>
<!-- backwards compatibility -->
<a id="schemacreatematchrequest"></a>
<a id="schema_CreateMatchRequest"></a>
<a id="tocScreatematchrequest"></a>
<a id="tocscreatematchrequest"></a>

```json
{
  "tournamentId": "4a951104-9f98-4996-b388-a0ef2c00bb2a",
  "homeTeamId": "fb7b8236-8f4a-4255-b25d-a64d7c4d6968",
  "awayTeamId": "aa1734e3-668a-43b1-918b-ecab48ec02f9",
  "matchDate": "2019-08-24T14:15:22Z",
  "stage": 0,
  "venue": "string",
  "apiFootballId": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|tournamentId|string(uuid)|false|none|none|
|homeTeamId|string(uuid)|false|none|none|
|awayTeamId|string(uuid)|false|none|none|
|matchDate|string(date-time)|false|none|none|
|stage|[MatchStage](#schemamatchstage)|false|none|none|
|venue|string¦null|false|none|none|
|apiFootballId|integer(int32)¦null|false|none|none|

<h2 id="tocS_CreateTeamRequest">CreateTeamRequest</h2>
<!-- backwards compatibility -->
<a id="schemacreateteamrequest"></a>
<a id="schema_CreateTeamRequest"></a>
<a id="tocScreateteamrequest"></a>
<a id="tocscreateteamrequest"></a>

```json
{
  "tournamentId": "4a951104-9f98-4996-b388-a0ef2c00bb2a",
  "name": "string",
  "code": "string",
  "flagUrl": "string",
  "groupName": "string",
  "fifaRank": 0,
  "fifaPoints": 0.1,
  "apiFootballId": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|tournamentId|string(uuid)|false|none|none|
|name|string¦null|false|none|none|
|code|string¦null|false|none|none|
|flagUrl|string¦null|false|none|none|
|groupName|string¦null|false|none|none|
|fifaRank|integer(int32)¦null|false|none|none|
|fifaPoints|number(double)¦null|false|none|none|
|apiFootballId|integer(int32)¦null|false|none|none|

<h2 id="tocS_CreateTournamentCommand">CreateTournamentCommand</h2>
<!-- backwards compatibility -->
<a id="schemacreatetournamentcommand"></a>
<a id="schema_CreateTournamentCommand"></a>
<a id="tocScreatetournamentcommand"></a>
<a id="tocscreatetournamentcommand"></a>

```json
{
  "name": "string",
  "year": 0,
  "type": 0,
  "startDate": "2019-08-24T14:15:22Z",
  "endDate": "2019-08-24T14:15:22Z",
  "country": "string",
  "logoUrl": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string¦null|false|none|none|
|year|integer(int32)|false|none|none|
|type|[TournamentType](#schematournamenttype)|false|none|none|
|startDate|string(date-time)|false|none|none|
|endDate|string(date-time)|false|none|none|
|country|string¦null|false|none|none|
|logoUrl|string¦null|false|none|none|

<h2 id="tocS_CurrentUserResponse">CurrentUserResponse</h2>
<!-- backwards compatibility -->
<a id="schemacurrentuserresponse"></a>
<a id="schema_CurrentUserResponse"></a>
<a id="tocScurrentuserresponse"></a>
<a id="tocscurrentuserresponse"></a>

```json
{
  "userId": "2c4a230c-5085-4924-a3e1-25fb4fc5965b",
  "email": "string",
  "username": "string",
  "displayName": "string",
  "avatarUrl": "string",
  "bio": "string",
  "favoriteTeamId": "d03f4e26-a6b7-4158-9c97-87bb7dc42e8b",
  "favoriteTeamName": "string",
  "lastLoginAt": "2019-08-24T14:15:22Z",
  "role": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|userId|string(uuid)|false|none|none|
|email|string¦null|false|none|none|
|username|string¦null|false|none|none|
|displayName|string¦null|false|none|none|
|avatarUrl|string¦null|false|none|none|
|bio|string¦null|false|none|none|
|favoriteTeamId|string(uuid)¦null|false|none|none|
|favoriteTeamName|string¦null|false|none|none|
|lastLoginAt|string(date-time)|false|none|none|
|role|[UserRole](#schemauserrole)|false|none|none|

<h2 id="tocS_CurrentUserResponseResult">CurrentUserResponseResult</h2>
<!-- backwards compatibility -->
<a id="schemacurrentuserresponseresult"></a>
<a id="schema_CurrentUserResponseResult"></a>
<a id="tocScurrentuserresponseresult"></a>
<a id="tocscurrentuserresponseresult"></a>

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": {
    "userId": "2c4a230c-5085-4924-a3e1-25fb4fc5965b",
    "email": "string",
    "username": "string",
    "displayName": "string",
    "avatarUrl": "string",
    "bio": "string",
    "favoriteTeamId": "d03f4e26-a6b7-4158-9c97-87bb7dc42e8b",
    "favoriteTeamName": "string",
    "lastLoginAt": "2019-08-24T14:15:22Z",
    "role": 0
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|isSuccess|boolean|false|read-only|none|
|error|[Error](#schemaerror)|false|none|none|
|data|[CurrentUserResponse](#schemacurrentuserresponse)|false|none|none|

<h2 id="tocS_Error">Error</h2>
<!-- backwards compatibility -->
<a id="schemaerror"></a>
<a id="schema_Error"></a>
<a id="tocSerror"></a>
<a id="tocserror"></a>

```json
{
  "type": 1,
  "message": "string",
  "code": "string",
  "validationErrors": {
    "property1": [
      "string"
    ],
    "property2": [
      "string"
    ]
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|type|[ErrorType](#schemaerrortype)|false|none|none|
|message|string¦null|false|none|none|
|code|string¦null|false|none|none|
|validationErrors|object¦null|false|none|none|
|» **additionalProperties**|[string]¦null|false|none|none|

<h2 id="tocS_ErrorResponse">ErrorResponse</h2>
<!-- backwards compatibility -->
<a id="schemaerrorresponse"></a>
<a id="schema_ErrorResponse"></a>
<a id="tocSerrorresponse"></a>
<a id="tocserrorresponse"></a>

```json
{
  "type": "string",
  "title": "string",
  "status": 0,
  "errors": {
    "property1": [
      "string"
    ],
    "property2": [
      "string"
    ]
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|type|string¦null|false|none|none|
|title|string¦null|false|none|none|
|status|integer(int32)|false|none|none|
|errors|object¦null|false|none|none|
|» **additionalProperties**|[string]¦null|false|none|none|

<h2 id="tocS_ErrorType">ErrorType</h2>
<!-- backwards compatibility -->
<a id="schemaerrortype"></a>
<a id="schema_ErrorType"></a>
<a id="tocSerrortype"></a>
<a id="tocserrortype"></a>

```json
1

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|integer(int32)|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|*anonymous*|1|
|*anonymous*|2|
|*anonymous*|3|
|*anonymous*|4|
|*anonymous*|5|
|*anonymous*|6|
|*anonymous*|7|

<h2 id="tocS_GuidResult">GuidResult</h2>
<!-- backwards compatibility -->
<a id="schemaguidresult"></a>
<a id="schema_GuidResult"></a>
<a id="tocSguidresult"></a>
<a id="tocsguidresult"></a>

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": "808ac6e4-93ed-4040-85a5-6c71a2444e90"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|isSuccess|boolean|false|read-only|none|
|error|[Error](#schemaerror)|false|none|none|
|data|string(uuid)|false|read-only|none|

<h2 id="tocS_Int32Result">Int32Result</h2>
<!-- backwards compatibility -->
<a id="schemaint32result"></a>
<a id="schema_Int32Result"></a>
<a id="tocSint32result"></a>
<a id="tocsint32result"></a>

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|isSuccess|boolean|false|read-only|none|
|error|[Error](#schemaerror)|false|none|none|
|data|integer(int32)|false|read-only|none|

<h2 id="tocS_JoinLeagueRequest">JoinLeagueRequest</h2>
<!-- backwards compatibility -->
<a id="schemajoinleaguerequest"></a>
<a id="schema_JoinLeagueRequest"></a>
<a id="tocSjoinleaguerequest"></a>
<a id="tocsjoinleaguerequest"></a>

```json
{
  "inviteCode": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|inviteCode|string¦null|false|none|none|

<h2 id="tocS_LeagueDto">LeagueDto</h2>
<!-- backwards compatibility -->
<a id="schemaleaguedto"></a>
<a id="schema_LeagueDto"></a>
<a id="tocSleaguedto"></a>
<a id="tocsleaguedto"></a>

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "name": "string",
  "description": "string",
  "tournamentId": "4a951104-9f98-4996-b388-a0ef2c00bb2a",
  "ownerId": "4d206909-730f-409a-88f6-dcfaa8fc28cc",
  "inviteCode": "string",
  "isPublic": true,
  "isGlobal": true,
  "maxMembers": 0,
  "imageUrl": "string",
  "settings": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "leagueId": "58549e12-c6e6-4e03-99d1-6e916f71ce9a",
    "predictionMode": "string",
    "deadlineMinutes": 0,
    "pointsCorrectScore": 0,
    "pointsCorrectOutcome": 0,
    "pointsCorrectGoals": 0,
    "pointsRoundOf16Team": 0,
    "pointsQuarterFinalTeam": 0,
    "pointsSemiFinalTeam": 0,
    "pointsFinalTeam": 0,
    "pointsTopScorer": 0,
    "pointsWinner": 0,
    "pointsMostGoalsGroup": 0,
    "pointsMostConcededGroup": 0,
    "allowLateEdits": true
  },
  "members": [
    {
      "userId": "2c4a230c-5085-4924-a3e1-25fb4fc5965b",
      "username": "string",
      "avatarUrl": "string",
      "joinedAt": "2019-08-24T14:15:22Z",
      "isAdmin": true,
      "isMuted": true
    }
  ],
  "memberCount": 0,
  "myRank": 0,
  "myTotalPoints": 0,
  "isOwner": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|false|none|none|
|name|string¦null|false|none|none|
|description|string¦null|false|none|none|
|tournamentId|string(uuid)|false|none|none|
|ownerId|string(uuid)¦null|false|none|none|
|inviteCode|string¦null|false|none|none|
|isPublic|boolean|false|none|none|
|isGlobal|boolean|false|none|none|
|maxMembers|integer(int32)¦null|false|none|none|
|imageUrl|string¦null|false|none|none|
|settings|[LeagueSettingsDto](#schemaleaguesettingsdto)|false|none|none|
|members|[[LeagueMemberDto](#schemaleaguememberdto)]¦null|false|none|none|
|memberCount|integer(int32)|false|none|none|
|myRank|integer(int32)|false|none|none|
|myTotalPoints|integer(int32)|false|none|none|
|isOwner|boolean|false|none|none|

<h2 id="tocS_LeagueDtoResult">LeagueDtoResult</h2>
<!-- backwards compatibility -->
<a id="schemaleaguedtoresult"></a>
<a id="schema_LeagueDtoResult"></a>
<a id="tocSleaguedtoresult"></a>
<a id="tocsleaguedtoresult"></a>

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "name": "string",
    "description": "string",
    "tournamentId": "4a951104-9f98-4996-b388-a0ef2c00bb2a",
    "ownerId": "4d206909-730f-409a-88f6-dcfaa8fc28cc",
    "inviteCode": "string",
    "isPublic": true,
    "isGlobal": true,
    "maxMembers": 0,
    "imageUrl": "string",
    "settings": {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "leagueId": "58549e12-c6e6-4e03-99d1-6e916f71ce9a",
      "predictionMode": "string",
      "deadlineMinutes": 0,
      "pointsCorrectScore": 0,
      "pointsCorrectOutcome": 0,
      "pointsCorrectGoals": 0,
      "pointsRoundOf16Team": 0,
      "pointsQuarterFinalTeam": 0,
      "pointsSemiFinalTeam": 0,
      "pointsFinalTeam": 0,
      "pointsTopScorer": 0,
      "pointsWinner": 0,
      "pointsMostGoalsGroup": 0,
      "pointsMostConcededGroup": 0,
      "allowLateEdits": true
    },
    "members": [
      {
        "userId": "2c4a230c-5085-4924-a3e1-25fb4fc5965b",
        "username": "string",
        "avatarUrl": "string",
        "joinedAt": "2019-08-24T14:15:22Z",
        "isAdmin": true,
        "isMuted": true
      }
    ],
    "memberCount": 0,
    "myRank": 0,
    "myTotalPoints": 0,
    "isOwner": true
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|isSuccess|boolean|false|read-only|none|
|error|[Error](#schemaerror)|false|none|none|
|data|[LeagueDto](#schemaleaguedto)|false|none|none|

<h2 id="tocS_LeagueListDto">LeagueListDto</h2>
<!-- backwards compatibility -->
<a id="schemaleaguelistdto"></a>
<a id="schema_LeagueListDto"></a>
<a id="tocSleaguelistdto"></a>
<a id="tocsleaguelistdto"></a>

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "name": "string",
  "description": "string",
  "tournamentId": "4a951104-9f98-4996-b388-a0ef2c00bb2a",
  "ownerId": "4d206909-730f-409a-88f6-dcfaa8fc28cc",
  "inviteCode": "string",
  "isPublic": true,
  "isGlobal": true,
  "maxMembers": 0,
  "imageUrl": "string",
  "memberCount": 0,
  "myRank": 0,
  "myTotalPoints": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|false|none|none|
|name|string¦null|false|none|none|
|description|string¦null|false|none|none|
|tournamentId|string(uuid)|false|none|none|
|ownerId|string(uuid)¦null|false|none|none|
|inviteCode|string¦null|false|none|none|
|isPublic|boolean|false|none|none|
|isGlobal|boolean|false|none|none|
|maxMembers|integer(int32)¦null|false|none|none|
|imageUrl|string¦null|false|none|none|
|memberCount|integer(int32)|false|none|none|
|myRank|integer(int32)|false|none|none|
|myTotalPoints|integer(int32)|false|none|none|

<h2 id="tocS_LeagueListDtoIReadOnlyListResult">LeagueListDtoIReadOnlyListResult</h2>
<!-- backwards compatibility -->
<a id="schemaleaguelistdtoireadonlylistresult"></a>
<a id="schema_LeagueListDtoIReadOnlyListResult"></a>
<a id="tocSleaguelistdtoireadonlylistresult"></a>
<a id="tocsleaguelistdtoireadonlylistresult"></a>

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "name": "string",
      "description": "string",
      "tournamentId": "4a951104-9f98-4996-b388-a0ef2c00bb2a",
      "ownerId": "4d206909-730f-409a-88f6-dcfaa8fc28cc",
      "inviteCode": "string",
      "isPublic": true,
      "isGlobal": true,
      "maxMembers": 0,
      "imageUrl": "string",
      "memberCount": 0,
      "myRank": 0,
      "myTotalPoints": 0
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|isSuccess|boolean|false|read-only|none|
|error|[Error](#schemaerror)|false|none|none|
|data|[[LeagueListDto](#schemaleaguelistdto)]¦null|false|read-only|none|

<h2 id="tocS_LeagueMemberDto">LeagueMemberDto</h2>
<!-- backwards compatibility -->
<a id="schemaleaguememberdto"></a>
<a id="schema_LeagueMemberDto"></a>
<a id="tocSleaguememberdto"></a>
<a id="tocsleaguememberdto"></a>

```json
{
  "userId": "2c4a230c-5085-4924-a3e1-25fb4fc5965b",
  "username": "string",
  "avatarUrl": "string",
  "joinedAt": "2019-08-24T14:15:22Z",
  "isAdmin": true,
  "isMuted": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|userId|string(uuid)|false|none|none|
|username|string¦null|false|none|none|
|avatarUrl|string¦null|false|none|none|
|joinedAt|string(date-time)|false|none|none|
|isAdmin|boolean|false|none|none|
|isMuted|boolean|false|none|none|

<h2 id="tocS_LeagueSettingsDto">LeagueSettingsDto</h2>
<!-- backwards compatibility -->
<a id="schemaleaguesettingsdto"></a>
<a id="schema_LeagueSettingsDto"></a>
<a id="tocSleaguesettingsdto"></a>
<a id="tocsleaguesettingsdto"></a>

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "leagueId": "58549e12-c6e6-4e03-99d1-6e916f71ce9a",
  "predictionMode": "string",
  "deadlineMinutes": 0,
  "pointsCorrectScore": 0,
  "pointsCorrectOutcome": 0,
  "pointsCorrectGoals": 0,
  "pointsRoundOf16Team": 0,
  "pointsQuarterFinalTeam": 0,
  "pointsSemiFinalTeam": 0,
  "pointsFinalTeam": 0,
  "pointsTopScorer": 0,
  "pointsWinner": 0,
  "pointsMostGoalsGroup": 0,
  "pointsMostConcededGroup": 0,
  "allowLateEdits": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|false|none|none|
|leagueId|string(uuid)|false|none|none|
|predictionMode|string¦null|false|none|none|
|deadlineMinutes|integer(int32)|false|none|none|
|pointsCorrectScore|integer(int32)|false|none|none|
|pointsCorrectOutcome|integer(int32)|false|none|none|
|pointsCorrectGoals|integer(int32)|false|none|none|
|pointsRoundOf16Team|integer(int32)|false|none|none|
|pointsQuarterFinalTeam|integer(int32)|false|none|none|
|pointsSemiFinalTeam|integer(int32)|false|none|none|
|pointsFinalTeam|integer(int32)|false|none|none|
|pointsTopScorer|integer(int32)|false|none|none|
|pointsWinner|integer(int32)|false|none|none|
|pointsMostGoalsGroup|integer(int32)|false|none|none|
|pointsMostConcededGroup|integer(int32)|false|none|none|
|allowLateEdits|boolean|false|none|none|

<h2 id="tocS_LeagueSettingsDtoResult">LeagueSettingsDtoResult</h2>
<!-- backwards compatibility -->
<a id="schemaleaguesettingsdtoresult"></a>
<a id="schema_LeagueSettingsDtoResult"></a>
<a id="tocSleaguesettingsdtoresult"></a>
<a id="tocsleaguesettingsdtoresult"></a>

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "leagueId": "58549e12-c6e6-4e03-99d1-6e916f71ce9a",
    "predictionMode": "string",
    "deadlineMinutes": 0,
    "pointsCorrectScore": 0,
    "pointsCorrectOutcome": 0,
    "pointsCorrectGoals": 0,
    "pointsRoundOf16Team": 0,
    "pointsQuarterFinalTeam": 0,
    "pointsSemiFinalTeam": 0,
    "pointsFinalTeam": 0,
    "pointsTopScorer": 0,
    "pointsWinner": 0,
    "pointsMostGoalsGroup": 0,
    "pointsMostConcededGroup": 0,
    "allowLateEdits": true
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|isSuccess|boolean|false|read-only|none|
|error|[Error](#schemaerror)|false|none|none|
|data|[LeagueSettingsDto](#schemaleaguesettingsdto)|false|none|none|

<h2 id="tocS_LeagueStandingDto">LeagueStandingDto</h2>
<!-- backwards compatibility -->
<a id="schemaleaguestandingdto"></a>
<a id="schema_LeagueStandingDto"></a>
<a id="tocSleaguestandingdto"></a>
<a id="tocsleaguestandingdto"></a>

```json
{
  "userId": "2c4a230c-5085-4924-a3e1-25fb4fc5965b",
  "username": "string",
  "avatarUrl": "string",
  "rank": 0,
  "previousRank": 0,
  "rankChange": 0,
  "totalPoints": 0,
  "matchPoints": 0,
  "bonusPoints": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|userId|string(uuid)|false|none|none|
|username|string¦null|false|none|none|
|avatarUrl|string¦null|false|none|none|
|rank|integer(int32)|false|none|none|
|previousRank|integer(int32)¦null|false|none|none|
|rankChange|integer(int32)¦null|false|none|none|
|totalPoints|integer(int32)|false|none|none|
|matchPoints|integer(int32)|false|none|none|
|bonusPoints|integer(int32)|false|none|none|

<h2 id="tocS_LeagueStandingDtoIReadOnlyListResult">LeagueStandingDtoIReadOnlyListResult</h2>
<!-- backwards compatibility -->
<a id="schemaleaguestandingdtoireadonlylistresult"></a>
<a id="schema_LeagueStandingDtoIReadOnlyListResult"></a>
<a id="tocSleaguestandingdtoireadonlylistresult"></a>
<a id="tocsleaguestandingdtoireadonlylistresult"></a>

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": [
    {
      "userId": "2c4a230c-5085-4924-a3e1-25fb4fc5965b",
      "username": "string",
      "avatarUrl": "string",
      "rank": 0,
      "previousRank": 0,
      "rankChange": 0,
      "totalPoints": 0,
      "matchPoints": 0,
      "bonusPoints": 0
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|isSuccess|boolean|false|read-only|none|
|error|[Error](#schemaerror)|false|none|none|
|data|[[LeagueStandingDto](#schemaleaguestandingdto)]¦null|false|read-only|none|

<h2 id="tocS_MatchDetailDto">MatchDetailDto</h2>
<!-- backwards compatibility -->
<a id="schemamatchdetaildto"></a>
<a id="schema_MatchDetailDto"></a>
<a id="tocSmatchdetaildto"></a>
<a id="tocsmatchdetaildto"></a>

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "tournamentId": "4a951104-9f98-4996-b388-a0ef2c00bb2a",
  "homeTeamId": "fb7b8236-8f4a-4255-b25d-a64d7c4d6968",
  "homeTeam": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "tournamentId": "4a951104-9f98-4996-b388-a0ef2c00bb2a",
    "name": "string",
    "displayName": "string",
    "code": "string",
    "logoUrl": "string",
    "groupName": "string",
    "fifaRank": 0,
    "apiFootballId": 0
  },
  "awayTeamId": "aa1734e3-668a-43b1-918b-ecab48ec02f9",
  "awayTeam": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "tournamentId": "4a951104-9f98-4996-b388-a0ef2c00bb2a",
    "name": "string",
    "displayName": "string",
    "code": "string",
    "logoUrl": "string",
    "groupName": "string",
    "fifaRank": 0,
    "apiFootballId": 0
  },
  "matchDate": "2019-08-24T14:15:22Z",
  "stage": 0,
  "status": 0,
  "homeScore": 0,
  "awayScore": 0,
  "venue": "string",
  "updatedAt": "2019-08-24T14:15:22Z"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|false|none|none|
|tournamentId|string(uuid)|false|none|none|
|homeTeamId|string(uuid)|false|none|none|
|homeTeam|[TeamDto](#schemateamdto)|false|none|none|
|awayTeamId|string(uuid)|false|none|none|
|awayTeam|[TeamDto](#schemateamdto)|false|none|none|
|matchDate|string(date-time)|false|none|none|
|stage|[MatchStage](#schemamatchstage)|false|none|none|
|status|[MatchStatus](#schemamatchstatus)|false|none|none|
|homeScore|integer(int32)¦null|false|none|none|
|awayScore|integer(int32)¦null|false|none|none|
|venue|string¦null|false|none|none|
|updatedAt|string(date-time)¦null|false|none|none|

<h2 id="tocS_MatchDetailDtoResult">MatchDetailDtoResult</h2>
<!-- backwards compatibility -->
<a id="schemamatchdetaildtoresult"></a>
<a id="schema_MatchDetailDtoResult"></a>
<a id="tocSmatchdetaildtoresult"></a>
<a id="tocsmatchdetaildtoresult"></a>

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "tournamentId": "4a951104-9f98-4996-b388-a0ef2c00bb2a",
    "homeTeamId": "fb7b8236-8f4a-4255-b25d-a64d7c4d6968",
    "homeTeam": {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "tournamentId": "4a951104-9f98-4996-b388-a0ef2c00bb2a",
      "name": "string",
      "displayName": "string",
      "code": "string",
      "logoUrl": "string",
      "groupName": "string",
      "fifaRank": 0,
      "apiFootballId": 0
    },
    "awayTeamId": "aa1734e3-668a-43b1-918b-ecab48ec02f9",
    "awayTeam": {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "tournamentId": "4a951104-9f98-4996-b388-a0ef2c00bb2a",
      "name": "string",
      "displayName": "string",
      "code": "string",
      "logoUrl": "string",
      "groupName": "string",
      "fifaRank": 0,
      "apiFootballId": 0
    },
    "matchDate": "2019-08-24T14:15:22Z",
    "stage": 0,
    "status": 0,
    "homeScore": 0,
    "awayScore": 0,
    "venue": "string",
    "updatedAt": "2019-08-24T14:15:22Z"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|isSuccess|boolean|false|read-only|none|
|error|[Error](#schemaerror)|false|none|none|
|data|[MatchDetailDto](#schemamatchdetaildto)|false|none|none|

<h2 id="tocS_MatchListItemDto">MatchListItemDto</h2>
<!-- backwards compatibility -->
<a id="schemamatchlistitemdto"></a>
<a id="schema_MatchListItemDto"></a>
<a id="tocSmatchlistitemdto"></a>
<a id="tocsmatchlistitemdto"></a>

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "tournamentId": "4a951104-9f98-4996-b388-a0ef2c00bb2a",
  "homeTeamId": "fb7b8236-8f4a-4255-b25d-a64d7c4d6968",
  "homeTeamName": "string",
  "homeTeamLogoUrl": "string",
  "homeTeamFifaRank": 0,
  "awayTeamId": "aa1734e3-668a-43b1-918b-ecab48ec02f9",
  "awayTeamName": "string",
  "awayTeamLogoUrl": "string",
  "awayTeamFifaRank": 0,
  "groupName": "string",
  "venue": "string",
  "matchDate": "2019-08-24T14:15:22Z",
  "stage": 0,
  "status": 0,
  "homeScore": 0,
  "awayScore": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|false|none|none|
|tournamentId|string(uuid)|false|none|none|
|homeTeamId|string(uuid)|false|none|none|
|homeTeamName|string¦null|false|none|none|
|homeTeamLogoUrl|string¦null|false|none|none|
|homeTeamFifaRank|integer(int32)¦null|false|none|none|
|awayTeamId|string(uuid)|false|none|none|
|awayTeamName|string¦null|false|none|none|
|awayTeamLogoUrl|string¦null|false|none|none|
|awayTeamFifaRank|integer(int32)¦null|false|none|none|
|groupName|string¦null|false|none|none|
|venue|string¦null|false|none|none|
|matchDate|string(date-time)|false|none|none|
|stage|[MatchStage](#schemamatchstage)|false|none|none|
|status|[MatchStatus](#schemamatchstatus)|false|none|none|
|homeScore|integer(int32)¦null|false|none|none|
|awayScore|integer(int32)¦null|false|none|none|

<h2 id="tocS_MatchListItemDtoIReadOnlyListResult">MatchListItemDtoIReadOnlyListResult</h2>
<!-- backwards compatibility -->
<a id="schemamatchlistitemdtoireadonlylistresult"></a>
<a id="schema_MatchListItemDtoIReadOnlyListResult"></a>
<a id="tocSmatchlistitemdtoireadonlylistresult"></a>
<a id="tocsmatchlistitemdtoireadonlylistresult"></a>

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "tournamentId": "4a951104-9f98-4996-b388-a0ef2c00bb2a",
      "homeTeamId": "fb7b8236-8f4a-4255-b25d-a64d7c4d6968",
      "homeTeamName": "string",
      "homeTeamLogoUrl": "string",
      "homeTeamFifaRank": 0,
      "awayTeamId": "aa1734e3-668a-43b1-918b-ecab48ec02f9",
      "awayTeamName": "string",
      "awayTeamLogoUrl": "string",
      "awayTeamFifaRank": 0,
      "groupName": "string",
      "venue": "string",
      "matchDate": "2019-08-24T14:15:22Z",
      "stage": 0,
      "status": 0,
      "homeScore": 0,
      "awayScore": 0
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|isSuccess|boolean|false|read-only|none|
|error|[Error](#schemaerror)|false|none|none|
|data|[[MatchListItemDto](#schemamatchlistitemdto)]¦null|false|read-only|none|

<h2 id="tocS_MatchStage">MatchStage</h2>
<!-- backwards compatibility -->
<a id="schemamatchstage"></a>
<a id="schema_MatchStage"></a>
<a id="tocSmatchstage"></a>
<a id="tocsmatchstage"></a>

```json
0

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|integer(int32)|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|*anonymous*|0|
|*anonymous*|1|
|*anonymous*|2|
|*anonymous*|3|
|*anonymous*|4|

<h2 id="tocS_MatchStatus">MatchStatus</h2>
<!-- backwards compatibility -->
<a id="schemamatchstatus"></a>
<a id="schema_MatchStatus"></a>
<a id="tocSmatchstatus"></a>
<a id="tocsmatchstatus"></a>

```json
0

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|integer(int32)|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|*anonymous*|0|
|*anonymous*|1|
|*anonymous*|2|
|*anonymous*|3|
|*anonymous*|4|

<h2 id="tocS_MatchUpdateInfo">MatchUpdateInfo</h2>
<!-- backwards compatibility -->
<a id="schemamatchupdateinfo"></a>
<a id="schema_MatchUpdateInfo"></a>
<a id="tocSmatchupdateinfo"></a>
<a id="tocsmatchupdateinfo"></a>

```json
{
  "matchId": "685569fd-95e6-4335-9aa5-fdd22382bd9e",
  "homeTeam": "string",
  "awayTeam": "string",
  "oldStatus": "string",
  "newStatus": "string",
  "oldScore": "string",
  "newScore": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|matchId|string(uuid)|false|none|none|
|homeTeam|string¦null|false|none|none|
|awayTeam|string¦null|false|none|none|
|oldStatus|string¦null|false|none|none|
|newStatus|string¦null|false|none|none|
|oldScore|string¦null|false|none|none|
|newScore|string¦null|false|none|none|

<h2 id="tocS_MergeAction">MergeAction</h2>
<!-- backwards compatibility -->
<a id="schemamergeaction"></a>
<a id="schema_MergeAction"></a>
<a id="tocSmergeaction"></a>
<a id="tocsmergeaction"></a>

```json
{
  "oldTeamName": "string",
  "oldTeamId": "2cc91b4f-bb2c-4e92-8025-83da45bec7aa",
  "newTeamName": "string",
  "newTeamId": "e64af117-bcb1-4d41-a79b-76a519341754",
  "transferredDisplayName": "string",
  "transferredFifaRank": 0,
  "transferredFifaPoints": 0.1
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|oldTeamName|string¦null|false|none|none|
|oldTeamId|string(uuid)|false|none|none|
|newTeamName|string¦null|false|none|none|
|newTeamId|string(uuid)|false|none|none|
|transferredDisplayName|string¦null|false|none|none|
|transferredFifaRank|integer(int32)¦null|false|none|none|
|transferredFifaPoints|number(double)¦null|false|none|none|

<h2 id="tocS_MergeDuplicateTeamsResult">MergeDuplicateTeamsResult</h2>
<!-- backwards compatibility -->
<a id="schemamergeduplicateteamsresult"></a>
<a id="schema_MergeDuplicateTeamsResult"></a>
<a id="tocSmergeduplicateteamsresult"></a>
<a id="tocsmergeduplicateteamsresult"></a>

```json
{
  "teamsMerged": 0,
  "teamsDeleted": 0,
  "matchesUpdated": 0,
  "predictionsUpdated": 0,
  "favoritesUpdated": 0,
  "wasDryRun": true,
  "mergeActions": [
    {
      "oldTeamName": "string",
      "oldTeamId": "2cc91b4f-bb2c-4e92-8025-83da45bec7aa",
      "newTeamName": "string",
      "newTeamId": "e64af117-bcb1-4d41-a79b-76a519341754",
      "transferredDisplayName": "string",
      "transferredFifaRank": 0,
      "transferredFifaPoints": 0.1
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|teamsMerged|integer(int32)|false|none|none|
|teamsDeleted|integer(int32)|false|none|none|
|matchesUpdated|integer(int32)|false|none|none|
|predictionsUpdated|integer(int32)|false|none|none|
|favoritesUpdated|integer(int32)|false|none|none|
|wasDryRun|boolean|false|none|none|
|mergeActions|[[MergeAction](#schemamergeaction)]¦null|false|none|none|

<h2 id="tocS_MergeDuplicateTeamsResultResult">MergeDuplicateTeamsResultResult</h2>
<!-- backwards compatibility -->
<a id="schemamergeduplicateteamsresultresult"></a>
<a id="schema_MergeDuplicateTeamsResultResult"></a>
<a id="tocSmergeduplicateteamsresultresult"></a>
<a id="tocsmergeduplicateteamsresultresult"></a>

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": {
    "teamsMerged": 0,
    "teamsDeleted": 0,
    "matchesUpdated": 0,
    "predictionsUpdated": 0,
    "favoritesUpdated": 0,
    "wasDryRun": true,
    "mergeActions": [
      {
        "oldTeamName": "string",
        "oldTeamId": "2cc91b4f-bb2c-4e92-8025-83da45bec7aa",
        "newTeamName": "string",
        "newTeamId": "e64af117-bcb1-4d41-a79b-76a519341754",
        "transferredDisplayName": "string",
        "transferredFifaRank": 0,
        "transferredFifaPoints": 0.1
      }
    ]
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|isSuccess|boolean|false|read-only|none|
|error|[Error](#schemaerror)|false|none|none|
|data|[MergeDuplicateTeamsResult](#schemamergeduplicateteamsresult)|false|none|none|

<h2 id="tocS_PlayerDto">PlayerDto</h2>
<!-- backwards compatibility -->
<a id="schemaplayerdto"></a>
<a id="schema_PlayerDto"></a>
<a id="tocSplayerdto"></a>
<a id="tocsplayerdto"></a>

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "teamId": "a4ede8ba-7c0a-4485-8763-cbd9b282fbec",
  "name": "string",
  "firstName": "string",
  "lastName": "string",
  "number": 0,
  "position": "string",
  "photoUrl": "string",
  "dateOfBirth": "2019-08-24T14:15:22Z",
  "age": 0,
  "nationality": "string",
  "height": 0,
  "weight": 0,
  "injured": true,
  "apiFootballId": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|false|none|none|
|teamId|string(uuid)|false|none|none|
|name|string¦null|false|none|none|
|firstName|string¦null|false|none|none|
|lastName|string¦null|false|none|none|
|number|integer(int32)¦null|false|none|none|
|position|string¦null|false|none|none|
|photoUrl|string¦null|false|none|none|
|dateOfBirth|string(date-time)¦null|false|none|none|
|age|integer(int32)¦null|false|none|none|
|nationality|string¦null|false|none|none|
|height|integer(int32)¦null|false|none|none|
|weight|integer(int32)¦null|false|none|none|
|injured|boolean¦null|false|none|none|
|apiFootballId|integer(int32)¦null|false|none|none|

<h2 id="tocS_PlayerDtoIReadOnlyListResult">PlayerDtoIReadOnlyListResult</h2>
<!-- backwards compatibility -->
<a id="schemaplayerdtoireadonlylistresult"></a>
<a id="schema_PlayerDtoIReadOnlyListResult"></a>
<a id="tocSplayerdtoireadonlylistresult"></a>
<a id="tocsplayerdtoireadonlylistresult"></a>

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "teamId": "a4ede8ba-7c0a-4485-8763-cbd9b282fbec",
      "name": "string",
      "firstName": "string",
      "lastName": "string",
      "number": 0,
      "position": "string",
      "photoUrl": "string",
      "dateOfBirth": "2019-08-24T14:15:22Z",
      "age": 0,
      "nationality": "string",
      "height": 0,
      "weight": 0,
      "injured": true,
      "apiFootballId": 0
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|isSuccess|boolean|false|read-only|none|
|error|[Error](#schemaerror)|false|none|none|
|data|[[PlayerDto](#schemaplayerdto)]¦null|false|read-only|none|

<h2 id="tocS_PlayerWithTeamDto">PlayerWithTeamDto</h2>
<!-- backwards compatibility -->
<a id="schemaplayerwithteamdto"></a>
<a id="schema_PlayerWithTeamDto"></a>
<a id="tocSplayerwithteamdto"></a>
<a id="tocsplayerwithteamdto"></a>

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "teamId": "a4ede8ba-7c0a-4485-8763-cbd9b282fbec",
  "teamName": "string",
  "teamDisplayName": "string",
  "teamLogoUrl": "string",
  "name": "string",
  "firstName": "string",
  "lastName": "string",
  "number": 0,
  "position": "string",
  "photoUrl": "string",
  "dateOfBirth": "2019-08-24T14:15:22Z",
  "age": 0,
  "nationality": "string",
  "height": 0,
  "weight": 0,
  "injured": true,
  "apiFootballId": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|false|none|none|
|teamId|string(uuid)|false|none|none|
|teamName|string¦null|false|none|none|
|teamDisplayName|string¦null|false|none|none|
|teamLogoUrl|string¦null|false|none|none|
|name|string¦null|false|none|none|
|firstName|string¦null|false|none|none|
|lastName|string¦null|false|none|none|
|number|integer(int32)¦null|false|none|none|
|position|string¦null|false|none|none|
|photoUrl|string¦null|false|none|none|
|dateOfBirth|string(date-time)¦null|false|none|none|
|age|integer(int32)¦null|false|none|none|
|nationality|string¦null|false|none|none|
|height|integer(int32)¦null|false|none|none|
|weight|integer(int32)¦null|false|none|none|
|injured|boolean¦null|false|none|none|
|apiFootballId|integer(int32)¦null|false|none|none|

<h2 id="tocS_PlayerWithTeamDtoIReadOnlyListResult">PlayerWithTeamDtoIReadOnlyListResult</h2>
<!-- backwards compatibility -->
<a id="schemaplayerwithteamdtoireadonlylistresult"></a>
<a id="schema_PlayerWithTeamDtoIReadOnlyListResult"></a>
<a id="tocSplayerwithteamdtoireadonlylistresult"></a>
<a id="tocsplayerwithteamdtoireadonlylistresult"></a>

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "teamId": "a4ede8ba-7c0a-4485-8763-cbd9b282fbec",
      "teamName": "string",
      "teamDisplayName": "string",
      "teamLogoUrl": "string",
      "name": "string",
      "firstName": "string",
      "lastName": "string",
      "number": 0,
      "position": "string",
      "photoUrl": "string",
      "dateOfBirth": "2019-08-24T14:15:22Z",
      "age": 0,
      "nationality": "string",
      "height": 0,
      "weight": 0,
      "injured": true,
      "apiFootballId": 0
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|isSuccess|boolean|false|read-only|none|
|error|[Error](#schemaerror)|false|none|none|
|data|[[PlayerWithTeamDto](#schemaplayerwithteamdto)]¦null|false|read-only|none|

<h2 id="tocS_PlayerWithTeamDtoResult">PlayerWithTeamDtoResult</h2>
<!-- backwards compatibility -->
<a id="schemaplayerwithteamdtoresult"></a>
<a id="schema_PlayerWithTeamDtoResult"></a>
<a id="tocSplayerwithteamdtoresult"></a>
<a id="tocsplayerwithteamdtoresult"></a>

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "teamId": "a4ede8ba-7c0a-4485-8763-cbd9b282fbec",
    "teamName": "string",
    "teamDisplayName": "string",
    "teamLogoUrl": "string",
    "name": "string",
    "firstName": "string",
    "lastName": "string",
    "number": 0,
    "position": "string",
    "photoUrl": "string",
    "dateOfBirth": "2019-08-24T14:15:22Z",
    "age": 0,
    "nationality": "string",
    "height": 0,
    "weight": 0,
    "injured": true,
    "apiFootballId": 0
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|isSuccess|boolean|false|read-only|none|
|error|[Error](#schemaerror)|false|none|none|
|data|[PlayerWithTeamDto](#schemaplayerwithteamdto)|false|none|none|

<h2 id="tocS_PredictionDto">PredictionDto</h2>
<!-- backwards compatibility -->
<a id="schemapredictiondto"></a>
<a id="schema_PredictionDto"></a>
<a id="tocSpredictiondto"></a>
<a id="tocspredictiondto"></a>

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "userId": "2c4a230c-5085-4924-a3e1-25fb4fc5965b",
  "leagueId": "58549e12-c6e6-4e03-99d1-6e916f71ce9a",
  "matchId": "685569fd-95e6-4335-9aa5-fdd22382bd9e",
  "homeScore": 0,
  "awayScore": 0,
  "pointsEarned": 0,
  "createdAt": "2019-08-24T14:15:22Z",
  "updatedAt": "2019-08-24T14:15:22Z"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|false|none|none|
|userId|string(uuid)|false|none|none|
|leagueId|string(uuid)|false|none|none|
|matchId|string(uuid)|false|none|none|
|homeScore|integer(int32)|false|none|none|
|awayScore|integer(int32)|false|none|none|
|pointsEarned|integer(int32)¦null|false|none|none|
|createdAt|string(date-time)|false|none|none|
|updatedAt|string(date-time)¦null|false|none|none|

<h2 id="tocS_PredictionDtoListResult">PredictionDtoListResult</h2>
<!-- backwards compatibility -->
<a id="schemapredictiondtolistresult"></a>
<a id="schema_PredictionDtoListResult"></a>
<a id="tocSpredictiondtolistresult"></a>
<a id="tocspredictiondtolistresult"></a>

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "userId": "2c4a230c-5085-4924-a3e1-25fb4fc5965b",
      "leagueId": "58549e12-c6e6-4e03-99d1-6e916f71ce9a",
      "matchId": "685569fd-95e6-4335-9aa5-fdd22382bd9e",
      "homeScore": 0,
      "awayScore": 0,
      "pointsEarned": 0,
      "createdAt": "2019-08-24T14:15:22Z",
      "updatedAt": "2019-08-24T14:15:22Z"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|isSuccess|boolean|false|read-only|none|
|error|[Error](#schemaerror)|false|none|none|
|data|[[PredictionDto](#schemapredictiondto)]¦null|false|read-only|none|

<h2 id="tocS_PredictionDtoResult">PredictionDtoResult</h2>
<!-- backwards compatibility -->
<a id="schemapredictiondtoresult"></a>
<a id="schema_PredictionDtoResult"></a>
<a id="tocSpredictiondtoresult"></a>
<a id="tocspredictiondtoresult"></a>

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "userId": "2c4a230c-5085-4924-a3e1-25fb4fc5965b",
    "leagueId": "58549e12-c6e6-4e03-99d1-6e916f71ce9a",
    "matchId": "685569fd-95e6-4335-9aa5-fdd22382bd9e",
    "homeScore": 0,
    "awayScore": 0,
    "pointsEarned": 0,
    "createdAt": "2019-08-24T14:15:22Z",
    "updatedAt": "2019-08-24T14:15:22Z"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|isSuccess|boolean|false|read-only|none|
|error|[Error](#schemaerror)|false|none|none|
|data|[PredictionDto](#schemapredictiondto)|false|none|none|

<h2 id="tocS_PredictionResult">PredictionResult</h2>
<!-- backwards compatibility -->
<a id="schemapredictionresult"></a>
<a id="schema_PredictionResult"></a>
<a id="tocSpredictionresult"></a>
<a id="tocspredictionresult"></a>

```json
{
  "matchId": "685569fd-95e6-4335-9aa5-fdd22382bd9e",
  "predictionId": "07ef3e55-acee-4631-909a-2d5902a608e6",
  "success": true,
  "errorMessage": "string",
  "errorCode": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|matchId|string(uuid)|false|none|none|
|predictionId|string(uuid)¦null|false|none|none|
|success|boolean|false|none|none|
|errorMessage|string¦null|false|none|none|
|errorCode|string¦null|false|none|none|

<h2 id="tocS_RecalculateBonusQuestionResult">RecalculateBonusQuestionResult</h2>
<!-- backwards compatibility -->
<a id="schemarecalculatebonusquestionresult"></a>
<a id="schema_RecalculateBonusQuestionResult"></a>
<a id="tocSrecalculatebonusquestionresult"></a>
<a id="tocsrecalculatebonusquestionresult"></a>

```json
{
  "predictionsUpdated": 0,
  "correctPredictions": 0,
  "totalPointsAwarded": 0,
  "leaguesAffected": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|predictionsUpdated|integer(int32)|false|none|none|
|correctPredictions|integer(int32)|false|none|none|
|totalPointsAwarded|integer(int32)|false|none|none|
|leaguesAffected|integer(int32)|false|none|none|

<h2 id="tocS_RecalculateBonusQuestionResultResult">RecalculateBonusQuestionResultResult</h2>
<!-- backwards compatibility -->
<a id="schemarecalculatebonusquestionresultresult"></a>
<a id="schema_RecalculateBonusQuestionResultResult"></a>
<a id="tocSrecalculatebonusquestionresultresult"></a>
<a id="tocsrecalculatebonusquestionresultresult"></a>

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": {
    "predictionsUpdated": 0,
    "correctPredictions": 0,
    "totalPointsAwarded": 0,
    "leaguesAffected": 0
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|isSuccess|boolean|false|read-only|none|
|error|[Error](#schemaerror)|false|none|none|
|data|[RecalculateBonusQuestionResult](#schemarecalculatebonusquestionresult)|false|none|none|

<h2 id="tocS_RecalculateLeaguePredictionsResult">RecalculateLeaguePredictionsResult</h2>
<!-- backwards compatibility -->
<a id="schemarecalculateleaguepredictionsresult"></a>
<a id="schema_RecalculateLeaguePredictionsResult"></a>
<a id="tocSrecalculateleaguepredictionsresult"></a>
<a id="tocsrecalculateleaguepredictionsresult"></a>

```json
{
  "predictionsUpdated": 0,
  "totalPoints": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|predictionsUpdated|integer(int32)|false|none|none|
|totalPoints|integer(int32)|false|none|none|

<h2 id="tocS_RecalculateLeaguePredictionsResultResult">RecalculateLeaguePredictionsResultResult</h2>
<!-- backwards compatibility -->
<a id="schemarecalculateleaguepredictionsresultresult"></a>
<a id="schema_RecalculateLeaguePredictionsResultResult"></a>
<a id="tocSrecalculateleaguepredictionsresultresult"></a>
<a id="tocsrecalculateleaguepredictionsresultresult"></a>

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": {
    "predictionsUpdated": 0,
    "totalPoints": 0
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|isSuccess|boolean|false|read-only|none|
|error|[Error](#schemaerror)|false|none|none|
|data|[RecalculateLeaguePredictionsResult](#schemarecalculateleaguepredictionsresult)|false|none|none|

<h2 id="tocS_RecalculateMatchPointsResult">RecalculateMatchPointsResult</h2>
<!-- backwards compatibility -->
<a id="schemarecalculatematchpointsresult"></a>
<a id="schema_RecalculateMatchPointsResult"></a>
<a id="tocSrecalculatematchpointsresult"></a>
<a id="tocsrecalculatematchpointsresult"></a>

```json
{
  "predictionsUpdated": 0,
  "leaguesAffected": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|predictionsUpdated|integer(int32)|false|none|none|
|leaguesAffected|integer(int32)|false|none|none|

<h2 id="tocS_RecalculateMatchPointsResultResult">RecalculateMatchPointsResultResult</h2>
<!-- backwards compatibility -->
<a id="schemarecalculatematchpointsresultresult"></a>
<a id="schema_RecalculateMatchPointsResultResult"></a>
<a id="tocSrecalculatematchpointsresultresult"></a>
<a id="tocsrecalculatematchpointsresultresult"></a>

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": {
    "predictionsUpdated": 0,
    "leaguesAffected": 0
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|isSuccess|boolean|false|read-only|none|
|error|[Error](#schemaerror)|false|none|none|
|data|[RecalculateMatchPointsResult](#schemarecalculatematchpointsresult)|false|none|none|

<h2 id="tocS_RecalculateTournamentStandingsResult">RecalculateTournamentStandingsResult</h2>
<!-- backwards compatibility -->
<a id="schemarecalculatetournamentstandingsresult"></a>
<a id="schema_RecalculateTournamentStandingsResult"></a>
<a id="tocSrecalculatetournamentstandingsresult"></a>
<a id="tocsrecalculatetournamentstandingsresult"></a>

```json
{
  "leaguesUpdated": 0,
  "totalMembersUpdated": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|leaguesUpdated|integer(int32)|false|none|none|
|totalMembersUpdated|integer(int32)|false|none|none|

<h2 id="tocS_RecalculateTournamentStandingsResultResult">RecalculateTournamentStandingsResultResult</h2>
<!-- backwards compatibility -->
<a id="schemarecalculatetournamentstandingsresultresult"></a>
<a id="schema_RecalculateTournamentStandingsResultResult"></a>
<a id="tocSrecalculatetournamentstandingsresultresult"></a>
<a id="tocsrecalculatetournamentstandingsresultresult"></a>

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": {
    "leaguesUpdated": 0,
    "totalMembersUpdated": 0
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|isSuccess|boolean|false|read-only|none|
|error|[Error](#schemaerror)|false|none|none|
|data|[RecalculateTournamentStandingsResult](#schemarecalculatetournamentstandingsresult)|false|none|none|

<h2 id="tocS_ResolveBonusQuestionRequest">ResolveBonusQuestionRequest</h2>
<!-- backwards compatibility -->
<a id="schemaresolvebonusquestionrequest"></a>
<a id="schema_ResolveBonusQuestionRequest"></a>
<a id="tocSresolvebonusquestionrequest"></a>
<a id="tocsresolvebonusquestionrequest"></a>

```json
{
  "answerTeamId": "ab2250dd-c194-4fab-a78b-360f3b350150",
  "answerText": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|answerTeamId|string(uuid)¦null|false|none|none|
|answerText|string¦null|false|none|none|

<h2 id="tocS_StringResult">StringResult</h2>
<!-- backwards compatibility -->
<a id="schemastringresult"></a>
<a id="schema_StringResult"></a>
<a id="tocSstringresult"></a>
<a id="tocsstringresult"></a>

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|isSuccess|boolean|false|read-only|none|
|error|[Error](#schemaerror)|false|none|none|
|data|string¦null|false|read-only|none|

<h2 id="tocS_SubmitBonusPredictionRequest">SubmitBonusPredictionRequest</h2>
<!-- backwards compatibility -->
<a id="schemasubmitbonuspredictionrequest"></a>
<a id="schema_SubmitBonusPredictionRequest"></a>
<a id="tocSsubmitbonuspredictionrequest"></a>
<a id="tocssubmitbonuspredictionrequest"></a>

```json
{
  "leagueId": "58549e12-c6e6-4e03-99d1-6e916f71ce9a",
  "bonusQuestionId": "a0b61934-6fef-4d97-866d-54f4b60aee83",
  "answerTeamId": "ab2250dd-c194-4fab-a78b-360f3b350150",
  "answerText": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|leagueId|string(uuid)|false|none|none|
|bonusQuestionId|string(uuid)|false|none|none|
|answerTeamId|string(uuid)¦null|false|none|none|
|answerText|string¦null|false|none|none|

<h2 id="tocS_SubmitPredictionRequest">SubmitPredictionRequest</h2>
<!-- backwards compatibility -->
<a id="schemasubmitpredictionrequest"></a>
<a id="schema_SubmitPredictionRequest"></a>
<a id="tocSsubmitpredictionrequest"></a>
<a id="tocssubmitpredictionrequest"></a>

```json
{
  "leagueId": "58549e12-c6e6-4e03-99d1-6e916f71ce9a",
  "matchId": "685569fd-95e6-4335-9aa5-fdd22382bd9e",
  "homeScore": 0,
  "awayScore": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|leagueId|string(uuid)|false|none|none|
|matchId|string(uuid)|false|none|none|
|homeScore|integer(int32)|false|none|none|
|awayScore|integer(int32)|false|none|none|

<h2 id="tocS_SyncGroupStandingsResult">SyncGroupStandingsResult</h2>
<!-- backwards compatibility -->
<a id="schemasyncgroupstandingsresult"></a>
<a id="schema_SyncGroupStandingsResult"></a>
<a id="tocSsyncgroupstandingsresult"></a>
<a id="tocssyncgroupstandingsresult"></a>

```json
{
  "groupsCreated": 0,
  "groupsUpdated": 0,
  "teamsAssignedToGroups": 0,
  "standingsUpserted": 0,
  "warnings": [
    "string"
  ],
  "syncedAt": "2019-08-24T14:15:22Z"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|groupsCreated|integer(int32)|false|none|none|
|groupsUpdated|integer(int32)|false|none|none|
|teamsAssignedToGroups|integer(int32)|false|none|none|
|standingsUpserted|integer(int32)|false|none|none|
|warnings|[string]¦null|false|none|none|
|syncedAt|string(date-time)|false|none|none|

<h2 id="tocS_SyncGroupStandingsResultResult">SyncGroupStandingsResultResult</h2>
<!-- backwards compatibility -->
<a id="schemasyncgroupstandingsresultresult"></a>
<a id="schema_SyncGroupStandingsResultResult"></a>
<a id="tocSsyncgroupstandingsresultresult"></a>
<a id="tocssyncgroupstandingsresultresult"></a>

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": {
    "groupsCreated": 0,
    "groupsUpdated": 0,
    "teamsAssignedToGroups": 0,
    "standingsUpserted": 0,
    "warnings": [
      "string"
    ],
    "syncedAt": "2019-08-24T14:15:22Z"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|isSuccess|boolean|false|read-only|none|
|error|[Error](#schemaerror)|false|none|none|
|data|[SyncGroupStandingsResult](#schemasyncgroupstandingsresult)|false|none|none|

<h2 id="tocS_SyncMatchLineupsResult">SyncMatchLineupsResult</h2>
<!-- backwards compatibility -->
<a id="schemasyncmatchlineupsresult"></a>
<a id="schema_SyncMatchLineupsResult"></a>
<a id="tocSsyncmatchlineupsresult"></a>
<a id="tocssyncmatchlineupsresult"></a>

```json
{
  "success": true,
  "lineupsAvailable": true,
  "teamsWithLineups": 0,
  "fetchedAt": "2019-08-24T14:15:22Z",
  "message": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|success|boolean|false|none|none|
|lineupsAvailable|boolean|false|none|none|
|teamsWithLineups|integer(int32)|false|none|none|
|fetchedAt|string(date-time)¦null|false|none|none|
|message|string¦null|false|none|none|

<h2 id="tocS_SyncMatchLineupsResultResult">SyncMatchLineupsResultResult</h2>
<!-- backwards compatibility -->
<a id="schemasyncmatchlineupsresultresult"></a>
<a id="schema_SyncMatchLineupsResultResult"></a>
<a id="tocSsyncmatchlineupsresultresult"></a>
<a id="tocssyncmatchlineupsresultresult"></a>

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": {
    "success": true,
    "lineupsAvailable": true,
    "teamsWithLineups": 0,
    "fetchedAt": "2019-08-24T14:15:22Z",
    "message": "string"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|isSuccess|boolean|false|read-only|none|
|error|[Error](#schemaerror)|false|none|none|
|data|[SyncMatchLineupsResult](#schemasyncmatchlineupsresult)|false|none|none|

<h2 id="tocS_SyncTeamSquadsResult">SyncTeamSquadsResult</h2>
<!-- backwards compatibility -->
<a id="schemasyncteamsquadsresult"></a>
<a id="schema_SyncTeamSquadsResult"></a>
<a id="tocSsyncteamsquadsresult"></a>
<a id="tocssyncteamsquadsresult"></a>

```json
{
  "teamsProcessed": 0,
  "teamsSkipped": 0,
  "playersCreated": 0,
  "playersUpdated": 0,
  "warnings": [
    "string"
  ],
  "syncedAt": "2019-08-24T14:15:22Z"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|teamsProcessed|integer(int32)|false|none|none|
|teamsSkipped|integer(int32)|false|none|none|
|playersCreated|integer(int32)|false|none|none|
|playersUpdated|integer(int32)|false|none|none|
|warnings|[string]¦null|false|none|none|
|syncedAt|string(date-time)|false|none|none|

<h2 id="tocS_SyncTeamSquadsResultResult">SyncTeamSquadsResultResult</h2>
<!-- backwards compatibility -->
<a id="schemasyncteamsquadsresultresult"></a>
<a id="schema_SyncTeamSquadsResultResult"></a>
<a id="tocSsyncteamsquadsresultresult"></a>
<a id="tocssyncteamsquadsresultresult"></a>

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": {
    "teamsProcessed": 0,
    "teamsSkipped": 0,
    "playersCreated": 0,
    "playersUpdated": 0,
    "warnings": [
      "string"
    ],
    "syncedAt": "2019-08-24T14:15:22Z"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|isSuccess|boolean|false|read-only|none|
|error|[Error](#schemaerror)|false|none|none|
|data|[SyncTeamSquadsResult](#schemasyncteamsquadsresult)|false|none|none|

<h2 id="tocS_SyncTournamentBaselineResult">SyncTournamentBaselineResult</h2>
<!-- backwards compatibility -->
<a id="schemasynctournamentbaselineresult"></a>
<a id="schema_SyncTournamentBaselineResult"></a>
<a id="tocSsynctournamentbaselineresult"></a>
<a id="tocssynctournamentbaselineresult"></a>

```json
{
  "teamsUpdated": 0,
  "teamsCreated": 0,
  "teamsUnmapped": 0,
  "venuesUpserted": 0,
  "matchesUpserted": 0,
  "matchesLinked": 0,
  "matchesSkipped": 0,
  "unmappedTeams": [
    "string"
  ],
  "warnings": [
    "string"
  ],
  "syncedAt": "2019-08-24T14:15:22Z"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|teamsUpdated|integer(int32)|false|none|none|
|teamsCreated|integer(int32)|false|none|none|
|teamsUnmapped|integer(int32)|false|none|none|
|venuesUpserted|integer(int32)|false|none|none|
|matchesUpserted|integer(int32)|false|none|none|
|matchesLinked|integer(int32)|false|none|none|
|matchesSkipped|integer(int32)|false|none|none|
|unmappedTeams|[string]¦null|false|none|none|
|warnings|[string]¦null|false|none|none|
|syncedAt|string(date-time)|false|none|none|

<h2 id="tocS_SyncTournamentBaselineResultResult">SyncTournamentBaselineResultResult</h2>
<!-- backwards compatibility -->
<a id="schemasynctournamentbaselineresultresult"></a>
<a id="schema_SyncTournamentBaselineResultResult"></a>
<a id="tocSsynctournamentbaselineresultresult"></a>
<a id="tocssynctournamentbaselineresultresult"></a>

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": {
    "teamsUpdated": 0,
    "teamsCreated": 0,
    "teamsUnmapped": 0,
    "venuesUpserted": 0,
    "matchesUpserted": 0,
    "matchesLinked": 0,
    "matchesSkipped": 0,
    "unmappedTeams": [
      "string"
    ],
    "warnings": [
      "string"
    ],
    "syncedAt": "2019-08-24T14:15:22Z"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|isSuccess|boolean|false|read-only|none|
|error|[Error](#schemaerror)|false|none|none|
|data|[SyncTournamentBaselineResult](#schemasynctournamentbaselineresult)|false|none|none|

<h2 id="tocS_SyncTournamentResultsResult">SyncTournamentResultsResult</h2>
<!-- backwards compatibility -->
<a id="schemasynctournamentresultsresult"></a>
<a id="schema_SyncTournamentResultsResult"></a>
<a id="tocSsynctournamentresultsresult"></a>
<a id="tocssynctournamentresultsresult"></a>

```json
{
  "matchesUpdated": 0,
  "matchesUnchanged": 0,
  "matchesNotFound": 0,
  "apiCallsMade": 0,
  "updates": [
    {
      "matchId": "685569fd-95e6-4335-9aa5-fdd22382bd9e",
      "homeTeam": "string",
      "awayTeam": "string",
      "oldStatus": "string",
      "newStatus": "string",
      "oldScore": "string",
      "newScore": "string"
    }
  ],
  "warnings": [
    "string"
  ],
  "syncedAt": "2019-08-24T14:15:22Z"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|matchesUpdated|integer(int32)|false|none|none|
|matchesUnchanged|integer(int32)|false|none|none|
|matchesNotFound|integer(int32)|false|none|none|
|apiCallsMade|integer(int32)|false|none|none|
|updates|[[MatchUpdateInfo](#schemamatchupdateinfo)]¦null|false|none|none|
|warnings|[string]¦null|false|none|none|
|syncedAt|string(date-time)|false|none|none|

<h2 id="tocS_SyncTournamentResultsResultResult">SyncTournamentResultsResultResult</h2>
<!-- backwards compatibility -->
<a id="schemasynctournamentresultsresultresult"></a>
<a id="schema_SyncTournamentResultsResultResult"></a>
<a id="tocSsynctournamentresultsresultresult"></a>
<a id="tocssynctournamentresultsresultresult"></a>

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": {
    "matchesUpdated": 0,
    "matchesUnchanged": 0,
    "matchesNotFound": 0,
    "apiCallsMade": 0,
    "updates": [
      {
        "matchId": "685569fd-95e6-4335-9aa5-fdd22382bd9e",
        "homeTeam": "string",
        "awayTeam": "string",
        "oldStatus": "string",
        "newStatus": "string",
        "oldScore": "string",
        "newScore": "string"
      }
    ],
    "warnings": [
      "string"
    ],
    "syncedAt": "2019-08-24T14:15:22Z"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|isSuccess|boolean|false|read-only|none|
|error|[Error](#schemaerror)|false|none|none|
|data|[SyncTournamentResultsResult](#schemasynctournamentresultsresult)|false|none|none|

<h2 id="tocS_TeamDto">TeamDto</h2>
<!-- backwards compatibility -->
<a id="schemateamdto"></a>
<a id="schema_TeamDto"></a>
<a id="tocSteamdto"></a>
<a id="tocsteamdto"></a>

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "tournamentId": "4a951104-9f98-4996-b388-a0ef2c00bb2a",
  "name": "string",
  "displayName": "string",
  "code": "string",
  "logoUrl": "string",
  "groupName": "string",
  "fifaRank": 0,
  "apiFootballId": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|false|none|none|
|tournamentId|string(uuid)|false|none|none|
|name|string¦null|false|none|none|
|displayName|string¦null|false|none|none|
|code|string¦null|false|none|none|
|logoUrl|string¦null|false|none|none|
|groupName|string¦null|false|none|none|
|fifaRank|integer(int32)¦null|false|none|none|
|apiFootballId|integer(int32)¦null|false|none|none|

<h2 id="tocS_TeamDtoIReadOnlyListResult">TeamDtoIReadOnlyListResult</h2>
<!-- backwards compatibility -->
<a id="schemateamdtoireadonlylistresult"></a>
<a id="schema_TeamDtoIReadOnlyListResult"></a>
<a id="tocSteamdtoireadonlylistresult"></a>
<a id="tocsteamdtoireadonlylistresult"></a>

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "tournamentId": "4a951104-9f98-4996-b388-a0ef2c00bb2a",
      "name": "string",
      "displayName": "string",
      "code": "string",
      "logoUrl": "string",
      "groupName": "string",
      "fifaRank": 0,
      "apiFootballId": 0
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|isSuccess|boolean|false|read-only|none|
|error|[Error](#schemaerror)|false|none|none|
|data|[[TeamDto](#schemateamdto)]¦null|false|read-only|none|

<h2 id="tocS_TeamDtoResult">TeamDtoResult</h2>
<!-- backwards compatibility -->
<a id="schemateamdtoresult"></a>
<a id="schema_TeamDtoResult"></a>
<a id="tocSteamdtoresult"></a>
<a id="tocsteamdtoresult"></a>

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "tournamentId": "4a951104-9f98-4996-b388-a0ef2c00bb2a",
    "name": "string",
    "displayName": "string",
    "code": "string",
    "logoUrl": "string",
    "groupName": "string",
    "fifaRank": 0,
    "apiFootballId": 0
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|isSuccess|boolean|false|read-only|none|
|error|[Error](#schemaerror)|false|none|none|
|data|[TeamDto](#schemateamdto)|false|none|none|

<h2 id="tocS_TournamentDto">TournamentDto</h2>
<!-- backwards compatibility -->
<a id="schematournamentdto"></a>
<a id="schema_TournamentDto"></a>
<a id="tocStournamentdto"></a>
<a id="tocstournamentdto"></a>

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "name": "string",
  "year": 0,
  "type": 0,
  "startDate": "2019-08-24T14:15:22Z",
  "endDate": "2019-08-24T14:15:22Z",
  "country": "string",
  "logoUrl": "string",
  "isActive": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|false|none|none|
|name|string¦null|false|none|none|
|year|integer(int32)|false|none|none|
|type|[TournamentType](#schematournamenttype)|false|none|none|
|startDate|string(date-time)|false|none|none|
|endDate|string(date-time)|false|none|none|
|country|string¦null|false|none|none|
|logoUrl|string¦null|false|none|none|
|isActive|boolean|false|none|none|

<h2 id="tocS_TournamentDtoIReadOnlyListResult">TournamentDtoIReadOnlyListResult</h2>
<!-- backwards compatibility -->
<a id="schematournamentdtoireadonlylistresult"></a>
<a id="schema_TournamentDtoIReadOnlyListResult"></a>
<a id="tocStournamentdtoireadonlylistresult"></a>
<a id="tocstournamentdtoireadonlylistresult"></a>

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "name": "string",
      "year": 0,
      "type": 0,
      "startDate": "2019-08-24T14:15:22Z",
      "endDate": "2019-08-24T14:15:22Z",
      "country": "string",
      "logoUrl": "string",
      "isActive": true
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|isSuccess|boolean|false|read-only|none|
|error|[Error](#schemaerror)|false|none|none|
|data|[[TournamentDto](#schematournamentdto)]¦null|false|read-only|none|

<h2 id="tocS_TournamentDtoResult">TournamentDtoResult</h2>
<!-- backwards compatibility -->
<a id="schematournamentdtoresult"></a>
<a id="schema_TournamentDtoResult"></a>
<a id="tocStournamentdtoresult"></a>
<a id="tocstournamentdtoresult"></a>

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "name": "string",
    "year": 0,
    "type": 0,
    "startDate": "2019-08-24T14:15:22Z",
    "endDate": "2019-08-24T14:15:22Z",
    "country": "string",
    "logoUrl": "string",
    "isActive": true
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|isSuccess|boolean|false|read-only|none|
|error|[Error](#schemaerror)|false|none|none|
|data|[TournamentDto](#schematournamentdto)|false|none|none|

<h2 id="tocS_TournamentType">TournamentType</h2>
<!-- backwards compatibility -->
<a id="schematournamenttype"></a>
<a id="schema_TournamentType"></a>
<a id="tocStournamenttype"></a>
<a id="tocstournamenttype"></a>

```json
0

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|integer(int32)|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|*anonymous*|0|
|*anonymous*|1|
|*anonymous*|2|
|*anonymous*|3|

<h2 id="tocS_UpdateAdminLeagueRequest">UpdateAdminLeagueRequest</h2>
<!-- backwards compatibility -->
<a id="schemaupdateadminleaguerequest"></a>
<a id="schema_UpdateAdminLeagueRequest"></a>
<a id="tocSupdateadminleaguerequest"></a>
<a id="tocsupdateadminleaguerequest"></a>

```json
{
  "name": "string",
  "description": "string",
  "isPublic": true,
  "isGlobal": true,
  "maxMembers": 0,
  "imageUrl": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string¦null|false|none|none|
|description|string¦null|false|none|none|
|isPublic|boolean¦null|false|none|none|
|isGlobal|boolean¦null|false|none|none|
|maxMembers|integer(int32)¦null|false|none|none|
|imageUrl|string¦null|false|none|none|

<h2 id="tocS_UpdateAdminUserRequest">UpdateAdminUserRequest</h2>
<!-- backwards compatibility -->
<a id="schemaupdateadminuserrequest"></a>
<a id="schema_UpdateAdminUserRequest"></a>
<a id="tocSupdateadminuserrequest"></a>
<a id="tocsupdateadminuserrequest"></a>

```json
{
  "username": "string",
  "displayName": "string",
  "email": "string",
  "bio": "string",
  "avatarUrl": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|username|string¦null|false|none|none|
|displayName|string¦null|false|none|none|
|email|string¦null|false|none|none|
|bio|string¦null|false|none|none|
|avatarUrl|string¦null|false|none|none|

<h2 id="tocS_UpdateBonusQuestionRequest">UpdateBonusQuestionRequest</h2>
<!-- backwards compatibility -->
<a id="schemaupdatebonusquestionrequest"></a>
<a id="schema_UpdateBonusQuestionRequest"></a>
<a id="tocSupdatebonusquestionrequest"></a>
<a id="tocsupdatebonusquestionrequest"></a>

```json
{
  "questionType": 0,
  "question": "string",
  "points": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|questionType|[BonusQuestionType](#schemabonusquestiontype)|false|none|none|
|question|string¦null|false|none|none|
|points|integer(int32)¦null|false|none|none|

<h2 id="tocS_UpdateLeagueMemberRequest">UpdateLeagueMemberRequest</h2>
<!-- backwards compatibility -->
<a id="schemaupdateleaguememberrequest"></a>
<a id="schema_UpdateLeagueMemberRequest"></a>
<a id="tocSupdateleaguememberrequest"></a>
<a id="tocsupdateleaguememberrequest"></a>

```json
{
  "isAdmin": true,
  "isMuted": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|isAdmin|boolean¦null|false|none|none|
|isMuted|boolean¦null|false|none|none|

<h2 id="tocS_UpdateLeagueSettingsRequest">UpdateLeagueSettingsRequest</h2>
<!-- backwards compatibility -->
<a id="schemaupdateleaguesettingsrequest"></a>
<a id="schema_UpdateLeagueSettingsRequest"></a>
<a id="tocSupdateleaguesettingsrequest"></a>
<a id="tocsupdateleaguesettingsrequest"></a>

```json
{
  "predictionMode": "string",
  "deadlineMinutes": 0,
  "pointsCorrectScore": 0,
  "pointsCorrectOutcome": 0,
  "pointsCorrectGoals": 0,
  "pointsRoundOf16Team": 0,
  "pointsQuarterFinalTeam": 0,
  "pointsSemiFinalTeam": 0,
  "pointsFinalTeam": 0,
  "pointsTopScorer": 0,
  "pointsWinner": 0,
  "pointsMostGoalsGroup": 0,
  "pointsMostConcededGroup": 0,
  "allowLateEdits": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|predictionMode|string¦null|false|none|none|
|deadlineMinutes|integer(int32)|false|none|none|
|pointsCorrectScore|integer(int32)|false|none|none|
|pointsCorrectOutcome|integer(int32)|false|none|none|
|pointsCorrectGoals|integer(int32)|false|none|none|
|pointsRoundOf16Team|integer(int32)|false|none|none|
|pointsQuarterFinalTeam|integer(int32)|false|none|none|
|pointsSemiFinalTeam|integer(int32)|false|none|none|
|pointsFinalTeam|integer(int32)|false|none|none|
|pointsTopScorer|integer(int32)|false|none|none|
|pointsWinner|integer(int32)|false|none|none|
|pointsMostGoalsGroup|integer(int32)|false|none|none|
|pointsMostConcededGroup|integer(int32)|false|none|none|
|allowLateEdits|boolean|false|none|none|

<h2 id="tocS_UpdateMatchRequest">UpdateMatchRequest</h2>
<!-- backwards compatibility -->
<a id="schemaupdatematchrequest"></a>
<a id="schema_UpdateMatchRequest"></a>
<a id="tocSupdatematchrequest"></a>
<a id="tocsupdatematchrequest"></a>

```json
{
  "matchDate": "2019-08-24T14:15:22Z",
  "stage": 0,
  "status": 0,
  "venue": "string",
  "apiFootballId": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|matchDate|string(date-time)¦null|false|none|none|
|stage|[MatchStage](#schemamatchstage)|false|none|none|
|status|[MatchStatus](#schemamatchstatus)|false|none|none|
|venue|string¦null|false|none|none|
|apiFootballId|integer(int32)¦null|false|none|none|

<h2 id="tocS_UpdateMatchResultRequest">UpdateMatchResultRequest</h2>
<!-- backwards compatibility -->
<a id="schemaupdatematchresultrequest"></a>
<a id="schema_UpdateMatchResultRequest"></a>
<a id="tocSupdatematchresultrequest"></a>
<a id="tocsupdatematchresultrequest"></a>

```json
{
  "homeScore": 0,
  "awayScore": 0,
  "status": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|homeScore|integer(int32)¦null|false|none|none|
|awayScore|integer(int32)¦null|false|none|none|
|status|[MatchStatus](#schemamatchstatus)|false|none|none|

<h2 id="tocS_UpdatePredictionRequest">UpdatePredictionRequest</h2>
<!-- backwards compatibility -->
<a id="schemaupdatepredictionrequest"></a>
<a id="schema_UpdatePredictionRequest"></a>
<a id="tocSupdatepredictionrequest"></a>
<a id="tocsupdatepredictionrequest"></a>

```json
{
  "homeScore": 0,
  "awayScore": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|homeScore|integer(int32)|false|none|none|
|awayScore|integer(int32)|false|none|none|

<h2 id="tocS_UpdateProfileRequest">UpdateProfileRequest</h2>
<!-- backwards compatibility -->
<a id="schemaupdateprofilerequest"></a>
<a id="schema_UpdateProfileRequest"></a>
<a id="tocSupdateprofilerequest"></a>
<a id="tocsupdateprofilerequest"></a>

```json
{
  "displayName": "string",
  "bio": "string",
  "favoriteTeamId": "d03f4e26-a6b7-4158-9c97-87bb7dc42e8b"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|displayName|string¦null|false|none|none|
|bio|string¦null|false|none|none|
|favoriteTeamId|string(uuid)¦null|false|none|none|

<h2 id="tocS_UpdateTeamRequest">UpdateTeamRequest</h2>
<!-- backwards compatibility -->
<a id="schemaupdateteamrequest"></a>
<a id="schema_UpdateTeamRequest"></a>
<a id="tocSupdateteamrequest"></a>
<a id="tocsupdateteamrequest"></a>

```json
{
  "name": "string",
  "code": "string",
  "flagUrl": "string",
  "groupName": "string",
  "fifaRank": 0,
  "fifaPoints": 0.1,
  "apiFootballId": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string¦null|false|none|none|
|code|string¦null|false|none|none|
|flagUrl|string¦null|false|none|none|
|groupName|string¦null|false|none|none|
|fifaRank|integer(int32)¦null|false|none|none|
|fifaPoints|number(double)¦null|false|none|none|
|apiFootballId|integer(int32)¦null|false|none|none|

<h2 id="tocS_UpdateTournamentRequest">UpdateTournamentRequest</h2>
<!-- backwards compatibility -->
<a id="schemaupdatetournamentrequest"></a>
<a id="schema_UpdateTournamentRequest"></a>
<a id="tocSupdatetournamentrequest"></a>
<a id="tocsupdatetournamentrequest"></a>

```json
{
  "name": "string",
  "year": 0,
  "type": 0,
  "startDate": "2019-08-24T14:15:22Z",
  "endDate": "2019-08-24T14:15:22Z",
  "logoUrl": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string¦null|false|none|none|
|year|integer(int32)¦null|false|none|none|
|type|[TournamentType](#schematournamenttype)|false|none|none|
|startDate|string(date-time)¦null|false|none|none|
|endDate|string(date-time)¦null|false|none|none|
|logoUrl|string¦null|false|none|none|

<h2 id="tocS_UpdateUserRoleRequest">UpdateUserRoleRequest</h2>
<!-- backwards compatibility -->
<a id="schemaupdateuserrolerequest"></a>
<a id="schema_UpdateUserRoleRequest"></a>
<a id="tocSupdateuserrolerequest"></a>
<a id="tocsupdateuserrolerequest"></a>

```json
{
  "role": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|role|[UserRole](#schemauserrole)|false|none|none|

<h2 id="tocS_UserProfileDto">UserProfileDto</h2>
<!-- backwards compatibility -->
<a id="schemauserprofiledto"></a>
<a id="schema_UserProfileDto"></a>
<a id="tocSuserprofiledto"></a>
<a id="tocsuserprofiledto"></a>

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "username": "string",
  "displayName": "string",
  "avatarUrl": "string",
  "bio": "string",
  "favoriteTeamId": "d03f4e26-a6b7-4158-9c97-87bb7dc42e8b",
  "favoriteTeamName": "string",
  "createdAt": "2019-08-24T14:15:22Z",
  "updatedAt": "2019-08-24T14:15:22Z"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|false|none|none|
|username|string¦null|false|none|none|
|displayName|string¦null|false|none|none|
|avatarUrl|string¦null|false|none|none|
|bio|string¦null|false|none|none|
|favoriteTeamId|string(uuid)¦null|false|none|none|
|favoriteTeamName|string¦null|false|none|none|
|createdAt|string(date-time)|false|none|none|
|updatedAt|string(date-time)¦null|false|none|none|

<h2 id="tocS_UserProfileDtoResult">UserProfileDtoResult</h2>
<!-- backwards compatibility -->
<a id="schemauserprofiledtoresult"></a>
<a id="schema_UserProfileDtoResult"></a>
<a id="tocSuserprofiledtoresult"></a>
<a id="tocsuserprofiledtoresult"></a>

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "username": "string",
    "displayName": "string",
    "avatarUrl": "string",
    "bio": "string",
    "favoriteTeamId": "d03f4e26-a6b7-4158-9c97-87bb7dc42e8b",
    "favoriteTeamName": "string",
    "createdAt": "2019-08-24T14:15:22Z",
    "updatedAt": "2019-08-24T14:15:22Z"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|isSuccess|boolean|false|read-only|none|
|error|[Error](#schemaerror)|false|none|none|
|data|[UserProfileDto](#schemauserprofiledto)|false|none|none|

<h2 id="tocS_UserRole">UserRole</h2>
<!-- backwards compatibility -->
<a id="schemauserrole"></a>
<a id="schema_UserRole"></a>
<a id="tocSuserrole"></a>
<a id="tocsuserrole"></a>

```json
0

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|integer(int32)|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|*anonymous*|0|
|*anonymous*|1|

<h2 id="tocS_ValidateLeagueResult">ValidateLeagueResult</h2>
<!-- backwards compatibility -->
<a id="schemavalidateleagueresult"></a>
<a id="schema_ValidateLeagueResult"></a>
<a id="tocSvalidateleagueresult"></a>
<a id="tocsvalidateleagueresult"></a>

```json
{
  "isValid": true,
  "leagueName": "string",
  "leagueType": "string",
  "country": "string",
  "hasLineupsSupport": true,
  "hasEventsSupport": true,
  "hasStatisticsSupport": true,
  "errorMessage": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|isValid|boolean|false|none|none|
|leagueName|string¦null|false|none|none|
|leagueType|string¦null|false|none|none|
|country|string¦null|false|none|none|
|hasLineupsSupport|boolean|false|none|none|
|hasEventsSupport|boolean|false|none|none|
|hasStatisticsSupport|boolean|false|none|none|
|errorMessage|string¦null|false|none|none|

<h2 id="tocS_ValidateLeagueResultResult">ValidateLeagueResultResult</h2>
<!-- backwards compatibility -->
<a id="schemavalidateleagueresultresult"></a>
<a id="schema_ValidateLeagueResultResult"></a>
<a id="tocSvalidateleagueresultresult"></a>
<a id="tocsvalidateleagueresultresult"></a>

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": {
    "isValid": true,
    "leagueName": "string",
    "leagueType": "string",
    "country": "string",
    "hasLineupsSupport": true,
    "hasEventsSupport": true,
    "hasStatisticsSupport": true,
    "errorMessage": "string"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|isSuccess|boolean|false|read-only|none|
|error|[Error](#schemaerror)|false|none|none|
|data|[ValidateLeagueResult](#schemavalidateleagueresult)|false|none|none|

<h2 id="tocS_VenueDto">VenueDto</h2>
<!-- backwards compatibility -->
<a id="schemavenuedto"></a>
<a id="schema_VenueDto"></a>
<a id="tocSvenuedto"></a>
<a id="tocsvenuedto"></a>

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "name": "string",
  "address": "string",
  "city": "string",
  "capacity": 0,
  "surface": "string",
  "imageUrl": "string",
  "apiFootballId": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|false|none|none|
|name|string¦null|false|none|none|
|address|string¦null|false|none|none|
|city|string¦null|false|none|none|
|capacity|integer(int32)¦null|false|none|none|
|surface|string¦null|false|none|none|
|imageUrl|string¦null|false|none|none|
|apiFootballId|integer(int32)¦null|false|none|none|

<h2 id="tocS_VenueDtoIReadOnlyListResult">VenueDtoIReadOnlyListResult</h2>
<!-- backwards compatibility -->
<a id="schemavenuedtoireadonlylistresult"></a>
<a id="schema_VenueDtoIReadOnlyListResult"></a>
<a id="tocSvenuedtoireadonlylistresult"></a>
<a id="tocsvenuedtoireadonlylistresult"></a>

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "name": "string",
      "address": "string",
      "city": "string",
      "capacity": 0,
      "surface": "string",
      "imageUrl": "string",
      "apiFootballId": 0
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|isSuccess|boolean|false|read-only|none|
|error|[Error](#schemaerror)|false|none|none|
|data|[[VenueDto](#schemavenuedto)]¦null|false|read-only|none|

<h2 id="tocS_VenueDtoResult">VenueDtoResult</h2>
<!-- backwards compatibility -->
<a id="schemavenuedtoresult"></a>
<a id="schema_VenueDtoResult"></a>
<a id="tocSvenuedtoresult"></a>
<a id="tocsvenuedtoresult"></a>

```json
{
  "isSuccess": true,
  "error": {
    "type": 1,
    "message": "string",
    "code": "string",
    "validationErrors": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  },
  "data": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "name": "string",
    "address": "string",
    "city": "string",
    "capacity": 0,
    "surface": "string",
    "imageUrl": "string",
    "apiFootballId": 0
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|isSuccess|boolean|false|read-only|none|
|error|[Error](#schemaerror)|false|none|none|
|data|[VenueDto](#schemavenuedto)|false|none|none|

