---
title: Tippr API v1
language_tabs:
  - shell: Shell
  - javascript: JavaScript
  - csharp: C#
language_clients:
  - shell: ""
  - javascript: ""
  - csharp: ""
toc_footers: []
includes: []
search: true
highlight_theme: darkula
headingLevel: 2

---

<!-- Generator: Widdershins v4.0.1 -->

<h1 id="tippr-api">Tippr API v1</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

# Authentication

- HTTP Authentication, scheme: bearer Paste Supabase access_token

<h1 id="tippr-api-adminbonuspredictions">AdminBonusPredictions</h1>

## get__api_admin_bonus-predictions

> Code samples

```shell
# You can also use wget
curl -X GET /api/admin/bonus-predictions \
  -H 'Accept: text/plain' \
  -H 'Authorization: Bearer {access-token}'

```

```javascript

const headers = {
  'Accept':'text/plain',
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

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    /// Make a dummy request
    public async Task MakeGetRequest()
    {
      string url = "/api/admin/bonus-predictions";
      var result = await GetAsync(url);
    }

    /// Performs a GET Request
    public async Task GetAsync(string url)
    {
        //Start the request
        HttpResponseMessage response = await Client.GetAsync(url);

        //Validate result
        response.EnsureSuccessStatusCode();

    }
    
    
    
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
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

```
{"isSuccess":true,"error":{"type":1,"message":"string","code":"string","validationErrors":{"property1":["string"],"property2":["string"]}},"data":{"items":[{"id":"497f6eca-6276-4993-bfeb-53cbbbba6f08","userId":"2c4a230c-5085-4924-a3e1-25fb4fc5965b","username":"string","bonusQuestionId":"a0b61934-6fef-4d97-866d-54f4b60aee83","leagueId":"58549e12-c6e6-4e03-99d1-6e916f71ce9a","leagueName":"string","answerTeamId":"ab2250dd-c194-4fab-a78b-360f3b350150","answerTeamName":"string","answerText":"string","pointsEarned":0}],"totalCount":0,"page":0,"pageSize":0,"totalPages":0,"hasNextPage":true,"hasPreviousPage":true}}
```

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
  -H 'Accept: text/plain' \
  -H 'Authorization: Bearer {access-token}'

```

```javascript

const headers = {
  'Accept':'text/plain',
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

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    /// Make a dummy request
    public async Task MakeGetRequest()
    {
      string url = "/api/admin/bonus-questions/{bonusQuestionId}";
      var result = await GetAsync(url);
    }

    /// Performs a GET Request
    public async Task GetAsync(string url)
    {
        //Start the request
        HttpResponseMessage response = await Client.GetAsync(url);

        //Validate result
        response.EnsureSuccessStatusCode();

    }
    
    
    
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
}

```

`GET /api/admin/bonus-questions/{bonusQuestionId}`

<h3 id="get__api_admin_bonus-questions_{bonusquestionid}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|bonusQuestionId|path|string(uuid)|true|none|

> Example responses

> 200 Response

```
{"isSuccess":true,"error":{"type":1,"message":"string","code":"string","validationErrors":{"property1":["string"],"property2":["string"]}},"data":{"id":"497f6eca-6276-4993-bfeb-53cbbbba6f08","tournamentId":"4a951104-9f98-4996-b388-a0ef2c00bb2a","tournamentName":"string","questionType":0,"question":"string","answerTeamId":"ab2250dd-c194-4fab-a78b-360f3b350150","answerTeamName":"string","answerText":"string","isResolved":true,"points":0,"createdAt":"2019-08-24T14:15:22Z","updatedAt":"2019-08-24T14:15:22Z","predictionCount":0}}
```

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
  -H 'Accept: text/plain' \
  -H 'Authorization: Bearer {access-token}'

```

```javascript
const inputBody = '{
  "questionType": 0,
  "question": "string",
  "points": 0
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'text/plain',
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

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    
    
    /// Make a dummy request
    public async Task MakePutRequest()
    {
      int id = 1;
      string url = "/api/admin/bonus-questions/{bonusQuestionId}";

      
      string json = @"{
  ""questionType"": 0,
  ""question"": ""string"",
  ""points"": 0
}";
      UpdateBonusQuestionRequest content = JsonConvert.DeserializeObject(json);
      var result = await PutAsync(id, content, url);
      
          
    }

    /// Performs a PUT Request
    public async Task PutAsync(int id, UpdateBonusQuestionRequest content, string url)
    {
        //Serialize Object
        StringContent jsonContent = SerializeObject(content);

        //Execute PUT request
        HttpResponseMessage response = await Client.PutAsync(url + $"/{id}", jsonContent);

        //Return response
        return await DeserializeObject(response);
    }
    
    
    /// Serialize an object to Json
    private StringContent SerializeObject(UpdateBonusQuestionRequest content)
    {
        //Serialize Object
        string jsonObject = JsonConvert.SerializeObject(content);

        //Create Json UTF8 String Content
        return new StringContent(jsonObject, Encoding.UTF8, "application/json");
    }
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
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

```
{"isSuccess":true,"error":{"type":1,"message":"string","code":"string","validationErrors":{"property1":["string"],"property2":["string"]}},"data":{"id":"497f6eca-6276-4993-bfeb-53cbbbba6f08","tournamentId":"4a951104-9f98-4996-b388-a0ef2c00bb2a","tournamentName":"string","questionType":0,"question":"string","answerTeamId":"ab2250dd-c194-4fab-a78b-360f3b350150","answerTeamName":"string","answerText":"string","isResolved":true,"points":0,"createdAt":"2019-08-24T14:15:22Z","updatedAt":"2019-08-24T14:15:22Z","predictionCount":0}}
```

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
  -H 'Accept: text/plain' \
  -H 'Authorization: Bearer {access-token}'

```

```javascript

const headers = {
  'Accept':'text/plain',
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

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    
    
    
    /// Make a dummy request
    public async Task MakeDeleteRequest()
    {
      int id = 1;
      string url = "/api/admin/bonus-questions/{bonusQuestionId}";

      await DeleteAsync(id, url);
    }

    /// Performs a DELETE Request
    public async Task DeleteAsync(int id, string url)
    {
        //Execute DELETE request
        HttpResponseMessage response = await Client.DeleteAsync(url + $"/{id}");

        //Return response
        await DeserializeObject(response);
    }
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
}

```

`DELETE /api/admin/bonus-questions/{bonusQuestionId}`

<h3 id="delete__api_admin_bonus-questions_{bonusquestionid}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|bonusQuestionId|path|string(uuid)|true|none|

> Example responses

> 200 Response

```
{"isSuccess":true,"error":{"type":1,"message":"string","code":"string","validationErrors":{"property1":["string"],"property2":["string"]}},"data":true}
```

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
  -H 'Accept: text/plain' \
  -H 'Authorization: Bearer {access-token}'

```

```javascript

const headers = {
  'Accept':'text/plain',
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

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    
    /// Make a dummy request
    public async Task MakePostRequest()
    {
      string url = "/api/admin/bonus-questions/{bonusQuestionId}/recalculate";
      
      
      await PostAsync(null, url);
      
    }

    /// Performs a POST Request
    public async Task PostAsync(undefined content, string url)
    {
        //Serialize Object
        StringContent jsonContent = SerializeObject(content);

        //Execute POST request
        HttpResponseMessage response = await Client.PostAsync(url, jsonContent);
    }
    
    
    
    /// Serialize an object to Json
    private StringContent SerializeObject(undefined content)
    {
        //Serialize Object
        string jsonObject = JsonConvert.SerializeObject(content);

        //Create Json UTF8 String Content
        return new StringContent(jsonObject, Encoding.UTF8, "application/json");
    }
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
}

```

`POST /api/admin/bonus-questions/{bonusQuestionId}/recalculate`

<h3 id="post__api_admin_bonus-questions_{bonusquestionid}_recalculate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|bonusQuestionId|path|string(uuid)|true|none|

> Example responses

> 200 Response

```
{"isSuccess":true,"error":{"type":1,"message":"string","code":"string","validationErrors":{"property1":["string"],"property2":["string"]}},"data":{"predictionsUpdated":0,"correctPredictions":0,"totalPointsAwarded":0,"leaguesAffected":0}}
```

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
  -H 'Accept: text/plain' \
  -H 'Authorization: Bearer {access-token}'

```

```javascript

const headers = {
  'Accept':'text/plain',
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

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    /// Make a dummy request
    public async Task MakeGetRequest()
    {
      string url = "/api/admin/chat/messages";
      var result = await GetAsync(url);
    }

    /// Performs a GET Request
    public async Task GetAsync(string url)
    {
        //Start the request
        HttpResponseMessage response = await Client.GetAsync(url);

        //Validate result
        response.EnsureSuccessStatusCode();

    }
    
    
    
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
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

```
{"isSuccess":true,"error":{"type":1,"message":"string","code":"string","validationErrors":{"property1":["string"],"property2":["string"]}},"data":{"messages":[{"id":"497f6eca-6276-4993-bfeb-53cbbbba6f08","leagueId":"58549e12-c6e6-4e03-99d1-6e916f71ce9a","leagueName":"string","userId":"2c4a230c-5085-4924-a3e1-25fb4fc5965b","username":"string","userDisplayName":"string","userAvatarUrl":"string","message":"string","isEdited":true,"editedAt":"2019-08-24T14:15:22Z","isDeleted":true,"createdAt":"2019-08-24T14:15:22Z"}],"nextCursor":"2019-08-24T14:15:22Z","hasMore":true}}
```

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
  -H 'Accept: text/plain' \
  -H 'Authorization: Bearer {access-token}'

```

```javascript

const headers = {
  'Accept':'text/plain',
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

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    
    
    
    /// Make a dummy request
    public async Task MakeDeleteRequest()
    {
      int id = 1;
      string url = "/api/admin/chat/messages/{messageId}";

      await DeleteAsync(id, url);
    }

    /// Performs a DELETE Request
    public async Task DeleteAsync(int id, string url)
    {
        //Execute DELETE request
        HttpResponseMessage response = await Client.DeleteAsync(url + $"/{id}");

        //Return response
        await DeserializeObject(response);
    }
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
}

```

`DELETE /api/admin/chat/messages/{messageId}`

<h3 id="delete__api_admin_chat_messages_{messageid}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|messageId|path|string(uuid)|true|none|

> Example responses

> 200 Response

```
{"isSuccess":true,"error":{"type":1,"message":"string","code":"string","validationErrors":{"property1":["string"],"property2":["string"]}},"data":true}
```

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
  -H 'Accept: text/plain' \
  -H 'Authorization: Bearer {access-token}'

```

```javascript

const headers = {
  'Accept':'text/plain',
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

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    /// Make a dummy request
    public async Task MakeGetRequest()
    {
      string url = "/api/admin/leagues";
      var result = await GetAsync(url);
    }

    /// Performs a GET Request
    public async Task GetAsync(string url)
    {
        //Start the request
        HttpResponseMessage response = await Client.GetAsync(url);

        //Validate result
        response.EnsureSuccessStatusCode();

    }
    
    
    
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
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

```
{"isSuccess":true,"error":{"type":1,"message":"string","code":"string","validationErrors":{"property1":["string"],"property2":["string"]}},"data":{"items":[{"id":"497f6eca-6276-4993-bfeb-53cbbbba6f08","name":"string","description":"string","tournamentId":"4a951104-9f98-4996-b388-a0ef2c00bb2a","tournamentName":"string","ownerId":"4d206909-730f-409a-88f6-dcfaa8fc28cc","ownerUsername":"string","isPublic":true,"isGlobal":true,"maxMembers":0,"createdAt":"2019-08-24T14:15:22Z","memberCount":0}],"totalCount":0,"page":0,"pageSize":0,"totalPages":0,"hasNextPage":true,"hasPreviousPage":true}}
```

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
  -H 'Accept: text/plain' \
  -H 'Authorization: Bearer {access-token}'

```

```javascript

const headers = {
  'Accept':'text/plain',
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

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    /// Make a dummy request
    public async Task MakeGetRequest()
    {
      string url = "/api/admin/leagues/{leagueId}";
      var result = await GetAsync(url);
    }

    /// Performs a GET Request
    public async Task GetAsync(string url)
    {
        //Start the request
        HttpResponseMessage response = await Client.GetAsync(url);

        //Validate result
        response.EnsureSuccessStatusCode();

    }
    
    
    
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
}

```

`GET /api/admin/leagues/{leagueId}`

<h3 id="get__api_admin_leagues_{leagueid}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|leagueId|path|string(uuid)|true|none|

> Example responses

> 200 Response

```
{"isSuccess":true,"error":{"type":1,"message":"string","code":"string","validationErrors":{"property1":["string"],"property2":["string"]}},"data":{"id":"497f6eca-6276-4993-bfeb-53cbbbba6f08","name":"string","description":"string","tournamentId":"4a951104-9f98-4996-b388-a0ef2c00bb2a","tournamentName":"string","ownerId":"4d206909-730f-409a-88f6-dcfaa8fc28cc","ownerUsername":"string","inviteCode":"string","isPublic":true,"isGlobal":true,"isSystemCreated":true,"maxMembers":0,"imageUrl":"string","createdAt":"2019-08-24T14:15:22Z","updatedAt":"2019-08-24T14:15:22Z","memberCount":0,"predictionCount":0}}
```

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
  -H 'Accept: text/plain' \
  -H 'Authorization: Bearer {access-token}'

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
  'Accept':'text/plain',
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

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    
    
    /// Make a dummy request
    public async Task MakePutRequest()
    {
      int id = 1;
      string url = "/api/admin/leagues/{leagueId}";

      
      string json = @"{
  ""name"": ""string"",
  ""description"": ""string"",
  ""isPublic"": true,
  ""isGlobal"": true,
  ""maxMembers"": 0,
  ""imageUrl"": ""string""
}";
      UpdateAdminLeagueRequest content = JsonConvert.DeserializeObject(json);
      var result = await PutAsync(id, content, url);
      
          
    }

    /// Performs a PUT Request
    public async Task PutAsync(int id, UpdateAdminLeagueRequest content, string url)
    {
        //Serialize Object
        StringContent jsonContent = SerializeObject(content);

        //Execute PUT request
        HttpResponseMessage response = await Client.PutAsync(url + $"/{id}", jsonContent);

        //Return response
        return await DeserializeObject(response);
    }
    
    
    /// Serialize an object to Json
    private StringContent SerializeObject(UpdateAdminLeagueRequest content)
    {
        //Serialize Object
        string jsonObject = JsonConvert.SerializeObject(content);

        //Create Json UTF8 String Content
        return new StringContent(jsonObject, Encoding.UTF8, "application/json");
    }
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
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

```
{"isSuccess":true,"error":{"type":1,"message":"string","code":"string","validationErrors":{"property1":["string"],"property2":["string"]}},"data":{"id":"497f6eca-6276-4993-bfeb-53cbbbba6f08","name":"string","description":"string","tournamentId":"4a951104-9f98-4996-b388-a0ef2c00bb2a","tournamentName":"string","ownerId":"4d206909-730f-409a-88f6-dcfaa8fc28cc","ownerUsername":"string","inviteCode":"string","isPublic":true,"isGlobal":true,"isSystemCreated":true,"maxMembers":0,"imageUrl":"string","createdAt":"2019-08-24T14:15:22Z","updatedAt":"2019-08-24T14:15:22Z","memberCount":0,"predictionCount":0}}
```

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
  -H 'Accept: text/plain' \
  -H 'Authorization: Bearer {access-token}'

```

```javascript

const headers = {
  'Accept':'text/plain',
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

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    
    
    
    /// Make a dummy request
    public async Task MakeDeleteRequest()
    {
      int id = 1;
      string url = "/api/admin/leagues/{leagueId}";

      await DeleteAsync(id, url);
    }

    /// Performs a DELETE Request
    public async Task DeleteAsync(int id, string url)
    {
        //Execute DELETE request
        HttpResponseMessage response = await Client.DeleteAsync(url + $"/{id}");

        //Return response
        await DeserializeObject(response);
    }
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
}

```

`DELETE /api/admin/leagues/{leagueId}`

<h3 id="delete__api_admin_leagues_{leagueid}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|leagueId|path|string(uuid)|true|none|

> Example responses

> 200 Response

```
{"isSuccess":true,"error":{"type":1,"message":"string","code":"string","validationErrors":{"property1":["string"],"property2":["string"]}},"data":true}
```

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
  -H 'Accept: text/plain' \
  -H 'Authorization: Bearer {access-token}'

```

```javascript

const headers = {
  'Accept':'text/plain',
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

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    
    /// Make a dummy request
    public async Task MakePostRequest()
    {
      string url = "/api/admin/leagues/{leagueId}/invite-code/regenerate";
      
      
      await PostAsync(null, url);
      
    }

    /// Performs a POST Request
    public async Task PostAsync(undefined content, string url)
    {
        //Serialize Object
        StringContent jsonContent = SerializeObject(content);

        //Execute POST request
        HttpResponseMessage response = await Client.PostAsync(url, jsonContent);
    }
    
    
    
    /// Serialize an object to Json
    private StringContent SerializeObject(undefined content)
    {
        //Serialize Object
        string jsonObject = JsonConvert.SerializeObject(content);

        //Create Json UTF8 String Content
        return new StringContent(jsonObject, Encoding.UTF8, "application/json");
    }
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
}

```

`POST /api/admin/leagues/{leagueId}/invite-code/regenerate`

<h3 id="post__api_admin_leagues_{leagueid}_invite-code_regenerate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|leagueId|path|string(uuid)|true|none|

> Example responses

> 200 Response

```
{"isSuccess":true,"error":{"type":1,"message":"string","code":"string","validationErrors":{"property1":["string"],"property2":["string"]}},"data":"string"}
```

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
  -H 'Accept: text/plain' \
  -H 'Authorization: Bearer {access-token}'

```

```javascript

const headers = {
  'Accept':'text/plain',
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

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    /// Make a dummy request
    public async Task MakeGetRequest()
    {
      string url = "/api/admin/leagues/{leagueId}/members";
      var result = await GetAsync(url);
    }

    /// Performs a GET Request
    public async Task GetAsync(string url)
    {
        //Start the request
        HttpResponseMessage response = await Client.GetAsync(url);

        //Validate result
        response.EnsureSuccessStatusCode();

    }
    
    
    
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
}

```

`GET /api/admin/leagues/{leagueId}/members`

<h3 id="get__api_admin_leagues_{leagueid}_members-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|leagueId|path|string(uuid)|true|none|

> Example responses

> 200 Response

```
{"isSuccess":true,"error":{"type":1,"message":"string","code":"string","validationErrors":{"property1":["string"],"property2":["string"]}},"data":[{"id":"497f6eca-6276-4993-bfeb-53cbbbba6f08","leagueId":"58549e12-c6e6-4e03-99d1-6e916f71ce9a","userId":"2c4a230c-5085-4924-a3e1-25fb4fc5965b","username":"string","displayName":"string","email":"string","avatarUrl":"string","joinedAt":"2019-08-24T14:15:22Z","isAdmin":true,"isMuted":true,"totalPoints":0,"rank":0}]}
```

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
  -H 'Accept: text/plain' \
  -H 'Authorization: Bearer {access-token}'

```

```javascript
const inputBody = '{
  "userId": "2c4a230c-5085-4924-a3e1-25fb4fc5965b",
  "isAdmin": true
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'text/plain',
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

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    
    /// Make a dummy request
    public async Task MakePostRequest()
    {
      string url = "/api/admin/leagues/{leagueId}/members";
      
      string json = @"{
  ""userId"": ""2c4a230c-5085-4924-a3e1-25fb4fc5965b"",
  ""isAdmin"": true
}";
      AddLeagueMemberRequest content = JsonConvert.DeserializeObject(json);
      await PostAsync(content, url);
      
      
    }

    /// Performs a POST Request
    public async Task PostAsync(AddLeagueMemberRequest content, string url)
    {
        //Serialize Object
        StringContent jsonContent = SerializeObject(content);

        //Execute POST request
        HttpResponseMessage response = await Client.PostAsync(url, jsonContent);
    }
    
    
    
    /// Serialize an object to Json
    private StringContent SerializeObject(AddLeagueMemberRequest content)
    {
        //Serialize Object
        string jsonObject = JsonConvert.SerializeObject(content);

        //Create Json UTF8 String Content
        return new StringContent(jsonObject, Encoding.UTF8, "application/json");
    }
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
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

```
{"isSuccess":true,"error":{"type":1,"message":"string","code":"string","validationErrors":{"property1":["string"],"property2":["string"]}},"data":"808ac6e4-93ed-4040-85a5-6c71a2444e90"}
```

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
  -H 'Accept: text/plain' \
  -H 'Authorization: Bearer {access-token}'

```

```javascript

const headers = {
  'Accept':'text/plain',
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

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    
    
    
    /// Make a dummy request
    public async Task MakeDeleteRequest()
    {
      int id = 1;
      string url = "/api/admin/leagues/{leagueId}/members/{userId}";

      await DeleteAsync(id, url);
    }

    /// Performs a DELETE Request
    public async Task DeleteAsync(int id, string url)
    {
        //Execute DELETE request
        HttpResponseMessage response = await Client.DeleteAsync(url + $"/{id}");

        //Return response
        await DeserializeObject(response);
    }
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
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

```
{"isSuccess":true,"error":{"type":1,"message":"string","code":"string","validationErrors":{"property1":["string"],"property2":["string"]}},"data":true}
```

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
  -H 'Accept: text/plain' \
  -H 'Authorization: Bearer {access-token}'

```

```javascript
const inputBody = '{
  "isAdmin": true,
  "isMuted": true
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'text/plain',
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

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    
    
    /// Make a dummy request
    public async Task MakePutRequest()
    {
      int id = 1;
      string url = "/api/admin/leagues/{leagueId}/members/{userId}";

      
      string json = @"{
  ""isAdmin"": true,
  ""isMuted"": true
}";
      UpdateLeagueMemberRequest content = JsonConvert.DeserializeObject(json);
      var result = await PutAsync(id, content, url);
      
          
    }

    /// Performs a PUT Request
    public async Task PutAsync(int id, UpdateLeagueMemberRequest content, string url)
    {
        //Serialize Object
        StringContent jsonContent = SerializeObject(content);

        //Execute PUT request
        HttpResponseMessage response = await Client.PutAsync(url + $"/{id}", jsonContent);

        //Return response
        return await DeserializeObject(response);
    }
    
    
    /// Serialize an object to Json
    private StringContent SerializeObject(UpdateLeagueMemberRequest content)
    {
        //Serialize Object
        string jsonObject = JsonConvert.SerializeObject(content);

        //Create Json UTF8 String Content
        return new StringContent(jsonObject, Encoding.UTF8, "application/json");
    }
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
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

```
{"isSuccess":true,"error":{"type":1,"message":"string","code":"string","validationErrors":{"property1":["string"],"property2":["string"]}},"data":true}
```

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
  -H 'Accept: text/plain' \
  -H 'Authorization: Bearer {access-token}'

```

```javascript

const headers = {
  'Accept':'text/plain',
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

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    
    /// Make a dummy request
    public async Task MakePostRequest()
    {
      string url = "/api/admin/leagues/{leagueId}/standings/recalculate";
      
      
      await PostAsync(null, url);
      
    }

    /// Performs a POST Request
    public async Task PostAsync(undefined content, string url)
    {
        //Serialize Object
        StringContent jsonContent = SerializeObject(content);

        //Execute POST request
        HttpResponseMessage response = await Client.PostAsync(url, jsonContent);
    }
    
    
    
    /// Serialize an object to Json
    private StringContent SerializeObject(undefined content)
    {
        //Serialize Object
        string jsonObject = JsonConvert.SerializeObject(content);

        //Create Json UTF8 String Content
        return new StringContent(jsonObject, Encoding.UTF8, "application/json");
    }
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
}

```

`POST /api/admin/leagues/{leagueId}/standings/recalculate`

<h3 id="post__api_admin_leagues_{leagueid}_standings_recalculate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|leagueId|path|string(uuid)|true|none|

> Example responses

> 200 Response

```
{"isSuccess":true,"error":{"type":1,"message":"string","code":"string","validationErrors":{"property1":["string"],"property2":["string"]}},"data":true}
```

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
  -H 'Accept: text/plain' \
  -H 'Authorization: Bearer {access-token}'

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
  'Accept':'text/plain',
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

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    
    /// Make a dummy request
    public async Task MakePostRequest()
    {
      string url = "/api/admin/matches";
      
      string json = @"{
  ""tournamentId"": ""4a951104-9f98-4996-b388-a0ef2c00bb2a"",
  ""homeTeamId"": ""fb7b8236-8f4a-4255-b25d-a64d7c4d6968"",
  ""awayTeamId"": ""aa1734e3-668a-43b1-918b-ecab48ec02f9"",
  ""matchDate"": ""2019-08-24T14:15:22Z"",
  ""stage"": 0,
  ""venue"": ""string"",
  ""apiFootballId"": 0
}";
      CreateMatchRequest content = JsonConvert.DeserializeObject(json);
      await PostAsync(content, url);
      
      
    }

    /// Performs a POST Request
    public async Task PostAsync(CreateMatchRequest content, string url)
    {
        //Serialize Object
        StringContent jsonContent = SerializeObject(content);

        //Execute POST request
        HttpResponseMessage response = await Client.PostAsync(url, jsonContent);
    }
    
    
    
    /// Serialize an object to Json
    private StringContent SerializeObject(CreateMatchRequest content)
    {
        //Serialize Object
        string jsonObject = JsonConvert.SerializeObject(content);

        //Create Json UTF8 String Content
        return new StringContent(jsonObject, Encoding.UTF8, "application/json");
    }
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
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

```
{"isSuccess":true,"error":{"type":1,"message":"string","code":"string","validationErrors":{"property1":["string"],"property2":["string"]}},"data":"808ac6e4-93ed-4040-85a5-6c71a2444e90"}
```

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
  -H 'Accept: text/plain' \
  -H 'Authorization: Bearer {access-token}'

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
  'Accept':'text/plain',
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

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    
    
    /// Make a dummy request
    public async Task MakePutRequest()
    {
      int id = 1;
      string url = "/api/admin/matches/{matchId}";

      
      string json = @"{
  ""matchDate"": ""2019-08-24T14:15:22Z"",
  ""stage"": 0,
  ""status"": 0,
  ""venue"": ""string"",
  ""apiFootballId"": 0
}";
      UpdateMatchRequest content = JsonConvert.DeserializeObject(json);
      var result = await PutAsync(id, content, url);
      
          
    }

    /// Performs a PUT Request
    public async Task PutAsync(int id, UpdateMatchRequest content, string url)
    {
        //Serialize Object
        StringContent jsonContent = SerializeObject(content);

        //Execute PUT request
        HttpResponseMessage response = await Client.PutAsync(url + $"/{id}", jsonContent);

        //Return response
        return await DeserializeObject(response);
    }
    
    
    /// Serialize an object to Json
    private StringContent SerializeObject(UpdateMatchRequest content)
    {
        //Serialize Object
        string jsonObject = JsonConvert.SerializeObject(content);

        //Create Json UTF8 String Content
        return new StringContent(jsonObject, Encoding.UTF8, "application/json");
    }
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
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

```
{"isSuccess":true,"error":{"type":1,"message":"string","code":"string","validationErrors":{"property1":["string"],"property2":["string"]}},"data":{"id":"497f6eca-6276-4993-bfeb-53cbbbba6f08","tournamentId":"4a951104-9f98-4996-b388-a0ef2c00bb2a","tournamentName":"string","homeTeamId":"fb7b8236-8f4a-4255-b25d-a64d7c4d6968","homeTeamName":"string","homeTeamCode":"string","homeTeamFlagUrl":"string","awayTeamId":"aa1734e3-668a-43b1-918b-ecab48ec02f9","awayTeamName":"string","awayTeamCode":"string","awayTeamFlagUrl":"string","matchDate":"2019-08-24T14:15:22Z","stage":0,"homeScore":0,"awayScore":0,"status":0,"venue":"string","apiFootballId":0,"resultVersion":0,"createdAt":"2019-08-24T14:15:22Z","updatedAt":"2019-08-24T14:15:22Z","predictionCount":0}}
```

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
    "homeTeamFlagUrl": "string",
    "awayTeamId": "aa1734e3-668a-43b1-918b-ecab48ec02f9",
    "awayTeamName": "string",
    "awayTeamCode": "string",
    "awayTeamFlagUrl": "string",
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
  -H 'Accept: text/plain' \
  -H 'Authorization: Bearer {access-token}'

```

```javascript
const inputBody = '{
  "homeScore": 0,
  "awayScore": 0,
  "status": 0
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'text/plain',
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

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    
    
    /// Make a dummy request
    public async Task MakePutRequest()
    {
      int id = 1;
      string url = "/api/admin/matches/{matchId}/result";

      
      string json = @"{
  ""homeScore"": 0,
  ""awayScore"": 0,
  ""status"": 0
}";
      UpdateMatchResultRequest content = JsonConvert.DeserializeObject(json);
      var result = await PutAsync(id, content, url);
      
          
    }

    /// Performs a PUT Request
    public async Task PutAsync(int id, UpdateMatchResultRequest content, string url)
    {
        //Serialize Object
        StringContent jsonContent = SerializeObject(content);

        //Execute PUT request
        HttpResponseMessage response = await Client.PutAsync(url + $"/{id}", jsonContent);

        //Return response
        return await DeserializeObject(response);
    }
    
    
    /// Serialize an object to Json
    private StringContent SerializeObject(UpdateMatchResultRequest content)
    {
        //Serialize Object
        string jsonObject = JsonConvert.SerializeObject(content);

        //Create Json UTF8 String Content
        return new StringContent(jsonObject, Encoding.UTF8, "application/json");
    }
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
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

```
{"isSuccess":true,"error":{"type":1,"message":"string","code":"string","validationErrors":{"property1":["string"],"property2":["string"]}},"data":true}
```

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
  -H 'Accept: text/plain' \
  -H 'Authorization: Bearer {access-token}'

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
  'Accept':'text/plain',
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

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    
    /// Make a dummy request
    public async Task MakePostRequest()
    {
      string url = "/api/admin/matches/bulk";
      
      string json = @"{
  ""tournamentId"": ""4a951104-9f98-4996-b388-a0ef2c00bb2a"",
  ""matches"": [
    {
      ""homeTeamId"": ""fb7b8236-8f4a-4255-b25d-a64d7c4d6968"",
      ""awayTeamId"": ""aa1734e3-668a-43b1-918b-ecab48ec02f9"",
      ""matchDate"": ""2019-08-24T14:15:22Z"",
      ""stage"": 0,
      ""venue"": ""string"",
      ""apiFootballId"": 0
    }
  ]
}";
      BulkCreateMatchesRequest content = JsonConvert.DeserializeObject(json);
      await PostAsync(content, url);
      
      
    }

    /// Performs a POST Request
    public async Task PostAsync(BulkCreateMatchesRequest content, string url)
    {
        //Serialize Object
        StringContent jsonContent = SerializeObject(content);

        //Execute POST request
        HttpResponseMessage response = await Client.PostAsync(url, jsonContent);
    }
    
    
    
    /// Serialize an object to Json
    private StringContent SerializeObject(BulkCreateMatchesRequest content)
    {
        //Serialize Object
        string jsonObject = JsonConvert.SerializeObject(content);

        //Create Json UTF8 String Content
        return new StringContent(jsonObject, Encoding.UTF8, "application/json");
    }
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
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

```
{"isSuccess":true,"error":{"type":1,"message":"string","code":"string","validationErrors":{"property1":["string"],"property2":["string"]}},"data":{"createdCount":0,"failedCount":0,"errors":["string"],"createdIds":["497f6eca-6276-4993-bfeb-53cbbbba6f08"]}}
```

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
  -H 'Accept: text/plain' \
  -H 'Authorization: Bearer {access-token}'

```

```javascript

const headers = {
  'Accept':'text/plain',
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

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    
    /// Make a dummy request
    public async Task MakePostRequest()
    {
      string url = "/api/admin/matches/{matchId}/recalculate";
      
      
      await PostAsync(null, url);
      
    }

    /// Performs a POST Request
    public async Task PostAsync(undefined content, string url)
    {
        //Serialize Object
        StringContent jsonContent = SerializeObject(content);

        //Execute POST request
        HttpResponseMessage response = await Client.PostAsync(url, jsonContent);
    }
    
    
    
    /// Serialize an object to Json
    private StringContent SerializeObject(undefined content)
    {
        //Serialize Object
        string jsonObject = JsonConvert.SerializeObject(content);

        //Create Json UTF8 String Content
        return new StringContent(jsonObject, Encoding.UTF8, "application/json");
    }
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
}

```

`POST /api/admin/matches/{matchId}/recalculate`

<h3 id="post__api_admin_matches_{matchid}_recalculate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|matchId|path|string(uuid)|true|none|

> Example responses

> 200 Response

```
{"isSuccess":true,"error":{"type":1,"message":"string","code":"string","validationErrors":{"property1":["string"],"property2":["string"]}},"data":{"predictionsUpdated":0,"leaguesAffected":0}}
```

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
  -H 'Accept: text/plain' \
  -H 'Authorization: Bearer {access-token}'

```

```javascript

const headers = {
  'Accept':'text/plain',
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

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    /// Make a dummy request
    public async Task MakeGetRequest()
    {
      string url = "/api/admin/predictions";
      var result = await GetAsync(url);
    }

    /// Performs a GET Request
    public async Task GetAsync(string url)
    {
        //Start the request
        HttpResponseMessage response = await Client.GetAsync(url);

        //Validate result
        response.EnsureSuccessStatusCode();

    }
    
    
    
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
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

```
{"isSuccess":true,"error":{"type":1,"message":"string","code":"string","validationErrors":{"property1":["string"],"property2":["string"]}},"data":{"items":[{"id":"497f6eca-6276-4993-bfeb-53cbbbba6f08","userId":"2c4a230c-5085-4924-a3e1-25fb4fc5965b","username":"string","matchId":"685569fd-95e6-4335-9aa5-fdd22382bd9e","matchDescription":"string","leagueId":"58549e12-c6e6-4e03-99d1-6e916f71ce9a","leagueName":"string","homeScore":0,"awayScore":0,"pointsEarned":0,"isScored":true}],"totalCount":0,"page":0,"pageSize":0,"totalPages":0,"hasNextPage":true,"hasPreviousPage":true}}
```

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
  -H 'Accept: text/plain' \
  -H 'Authorization: Bearer {access-token}'

```

```javascript

const headers = {
  'Accept':'text/plain',
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

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    /// Make a dummy request
    public async Task MakeGetRequest()
    {
      string url = "/api/admin/predictions/{predictionId}";
      var result = await GetAsync(url);
    }

    /// Performs a GET Request
    public async Task GetAsync(string url)
    {
        //Start the request
        HttpResponseMessage response = await Client.GetAsync(url);

        //Validate result
        response.EnsureSuccessStatusCode();

    }
    
    
    
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
}

```

`GET /api/admin/predictions/{predictionId}`

<h3 id="get__api_admin_predictions_{predictionid}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|predictionId|path|string(uuid)|true|none|

> Example responses

> 200 Response

```
{"isSuccess":true,"error":{"type":1,"message":"string","code":"string","validationErrors":{"property1":["string"],"property2":["string"]}},"data":{"id":"497f6eca-6276-4993-bfeb-53cbbbba6f08","userId":"2c4a230c-5085-4924-a3e1-25fb4fc5965b","username":"string","userDisplayName":"string","matchId":"685569fd-95e6-4335-9aa5-fdd22382bd9e","matchDescription":"string","leagueId":"58549e12-c6e6-4e03-99d1-6e916f71ce9a","leagueName":"string","homeScore":0,"awayScore":0,"actualHomeScore":0,"actualAwayScore":0,"pointsEarned":0,"isScored":true,"scoredResultVersion":0,"scoredAt":"2019-08-24T14:15:22Z","createdAt":"2019-08-24T14:15:22Z","updatedAt":"2019-08-24T14:15:22Z"}}
```

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
  -H 'Accept: text/plain' \
  -H 'Authorization: Bearer {access-token}'

```

```javascript

const headers = {
  'Accept':'text/plain',
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

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    
    
    
    /// Make a dummy request
    public async Task MakeDeleteRequest()
    {
      int id = 1;
      string url = "/api/admin/predictions/{predictionId}";

      await DeleteAsync(id, url);
    }

    /// Performs a DELETE Request
    public async Task DeleteAsync(int id, string url)
    {
        //Execute DELETE request
        HttpResponseMessage response = await Client.DeleteAsync(url + $"/{id}");

        //Return response
        await DeserializeObject(response);
    }
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
}

```

`DELETE /api/admin/predictions/{predictionId}`

<h3 id="delete__api_admin_predictions_{predictionid}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|predictionId|path|string(uuid)|true|none|

> Example responses

> 200 Response

```
{"isSuccess":true,"error":{"type":1,"message":"string","code":"string","validationErrors":{"property1":["string"],"property2":["string"]}},"data":true}
```

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
  -H 'Accept: text/plain' \
  -H 'Authorization: Bearer {access-token}'

```

```javascript

const headers = {
  'Accept':'text/plain',
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

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    
    /// Make a dummy request
    public async Task MakePostRequest()
    {
      string url = "/api/admin/predictions/recalculate";
      
      
      await PostAsync(null, url);
      
    }

    /// Performs a POST Request
    public async Task PostAsync(undefined content, string url)
    {
        //Serialize Object
        StringContent jsonContent = SerializeObject(content);

        //Execute POST request
        HttpResponseMessage response = await Client.PostAsync(url, jsonContent);
    }
    
    
    
    /// Serialize an object to Json
    private StringContent SerializeObject(undefined content)
    {
        //Serialize Object
        string jsonObject = JsonConvert.SerializeObject(content);

        //Create Json UTF8 String Content
        return new StringContent(jsonObject, Encoding.UTF8, "application/json");
    }
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
}

```

`POST /api/admin/predictions/recalculate`

<h3 id="post__api_admin_predictions_recalculate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|leagueId|query|string(uuid)|false|none|

> Example responses

> 200 Response

```
{"isSuccess":true,"error":{"type":1,"message":"string","code":"string","validationErrors":{"property1":["string"],"property2":["string"]}},"data":{"predictionsUpdated":0,"totalPoints":0}}
```

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
  -H 'Accept: text/plain' \
  -H 'Authorization: Bearer {access-token}'

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
  'Accept':'text/plain',
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

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    
    /// Make a dummy request
    public async Task MakePostRequest()
    {
      string url = "/api/admin/teams";
      
      string json = @"{
  ""tournamentId"": ""4a951104-9f98-4996-b388-a0ef2c00bb2a"",
  ""name"": ""string"",
  ""code"": ""string"",
  ""flagUrl"": ""string"",
  ""groupName"": ""string"",
  ""fifaRank"": 0,
  ""fifaPoints"": 0.1,
  ""apiFootballId"": 0
}";
      CreateTeamRequest content = JsonConvert.DeserializeObject(json);
      await PostAsync(content, url);
      
      
    }

    /// Performs a POST Request
    public async Task PostAsync(CreateTeamRequest content, string url)
    {
        //Serialize Object
        StringContent jsonContent = SerializeObject(content);

        //Execute POST request
        HttpResponseMessage response = await Client.PostAsync(url, jsonContent);
    }
    
    
    
    /// Serialize an object to Json
    private StringContent SerializeObject(CreateTeamRequest content)
    {
        //Serialize Object
        string jsonObject = JsonConvert.SerializeObject(content);

        //Create Json UTF8 String Content
        return new StringContent(jsonObject, Encoding.UTF8, "application/json");
    }
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
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

```
{"isSuccess":true,"error":{"type":1,"message":"string","code":"string","validationErrors":{"property1":["string"],"property2":["string"]}},"data":"808ac6e4-93ed-4040-85a5-6c71a2444e90"}
```

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
  -H 'Accept: text/plain' \
  -H 'Authorization: Bearer {access-token}'

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
  'Accept':'text/plain',
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

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    
    
    /// Make a dummy request
    public async Task MakePutRequest()
    {
      int id = 1;
      string url = "/api/admin/teams/{teamId}";

      
      string json = @"{
  ""name"": ""string"",
  ""code"": ""string"",
  ""flagUrl"": ""string"",
  ""groupName"": ""string"",
  ""fifaRank"": 0,
  ""fifaPoints"": 0.1,
  ""apiFootballId"": 0
}";
      UpdateTeamRequest content = JsonConvert.DeserializeObject(json);
      var result = await PutAsync(id, content, url);
      
          
    }

    /// Performs a PUT Request
    public async Task PutAsync(int id, UpdateTeamRequest content, string url)
    {
        //Serialize Object
        StringContent jsonContent = SerializeObject(content);

        //Execute PUT request
        HttpResponseMessage response = await Client.PutAsync(url + $"/{id}", jsonContent);

        //Return response
        return await DeserializeObject(response);
    }
    
    
    /// Serialize an object to Json
    private StringContent SerializeObject(UpdateTeamRequest content)
    {
        //Serialize Object
        string jsonObject = JsonConvert.SerializeObject(content);

        //Create Json UTF8 String Content
        return new StringContent(jsonObject, Encoding.UTF8, "application/json");
    }
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
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

```
{"isSuccess":true,"error":{"type":1,"message":"string","code":"string","validationErrors":{"property1":["string"],"property2":["string"]}},"data":{"id":"497f6eca-6276-4993-bfeb-53cbbbba6f08","tournamentId":"4a951104-9f98-4996-b388-a0ef2c00bb2a","tournamentName":"string","name":"string","code":"string","flagUrl":"string","groupName":"string","fifaRank":0,"fifaPoints":0.1,"fifaRankingUpdatedAt":"2019-08-24T14:15:22Z","apiFootballId":0,"createdAt":"2019-08-24T14:15:22Z","updatedAt":"2019-08-24T14:15:22Z"}}
```

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
    "flagUrl": "string",
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
  -H 'Accept: text/plain' \
  -H 'Authorization: Bearer {access-token}'

```

```javascript

const headers = {
  'Accept':'text/plain',
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

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    
    
    
    /// Make a dummy request
    public async Task MakeDeleteRequest()
    {
      int id = 1;
      string url = "/api/admin/teams/{teamId}";

      await DeleteAsync(id, url);
    }

    /// Performs a DELETE Request
    public async Task DeleteAsync(int id, string url)
    {
        //Execute DELETE request
        HttpResponseMessage response = await Client.DeleteAsync(url + $"/{id}");

        //Return response
        await DeserializeObject(response);
    }
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
}

```

`DELETE /api/admin/teams/{teamId}`

<h3 id="delete__api_admin_teams_{teamid}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|teamId|path|string(uuid)|true|none|

> Example responses

> 200 Response

```
{"isSuccess":true,"error":{"type":1,"message":"string","code":"string","validationErrors":{"property1":["string"],"property2":["string"]}},"data":true}
```

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
  -H 'Accept: text/plain' \
  -H 'Authorization: Bearer {access-token}'

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
  'Accept':'text/plain',
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

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    
    /// Make a dummy request
    public async Task MakePostRequest()
    {
      string url = "/api/admin/teams/bulk";
      
      string json = @"{
  ""tournamentId"": ""4a951104-9f98-4996-b388-a0ef2c00bb2a"",
  ""teams"": [
    {
      ""name"": ""string"",
      ""code"": ""string"",
      ""flagUrl"": ""string"",
      ""groupName"": ""string"",
      ""fifaRank"": 0,
      ""fifaPoints"": 0.1,
      ""apiFootballId"": 0
    }
  ]
}";
      BulkCreateTeamsRequest content = JsonConvert.DeserializeObject(json);
      await PostAsync(content, url);
      
      
    }

    /// Performs a POST Request
    public async Task PostAsync(BulkCreateTeamsRequest content, string url)
    {
        //Serialize Object
        StringContent jsonContent = SerializeObject(content);

        //Execute POST request
        HttpResponseMessage response = await Client.PostAsync(url, jsonContent);
    }
    
    
    
    /// Serialize an object to Json
    private StringContent SerializeObject(BulkCreateTeamsRequest content)
    {
        //Serialize Object
        string jsonObject = JsonConvert.SerializeObject(content);

        //Create Json UTF8 String Content
        return new StringContent(jsonObject, Encoding.UTF8, "application/json");
    }
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
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

```
{"isSuccess":true,"error":{"type":1,"message":"string","code":"string","validationErrors":{"property1":["string"],"property2":["string"]}},"data":{"createdCount":0,"skippedCount":0,"skippedTeams":["string"],"createdIds":["497f6eca-6276-4993-bfeb-53cbbbba6f08"]}}
```

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
  -H 'Accept: text/plain' \
  -H 'Authorization: Bearer {access-token}'

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
  'Accept':'text/plain',
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

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    
    
    /// Make a dummy request
    public async Task MakePutRequest()
    {
      int id = 1;
      string url = "/api/admin/tournaments/{tournamentId}";

      
      string json = @"{
  ""name"": ""string"",
  ""year"": 0,
  ""type"": 0,
  ""startDate"": ""2019-08-24T14:15:22Z"",
  ""endDate"": ""2019-08-24T14:15:22Z"",
  ""logoUrl"": ""string""
}";
      UpdateTournamentRequest content = JsonConvert.DeserializeObject(json);
      var result = await PutAsync(id, content, url);
      
          
    }

    /// Performs a PUT Request
    public async Task PutAsync(int id, UpdateTournamentRequest content, string url)
    {
        //Serialize Object
        StringContent jsonContent = SerializeObject(content);

        //Execute PUT request
        HttpResponseMessage response = await Client.PutAsync(url + $"/{id}", jsonContent);

        //Return response
        return await DeserializeObject(response);
    }
    
    
    /// Serialize an object to Json
    private StringContent SerializeObject(UpdateTournamentRequest content)
    {
        //Serialize Object
        string jsonObject = JsonConvert.SerializeObject(content);

        //Create Json UTF8 String Content
        return new StringContent(jsonObject, Encoding.UTF8, "application/json");
    }
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
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

```
{"isSuccess":true,"error":{"type":1,"message":"string","code":"string","validationErrors":{"property1":["string"],"property2":["string"]}},"data":{"id":"497f6eca-6276-4993-bfeb-53cbbbba6f08","name":"string","year":0,"type":0,"startDate":"2019-08-24T14:15:22Z","endDate":"2019-08-24T14:15:22Z","logoUrl":"string","isActive":true,"createdAt":"2019-08-24T14:15:22Z","updatedAt":"2019-08-24T14:15:22Z","teamCount":0,"matchCount":0,"leagueCount":0,"bonusQuestionCount":0}}
```

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
  -H 'Accept: text/plain' \
  -H 'Authorization: Bearer {access-token}'

```

```javascript

const headers = {
  'Accept':'text/plain',
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

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    
    
    
    /// Make a dummy request
    public async Task MakeDeleteRequest()
    {
      int id = 1;
      string url = "/api/admin/tournaments/{tournamentId}";

      await DeleteAsync(id, url);
    }

    /// Performs a DELETE Request
    public async Task DeleteAsync(int id, string url)
    {
        //Execute DELETE request
        HttpResponseMessage response = await Client.DeleteAsync(url + $"/{id}");

        //Return response
        await DeserializeObject(response);
    }
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
}

```

`DELETE /api/admin/tournaments/{tournamentId}`

<h3 id="delete__api_admin_tournaments_{tournamentid}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|tournamentId|path|string(uuid)|true|none|

> Example responses

> 200 Response

```
{"isSuccess":true,"error":{"type":1,"message":"string","code":"string","validationErrors":{"property1":["string"],"property2":["string"]}},"data":true}
```

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
  -H 'Accept: text/plain' \
  -H 'Authorization: Bearer {access-token}'

```

```javascript

const headers = {
  'Accept':'text/plain',
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

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    
    /// Make a dummy request
    public async Task MakePostRequest()
    {
      string url = "/api/admin/tournaments/{tournamentId}/activate";
      
      
      await PostAsync(null, url);
      
    }

    /// Performs a POST Request
    public async Task PostAsync(undefined content, string url)
    {
        //Serialize Object
        StringContent jsonContent = SerializeObject(content);

        //Execute POST request
        HttpResponseMessage response = await Client.PostAsync(url, jsonContent);
    }
    
    
    
    /// Serialize an object to Json
    private StringContent SerializeObject(undefined content)
    {
        //Serialize Object
        string jsonObject = JsonConvert.SerializeObject(content);

        //Create Json UTF8 String Content
        return new StringContent(jsonObject, Encoding.UTF8, "application/json");
    }
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
}

```

`POST /api/admin/tournaments/{tournamentId}/activate`

<h3 id="post__api_admin_tournaments_{tournamentid}_activate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|tournamentId|path|string(uuid)|true|none|

> Example responses

> 200 Response

```
{"isSuccess":true,"error":{"type":1,"message":"string","code":"string","validationErrors":{"property1":["string"],"property2":["string"]}},"data":true}
```

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
  -H 'Accept: text/plain' \
  -H 'Authorization: Bearer {access-token}'

```

```javascript

const headers = {
  'Accept':'text/plain',
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

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    
    /// Make a dummy request
    public async Task MakePostRequest()
    {
      string url = "/api/admin/tournaments/{tournamentId}/deactivate";
      
      
      await PostAsync(null, url);
      
    }

    /// Performs a POST Request
    public async Task PostAsync(undefined content, string url)
    {
        //Serialize Object
        StringContent jsonContent = SerializeObject(content);

        //Execute POST request
        HttpResponseMessage response = await Client.PostAsync(url, jsonContent);
    }
    
    
    
    /// Serialize an object to Json
    private StringContent SerializeObject(undefined content)
    {
        //Serialize Object
        string jsonObject = JsonConvert.SerializeObject(content);

        //Create Json UTF8 String Content
        return new StringContent(jsonObject, Encoding.UTF8, "application/json");
    }
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
}

```

`POST /api/admin/tournaments/{tournamentId}/deactivate`

<h3 id="post__api_admin_tournaments_{tournamentid}_deactivate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|tournamentId|path|string(uuid)|true|none|

> Example responses

> 200 Response

```
{"isSuccess":true,"error":{"type":1,"message":"string","code":"string","validationErrors":{"property1":["string"],"property2":["string"]}},"data":true}
```

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
  -H 'Accept: text/plain' \
  -H 'Authorization: Bearer {access-token}'

```

```javascript

const headers = {
  'Accept':'text/plain',
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

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    
    /// Make a dummy request
    public async Task MakePostRequest()
    {
      string url = "/api/admin/tournaments/{tournamentId}/standings/recalculate";
      
      
      await PostAsync(null, url);
      
    }

    /// Performs a POST Request
    public async Task PostAsync(undefined content, string url)
    {
        //Serialize Object
        StringContent jsonContent = SerializeObject(content);

        //Execute POST request
        HttpResponseMessage response = await Client.PostAsync(url, jsonContent);
    }
    
    
    
    /// Serialize an object to Json
    private StringContent SerializeObject(undefined content)
    {
        //Serialize Object
        string jsonObject = JsonConvert.SerializeObject(content);

        //Create Json UTF8 String Content
        return new StringContent(jsonObject, Encoding.UTF8, "application/json");
    }
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
}

```

`POST /api/admin/tournaments/{tournamentId}/standings/recalculate`

<h3 id="post__api_admin_tournaments_{tournamentid}_standings_recalculate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|tournamentId|path|string(uuid)|true|none|

> Example responses

> 200 Response

```
{"isSuccess":true,"error":{"type":1,"message":"string","code":"string","validationErrors":{"property1":["string"],"property2":["string"]}},"data":{"leaguesUpdated":0,"totalMembersUpdated":0}}
```

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
  -H 'Accept: text/plain' \
  -H 'Authorization: Bearer {access-token}'

```

```javascript

const headers = {
  'Accept':'text/plain',
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

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    /// Make a dummy request
    public async Task MakeGetRequest()
    {
      string url = "/api/admin/users";
      var result = await GetAsync(url);
    }

    /// Performs a GET Request
    public async Task GetAsync(string url)
    {
        //Start the request
        HttpResponseMessage response = await Client.GetAsync(url);

        //Validate result
        response.EnsureSuccessStatusCode();

    }
    
    
    
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
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

```
{"isSuccess":true,"error":{"type":1,"message":"string","code":"string","validationErrors":{"property1":["string"],"property2":["string"]}},"data":{"items":[{"id":"497f6eca-6276-4993-bfeb-53cbbbba6f08","username":"string","displayName":"string","email":"string","avatarUrl":"string","role":0,"isBanned":true,"lastLoginAt":"2019-08-24T14:15:22Z","createdAt":"2019-08-24T14:15:22Z"}],"totalCount":0,"page":0,"pageSize":0,"totalPages":0,"hasNextPage":true,"hasPreviousPage":true}}
```

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
  -H 'Accept: text/plain' \
  -H 'Authorization: Bearer {access-token}'

```

```javascript

const headers = {
  'Accept':'text/plain',
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

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    /// Make a dummy request
    public async Task MakeGetRequest()
    {
      string url = "/api/admin/users/{userId}";
      var result = await GetAsync(url);
    }

    /// Performs a GET Request
    public async Task GetAsync(string url)
    {
        //Start the request
        HttpResponseMessage response = await Client.GetAsync(url);

        //Validate result
        response.EnsureSuccessStatusCode();

    }
    
    
    
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
}

```

`GET /api/admin/users/{userId}`

<h3 id="get__api_admin_users_{userid}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|userId|path|string(uuid)|true|none|

> Example responses

> 200 Response

```
{"isSuccess":true,"error":{"type":1,"message":"string","code":"string","validationErrors":{"property1":["string"],"property2":["string"]}},"data":{"id":"497f6eca-6276-4993-bfeb-53cbbbba6f08","authUserId":"5a3cace6-919f-4109-8313-c3a2264a4134","username":"string","displayName":"string","email":"string","avatarUrl":"string","bio":"string","role":0,"isBanned":true,"favoriteTeamId":"d03f4e26-a6b7-4158-9c97-87bb7dc42e8b","favoriteTeamName":"string","lastLoginAt":"2019-08-24T14:15:22Z","createdAt":"2019-08-24T14:15:22Z","updatedAt":"2019-08-24T14:15:22Z","leagueCount":0,"ownedLeagueCount":0,"predictionCount":0}}
```

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
  -H 'Accept: text/plain' \
  -H 'Authorization: Bearer {access-token}'

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
  'Accept':'text/plain',
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

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    
    
    /// Make a dummy request
    public async Task MakePutRequest()
    {
      int id = 1;
      string url = "/api/admin/users/{userId}";

      
      string json = @"{
  ""username"": ""string"",
  ""displayName"": ""string"",
  ""email"": ""string"",
  ""bio"": ""string"",
  ""avatarUrl"": ""string""
}";
      UpdateAdminUserRequest content = JsonConvert.DeserializeObject(json);
      var result = await PutAsync(id, content, url);
      
          
    }

    /// Performs a PUT Request
    public async Task PutAsync(int id, UpdateAdminUserRequest content, string url)
    {
        //Serialize Object
        StringContent jsonContent = SerializeObject(content);

        //Execute PUT request
        HttpResponseMessage response = await Client.PutAsync(url + $"/{id}", jsonContent);

        //Return response
        return await DeserializeObject(response);
    }
    
    
    /// Serialize an object to Json
    private StringContent SerializeObject(UpdateAdminUserRequest content)
    {
        //Serialize Object
        string jsonObject = JsonConvert.SerializeObject(content);

        //Create Json UTF8 String Content
        return new StringContent(jsonObject, Encoding.UTF8, "application/json");
    }
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
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

```
{"isSuccess":true,"error":{"type":1,"message":"string","code":"string","validationErrors":{"property1":["string"],"property2":["string"]}},"data":{"id":"497f6eca-6276-4993-bfeb-53cbbbba6f08","authUserId":"5a3cace6-919f-4109-8313-c3a2264a4134","username":"string","displayName":"string","email":"string","avatarUrl":"string","bio":"string","role":0,"isBanned":true,"favoriteTeamId":"d03f4e26-a6b7-4158-9c97-87bb7dc42e8b","favoriteTeamName":"string","lastLoginAt":"2019-08-24T14:15:22Z","createdAt":"2019-08-24T14:15:22Z","updatedAt":"2019-08-24T14:15:22Z","leagueCount":0,"ownedLeagueCount":0,"predictionCount":0}}
```

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
  -H 'Accept: text/plain' \
  -H 'Authorization: Bearer {access-token}'

```

```javascript
const inputBody = '{
  "role": 0
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'text/plain',
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

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    
    /// Make a dummy request
    public async Task MakePostRequest()
    {
      string url = "/api/admin/users/{userId}/roles";
      
      string json = @"{
  ""role"": 0
}";
      UpdateUserRoleRequest content = JsonConvert.DeserializeObject(json);
      await PostAsync(content, url);
      
      
    }

    /// Performs a POST Request
    public async Task PostAsync(UpdateUserRoleRequest content, string url)
    {
        //Serialize Object
        StringContent jsonContent = SerializeObject(content);

        //Execute POST request
        HttpResponseMessage response = await Client.PostAsync(url, jsonContent);
    }
    
    
    
    /// Serialize an object to Json
    private StringContent SerializeObject(UpdateUserRoleRequest content)
    {
        //Serialize Object
        string jsonObject = JsonConvert.SerializeObject(content);

        //Create Json UTF8 String Content
        return new StringContent(jsonObject, Encoding.UTF8, "application/json");
    }
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
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

```
{"isSuccess":true,"error":{"type":1,"message":"string","code":"string","validationErrors":{"property1":["string"],"property2":["string"]}},"data":true}
```

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
  -H 'Accept: text/plain' \
  -H 'Authorization: Bearer {access-token}'

```

```javascript

const headers = {
  'Accept':'text/plain',
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

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    
    /// Make a dummy request
    public async Task MakePostRequest()
    {
      string url = "/api/admin/users/{userId}/ban";
      
      
      await PostAsync(null, url);
      
    }

    /// Performs a POST Request
    public async Task PostAsync(undefined content, string url)
    {
        //Serialize Object
        StringContent jsonContent = SerializeObject(content);

        //Execute POST request
        HttpResponseMessage response = await Client.PostAsync(url, jsonContent);
    }
    
    
    
    /// Serialize an object to Json
    private StringContent SerializeObject(undefined content)
    {
        //Serialize Object
        string jsonObject = JsonConvert.SerializeObject(content);

        //Create Json UTF8 String Content
        return new StringContent(jsonObject, Encoding.UTF8, "application/json");
    }
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
}

```

`POST /api/admin/users/{userId}/ban`

<h3 id="post__api_admin_users_{userid}_ban-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|userId|path|string(uuid)|true|none|

> Example responses

> 200 Response

```
{"isSuccess":true,"error":{"type":1,"message":"string","code":"string","validationErrors":{"property1":["string"],"property2":["string"]}},"data":true}
```

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
  -H 'Accept: text/plain' \
  -H 'Authorization: Bearer {access-token}'

```

```javascript

const headers = {
  'Accept':'text/plain',
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

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    
    /// Make a dummy request
    public async Task MakePostRequest()
    {
      string url = "/api/admin/users/{userId}/unban";
      
      
      await PostAsync(null, url);
      
    }

    /// Performs a POST Request
    public async Task PostAsync(undefined content, string url)
    {
        //Serialize Object
        StringContent jsonContent = SerializeObject(content);

        //Execute POST request
        HttpResponseMessage response = await Client.PostAsync(url, jsonContent);
    }
    
    
    
    /// Serialize an object to Json
    private StringContent SerializeObject(undefined content)
    {
        //Serialize Object
        string jsonObject = JsonConvert.SerializeObject(content);

        //Create Json UTF8 String Content
        return new StringContent(jsonObject, Encoding.UTF8, "application/json");
    }
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
}

```

`POST /api/admin/users/{userId}/unban`

<h3 id="post__api_admin_users_{userid}_unban-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|userId|path|string(uuid)|true|none|

> Example responses

> 200 Response

```
{"isSuccess":true,"error":{"type":1,"message":"string","code":"string","validationErrors":{"property1":["string"],"property2":["string"]}},"data":true}
```

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
  -H 'Accept: text/plain' \
  -H 'Authorization: Bearer {access-token}'

```

```javascript

const headers = {
  'Accept':'text/plain',
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

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    /// Make a dummy request
    public async Task MakeGetRequest()
    {
      string url = "/api/auth/me";
      var result = await GetAsync(url);
    }

    /// Performs a GET Request
    public async Task GetAsync(string url)
    {
        //Start the request
        HttpResponseMessage response = await Client.GetAsync(url);

        //Validate result
        response.EnsureSuccessStatusCode();

    }
    
    
    
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
}

```

`GET /api/auth/me`

> Example responses

> 200 Response

```
{"isSuccess":true,"error":{"type":1,"message":"string","code":"string","validationErrors":{"property1":["string"],"property2":["string"]}},"data":{"userId":"2c4a230c-5085-4924-a3e1-25fb4fc5965b","email":"string","displayName":"string","avatarUrl":"string","lastLoginAt":"2019-08-24T14:15:22Z","role":0}}
```

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
    "displayName": "string",
    "avatarUrl": "string",
    "lastLoginAt": "2019-08-24T14:15:22Z",
    "role": 0
  }
}
```

<h3 id="get__api_auth_me-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[CurrentUserResponseResult](#schemacurrentuserresponseresult)|

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
  -H 'Accept: text/plain' \
  -H 'Authorization: Bearer {access-token}'

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
  'Accept':'text/plain',
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

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    
    /// Make a dummy request
    public async Task MakePostRequest()
    {
      string url = "/api/bonus-predictions";
      
      string json = @"{
  ""leagueId"": ""58549e12-c6e6-4e03-99d1-6e916f71ce9a"",
  ""bonusQuestionId"": ""a0b61934-6fef-4d97-866d-54f4b60aee83"",
  ""answerTeamId"": ""ab2250dd-c194-4fab-a78b-360f3b350150"",
  ""answerText"": ""string""
}";
      SubmitBonusPredictionRequest content = JsonConvert.DeserializeObject(json);
      await PostAsync(content, url);
      
      
    }

    /// Performs a POST Request
    public async Task PostAsync(SubmitBonusPredictionRequest content, string url)
    {
        //Serialize Object
        StringContent jsonContent = SerializeObject(content);

        //Execute POST request
        HttpResponseMessage response = await Client.PostAsync(url, jsonContent);
    }
    
    
    
    /// Serialize an object to Json
    private StringContent SerializeObject(SubmitBonusPredictionRequest content)
    {
        //Serialize Object
        string jsonObject = JsonConvert.SerializeObject(content);

        //Create Json UTF8 String Content
        return new StringContent(jsonObject, Encoding.UTF8, "application/json");
    }
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
}

```

`POST /api/bonus-predictions`

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
|body|body|[SubmitBonusPredictionRequest](#schemasubmitbonuspredictionrequest)|false|none|

> Example responses

> 200 Response

```
{"isSuccess":true,"error":{"type":1,"message":"string","code":"string","validationErrors":{"property1":["string"],"property2":["string"]}},"data":"808ac6e4-93ed-4040-85a5-6c71a2444e90"}
```

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
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[GuidResult](#schemaguidresult)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

## get__api_bonus-predictions

> Code samples

```shell
# You can also use wget
curl -X GET /api/bonus-predictions \
  -H 'Accept: text/plain' \
  -H 'Authorization: Bearer {access-token}'

```

```javascript

const headers = {
  'Accept':'text/plain',
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

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    /// Make a dummy request
    public async Task MakeGetRequest()
    {
      string url = "/api/bonus-predictions";
      var result = await GetAsync(url);
    }

    /// Performs a GET Request
    public async Task GetAsync(string url)
    {
        //Start the request
        HttpResponseMessage response = await Client.GetAsync(url);

        //Validate result
        response.EnsureSuccessStatusCode();

    }
    
    
    
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
}

```

`GET /api/bonus-predictions`

<h3 id="get__api_bonus-predictions-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|leagueId|query|string(uuid)|false|none|

> Example responses

> 200 Response

```
{"isSuccess":true,"error":{"type":1,"message":"string","code":"string","validationErrors":{"property1":["string"],"property2":["string"]}},"data":[{"id":"497f6eca-6276-4993-bfeb-53cbbbba6f08","userId":"2c4a230c-5085-4924-a3e1-25fb4fc5965b","leagueId":"58549e12-c6e6-4e03-99d1-6e916f71ce9a","bonusQuestionId":"a0b61934-6fef-4d97-866d-54f4b60aee83","answerTeamId":"ab2250dd-c194-4fab-a78b-360f3b350150","answerText":"string","createdAt":"2019-08-24T14:15:22Z"}]}
```

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
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[BonusPredictionDtoListResult](#schemabonuspredictiondtolistresult)|

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
  -H 'Accept: text/plain' \
  -H 'Authorization: Bearer {access-token}'

```

```javascript

const headers = {
  'Accept':'text/plain',
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

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    /// Make a dummy request
    public async Task MakeGetRequest()
    {
      string url = "/api/bonus-questions";
      var result = await GetAsync(url);
    }

    /// Performs a GET Request
    public async Task GetAsync(string url)
    {
        //Start the request
        HttpResponseMessage response = await Client.GetAsync(url);

        //Validate result
        response.EnsureSuccessStatusCode();

    }
    
    
    
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
}

```

`GET /api/bonus-questions`

<h3 id="get__api_bonus-questions-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|tournamentId|query|string(uuid)|false|none|

> Example responses

> 200 Response

```
{"isSuccess":true,"error":{"type":1,"message":"string","code":"string","validationErrors":{"property1":["string"],"property2":["string"]}},"data":[{"id":"497f6eca-6276-4993-bfeb-53cbbbba6f08","tournamentId":"4a951104-9f98-4996-b388-a0ef2c00bb2a","questionType":0,"question":"string","points":0,"isResolved":true,"answerTeamId":"ab2250dd-c194-4fab-a78b-360f3b350150","answerText":"string"}]}
```

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
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[BonusQuestionDtoIReadOnlyListResult](#schemabonusquestiondtoireadonlylistresult)|

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
  -H 'Accept: text/plain' \
  -H 'Authorization: Bearer {access-token}'

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
  'Accept':'text/plain',
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

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    
    /// Make a dummy request
    public async Task MakePostRequest()
    {
      string url = "/api/bonus-questions";
      
      string json = @"{
  ""tournamentId"": ""4a951104-9f98-4996-b388-a0ef2c00bb2a"",
  ""questionType"": 0,
  ""question"": ""string"",
  ""points"": 0
}";
      CreateBonusQuestionRequest content = JsonConvert.DeserializeObject(json);
      await PostAsync(content, url);
      
      
    }

    /// Performs a POST Request
    public async Task PostAsync(CreateBonusQuestionRequest content, string url)
    {
        //Serialize Object
        StringContent jsonContent = SerializeObject(content);

        //Execute POST request
        HttpResponseMessage response = await Client.PostAsync(url, jsonContent);
    }
    
    
    
    /// Serialize an object to Json
    private StringContent SerializeObject(CreateBonusQuestionRequest content)
    {
        //Serialize Object
        string jsonObject = JsonConvert.SerializeObject(content);

        //Create Json UTF8 String Content
        return new StringContent(jsonObject, Encoding.UTF8, "application/json");
    }
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
}

```

`POST /api/bonus-questions`

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
|body|body|[CreateBonusQuestionRequest](#schemacreatebonusquestionrequest)|false|none|

> Example responses

> 200 Response

```
{"isSuccess":true,"error":{"type":1,"message":"string","code":"string","validationErrors":{"property1":["string"],"property2":["string"]}},"data":"808ac6e4-93ed-4040-85a5-6c71a2444e90"}
```

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
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[GuidResult](#schemaguidresult)|

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
  -H 'Accept: text/plain' \
  -H 'Authorization: Bearer {access-token}'

```

```javascript
const inputBody = '{
  "answerTeamId": "ab2250dd-c194-4fab-a78b-360f3b350150",
  "answerText": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'text/plain',
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

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    
    
    /// Make a dummy request
    public async Task MakePutRequest()
    {
      int id = 1;
      string url = "/api/bonus-questions/{id}/resolve";

      
      string json = @"{
  ""answerTeamId"": ""ab2250dd-c194-4fab-a78b-360f3b350150"",
  ""answerText"": ""string""
}";
      ResolveBonusQuestionRequest content = JsonConvert.DeserializeObject(json);
      var result = await PutAsync(id, content, url);
      
          
    }

    /// Performs a PUT Request
    public async Task PutAsync(int id, ResolveBonusQuestionRequest content, string url)
    {
        //Serialize Object
        StringContent jsonContent = SerializeObject(content);

        //Execute PUT request
        HttpResponseMessage response = await Client.PutAsync(url + $"/{id}", jsonContent);

        //Return response
        return await DeserializeObject(response);
    }
    
    
    /// Serialize an object to Json
    private StringContent SerializeObject(ResolveBonusQuestionRequest content)
    {
        //Serialize Object
        string jsonObject = JsonConvert.SerializeObject(content);

        //Create Json UTF8 String Content
        return new StringContent(jsonObject, Encoding.UTF8, "application/json");
    }
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
}

```

`PUT /api/bonus-questions/{id}/resolve`

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
|id|path|string(uuid)|true|none|
|body|body|[ResolveBonusQuestionRequest](#schemaresolvebonusquestionrequest)|false|none|

> Example responses

> 200 Response

```
{"isSuccess":true,"error":{"type":1,"message":"string","code":"string","validationErrors":{"property1":["string"],"property2":["string"]}},"data":0}
```

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
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[Int32Result](#schemaint32result)|

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
  -H 'Authorization: Bearer {access-token}'

```

```javascript

const headers = {
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

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    /// Make a dummy request
    public async Task MakeGetRequest()
    {
      string url = "/api/chat/messages";
      var result = await GetAsync(url);
    }

    /// Performs a GET Request
    public async Task GetAsync(string url)
    {
        //Start the request
        HttpResponseMessage response = await Client.GetAsync(url);

        //Validate result
        response.EnsureSuccessStatusCode();

    }
    
    
    
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
}

```

`GET /api/chat/messages`

<h3 id="get__api_chat_messages-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|leagueId|query|string(uuid)|false|none|
|cursor|query|string(date-time)|false|none|
|take|query|integer(int32)|false|none|

<h3 id="get__api_chat_messages-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|

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
  -H 'Accept: text/plain' \
  -H 'Authorization: Bearer {access-token}'

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
  'Accept':'text/plain',
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

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    
    /// Make a dummy request
    public async Task MakePostRequest()
    {
      string url = "/api/leagues";
      
      string json = @"{
  ""name"": ""string"",
  ""description"": ""string"",
  ""tournamentId"": ""4a951104-9f98-4996-b388-a0ef2c00bb2a"",
  ""isPublic"": true,
  ""maxMembers"": 0,
  ""imageUrl"": ""string""
}";
      CreateLeagueRequest content = JsonConvert.DeserializeObject(json);
      await PostAsync(content, url);
      
      
    }

    /// Performs a POST Request
    public async Task PostAsync(CreateLeagueRequest content, string url)
    {
        //Serialize Object
        StringContent jsonContent = SerializeObject(content);

        //Execute POST request
        HttpResponseMessage response = await Client.PostAsync(url, jsonContent);
    }
    
    
    
    /// Serialize an object to Json
    private StringContent SerializeObject(CreateLeagueRequest content)
    {
        //Serialize Object
        string jsonObject = JsonConvert.SerializeObject(content);

        //Create Json UTF8 String Content
        return new StringContent(jsonObject, Encoding.UTF8, "application/json");
    }
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
}

```

`POST /api/leagues`

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
|body|body|[CreateLeagueRequest](#schemacreateleaguerequest)|false|none|

> Example responses

> 200 Response

```
{"isSuccess":true,"error":{"type":1,"message":"string","code":"string","validationErrors":{"property1":["string"],"property2":["string"]}},"data":"808ac6e4-93ed-4040-85a5-6c71a2444e90"}
```

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
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[GuidResult](#schemaguidresult)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

## get__api_leagues

> Code samples

```shell
# You can also use wget
curl -X GET /api/leagues \
  -H 'Accept: text/plain' \
  -H 'Authorization: Bearer {access-token}'

```

```javascript

const headers = {
  'Accept':'text/plain',
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

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    /// Make a dummy request
    public async Task MakeGetRequest()
    {
      string url = "/api/leagues";
      var result = await GetAsync(url);
    }

    /// Performs a GET Request
    public async Task GetAsync(string url)
    {
        //Start the request
        HttpResponseMessage response = await Client.GetAsync(url);

        //Validate result
        response.EnsureSuccessStatusCode();

    }
    
    
    
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
}

```

`GET /api/leagues`

> Example responses

> 200 Response

```
{"isSuccess":true,"error":{"type":1,"message":"string","code":"string","validationErrors":{"property1":["string"],"property2":["string"]}},"data":[{"id":"497f6eca-6276-4993-bfeb-53cbbbba6f08","name":"string","description":"string","tournamentId":"4a951104-9f98-4996-b388-a0ef2c00bb2a","ownerId":"4d206909-730f-409a-88f6-dcfaa8fc28cc","inviteCode":"string","isPublic":true,"isGlobal":true,"maxMembers":0,"imageUrl":"string","memberCount":0,"myRank":0,"myTotalPoints":0}]}
```

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
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[LeagueListDtoIReadOnlyListResult](#schemaleaguelistdtoireadonlylistresult)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

## get__api_leagues_{id}

> Code samples

```shell
# You can also use wget
curl -X GET /api/leagues/{id} \
  -H 'Accept: text/plain' \
  -H 'Authorization: Bearer {access-token}'

```

```javascript

const headers = {
  'Accept':'text/plain',
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

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    /// Make a dummy request
    public async Task MakeGetRequest()
    {
      string url = "/api/leagues/{id}";
      var result = await GetAsync(url);
    }

    /// Performs a GET Request
    public async Task GetAsync(string url)
    {
        //Start the request
        HttpResponseMessage response = await Client.GetAsync(url);

        //Validate result
        response.EnsureSuccessStatusCode();

    }
    
    
    
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
}

```

`GET /api/leagues/{id}`

<h3 id="get__api_leagues_{id}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|none|

> Example responses

> 200 Response

```
{"isSuccess":true,"error":{"type":1,"message":"string","code":"string","validationErrors":{"property1":["string"],"property2":["string"]}},"data":{"id":"497f6eca-6276-4993-bfeb-53cbbbba6f08","name":"string","description":"string","tournamentId":"4a951104-9f98-4996-b388-a0ef2c00bb2a","ownerId":"4d206909-730f-409a-88f6-dcfaa8fc28cc","inviteCode":"string","isPublic":true,"isGlobal":true,"maxMembers":0,"imageUrl":"string","settings":{"id":"497f6eca-6276-4993-bfeb-53cbbbba6f08","leagueId":"58549e12-c6e6-4e03-99d1-6e916f71ce9a","predictionMode":"string","deadlineMinutes":0,"pointsCorrectScore":0,"pointsCorrectOutcome":0,"pointsCorrectGoals":0,"pointsRoundOf16Team":0,"pointsQuarterFinalTeam":0,"pointsSemiFinalTeam":0,"pointsFinalTeam":0,"pointsTopScorer":0,"pointsWinner":0,"pointsMostGoalsGroup":0,"pointsMostConcededGroup":0,"allowLateEdits":true},"members":[{"userId":"2c4a230c-5085-4924-a3e1-25fb4fc5965b","username":"string","avatarUrl":"string","joinedAt":"2019-08-24T14:15:22Z","isAdmin":true,"isMuted":true}],"memberCount":0,"myRank":0,"myTotalPoints":0,"isOwner":true}}
```

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
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[LeagueDtoResult](#schemaleaguedtoresult)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

## delete__api_leagues_{id}

> Code samples

```shell
# You can also use wget
curl -X DELETE /api/leagues/{id} \
  -H 'Accept: text/plain' \
  -H 'Authorization: Bearer {access-token}'

```

```javascript

const headers = {
  'Accept':'text/plain',
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

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    
    
    
    /// Make a dummy request
    public async Task MakeDeleteRequest()
    {
      int id = 1;
      string url = "/api/leagues/{id}";

      await DeleteAsync(id, url);
    }

    /// Performs a DELETE Request
    public async Task DeleteAsync(int id, string url)
    {
        //Execute DELETE request
        HttpResponseMessage response = await Client.DeleteAsync(url + $"/{id}");

        //Return response
        await DeserializeObject(response);
    }
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
}

```

`DELETE /api/leagues/{id}`

<h3 id="delete__api_leagues_{id}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|none|

> Example responses

> 200 Response

```
{"isSuccess":true,"error":{"type":1,"message":"string","code":"string","validationErrors":{"property1":["string"],"property2":["string"]}},"data":true}
```

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
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[BooleanResult](#schemabooleanresult)|

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
  -H 'Accept: text/plain' \
  -H 'Authorization: Bearer {access-token}'

```

```javascript
const inputBody = '{
  "inviteCode": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'text/plain',
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

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    
    /// Make a dummy request
    public async Task MakePostRequest()
    {
      string url = "/api/leagues/{id}/join";
      
      string json = @"{
  ""inviteCode"": ""string""
}";
      JoinLeagueRequest content = JsonConvert.DeserializeObject(json);
      await PostAsync(content, url);
      
      
    }

    /// Performs a POST Request
    public async Task PostAsync(JoinLeagueRequest content, string url)
    {
        //Serialize Object
        StringContent jsonContent = SerializeObject(content);

        //Execute POST request
        HttpResponseMessage response = await Client.PostAsync(url, jsonContent);
    }
    
    
    
    /// Serialize an object to Json
    private StringContent SerializeObject(JoinLeagueRequest content)
    {
        //Serialize Object
        string jsonObject = JsonConvert.SerializeObject(content);

        //Create Json UTF8 String Content
        return new StringContent(jsonObject, Encoding.UTF8, "application/json");
    }
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
}

```

`POST /api/leagues/{id}/join`

> Body parameter

```json
{
  "inviteCode": "string"
}
```

<h3 id="post__api_leagues_{id}_join-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|none|
|body|body|[JoinLeagueRequest](#schemajoinleaguerequest)|false|none|

> Example responses

> 200 Response

```
{"isSuccess":true,"error":{"type":1,"message":"string","code":"string","validationErrors":{"property1":["string"],"property2":["string"]}},"data":true}
```

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
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[BooleanResult](#schemabooleanresult)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

## post__api_leagues_{id}_leave

> Code samples

```shell
# You can also use wget
curl -X POST /api/leagues/{id}/leave \
  -H 'Accept: text/plain' \
  -H 'Authorization: Bearer {access-token}'

```

```javascript

const headers = {
  'Accept':'text/plain',
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

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    
    /// Make a dummy request
    public async Task MakePostRequest()
    {
      string url = "/api/leagues/{id}/leave";
      
      
      await PostAsync(null, url);
      
    }

    /// Performs a POST Request
    public async Task PostAsync(undefined content, string url)
    {
        //Serialize Object
        StringContent jsonContent = SerializeObject(content);

        //Execute POST request
        HttpResponseMessage response = await Client.PostAsync(url, jsonContent);
    }
    
    
    
    /// Serialize an object to Json
    private StringContent SerializeObject(undefined content)
    {
        //Serialize Object
        string jsonObject = JsonConvert.SerializeObject(content);

        //Create Json UTF8 String Content
        return new StringContent(jsonObject, Encoding.UTF8, "application/json");
    }
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
}

```

`POST /api/leagues/{id}/leave`

<h3 id="post__api_leagues_{id}_leave-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|none|

> Example responses

> 200 Response

```
{"isSuccess":true,"error":{"type":1,"message":"string","code":"string","validationErrors":{"property1":["string"],"property2":["string"]}},"data":true}
```

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
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[BooleanResult](#schemabooleanresult)|

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
  -H 'Accept: text/plain' \
  -H 'Authorization: Bearer {access-token}'

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
  'Accept':'text/plain',
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

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    
    
    /// Make a dummy request
    public async Task MakePutRequest()
    {
      int id = 1;
      string url = "/api/leagues/{id}/settings";

      
      string json = @"{
  ""predictionMode"": ""string"",
  ""deadlineMinutes"": 0,
  ""pointsCorrectScore"": 0,
  ""pointsCorrectOutcome"": 0,
  ""pointsCorrectGoals"": 0,
  ""pointsRoundOf16Team"": 0,
  ""pointsQuarterFinalTeam"": 0,
  ""pointsSemiFinalTeam"": 0,
  ""pointsFinalTeam"": 0,
  ""pointsTopScorer"": 0,
  ""pointsWinner"": 0,
  ""pointsMostGoalsGroup"": 0,
  ""pointsMostConcededGroup"": 0,
  ""allowLateEdits"": true
}";
      UpdateLeagueSettingsRequest content = JsonConvert.DeserializeObject(json);
      var result = await PutAsync(id, content, url);
      
          
    }

    /// Performs a PUT Request
    public async Task PutAsync(int id, UpdateLeagueSettingsRequest content, string url)
    {
        //Serialize Object
        StringContent jsonContent = SerializeObject(content);

        //Execute PUT request
        HttpResponseMessage response = await Client.PutAsync(url + $"/{id}", jsonContent);

        //Return response
        return await DeserializeObject(response);
    }
    
    
    /// Serialize an object to Json
    private StringContent SerializeObject(UpdateLeagueSettingsRequest content)
    {
        //Serialize Object
        string jsonObject = JsonConvert.SerializeObject(content);

        //Create Json UTF8 String Content
        return new StringContent(jsonObject, Encoding.UTF8, "application/json");
    }
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
}

```

`PUT /api/leagues/{id}/settings`

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
|id|path|string(uuid)|true|none|
|body|body|[UpdateLeagueSettingsRequest](#schemaupdateleaguesettingsrequest)|false|none|

> Example responses

> 200 Response

```
{"isSuccess":true,"error":{"type":1,"message":"string","code":"string","validationErrors":{"property1":["string"],"property2":["string"]}},"data":{"id":"497f6eca-6276-4993-bfeb-53cbbbba6f08","leagueId":"58549e12-c6e6-4e03-99d1-6e916f71ce9a","predictionMode":"string","deadlineMinutes":0,"pointsCorrectScore":0,"pointsCorrectOutcome":0,"pointsCorrectGoals":0,"pointsRoundOf16Team":0,"pointsQuarterFinalTeam":0,"pointsSemiFinalTeam":0,"pointsFinalTeam":0,"pointsTopScorer":0,"pointsWinner":0,"pointsMostGoalsGroup":0,"pointsMostConcededGroup":0,"allowLateEdits":true}}
```

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
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[LeagueSettingsDtoResult](#schemaleaguesettingsdtoresult)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

## get__api_leagues_{id}_standings

> Code samples

```shell
# You can also use wget
curl -X GET /api/leagues/{id}/standings \
  -H 'Accept: text/plain' \
  -H 'Authorization: Bearer {access-token}'

```

```javascript

const headers = {
  'Accept':'text/plain',
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

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    /// Make a dummy request
    public async Task MakeGetRequest()
    {
      string url = "/api/leagues/{id}/standings";
      var result = await GetAsync(url);
    }

    /// Performs a GET Request
    public async Task GetAsync(string url)
    {
        //Start the request
        HttpResponseMessage response = await Client.GetAsync(url);

        //Validate result
        response.EnsureSuccessStatusCode();

    }
    
    
    
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
}

```

`GET /api/leagues/{id}/standings`

<h3 id="get__api_leagues_{id}_standings-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|none|

> Example responses

> 200 Response

```
{"isSuccess":true,"error":{"type":1,"message":"string","code":"string","validationErrors":{"property1":["string"],"property2":["string"]}},"data":[{"userId":"2c4a230c-5085-4924-a3e1-25fb4fc5965b","username":"string","avatarUrl":"string","rank":0,"previousRank":0,"rankChange":0,"totalPoints":0,"matchPoints":0,"bonusPoints":0}]}
```

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
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[LeagueStandingDtoIReadOnlyListResult](#schemaleaguestandingdtoireadonlylistresult)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

## post__api_leagues_{id}_standings_recalculate

> Code samples

```shell
# You can also use wget
curl -X POST /api/leagues/{id}/standings/recalculate \
  -H 'Accept: text/plain' \
  -H 'Authorization: Bearer {access-token}'

```

```javascript

const headers = {
  'Accept':'text/plain',
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

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    
    /// Make a dummy request
    public async Task MakePostRequest()
    {
      string url = "/api/leagues/{id}/standings/recalculate";
      
      
      await PostAsync(null, url);
      
    }

    /// Performs a POST Request
    public async Task PostAsync(undefined content, string url)
    {
        //Serialize Object
        StringContent jsonContent = SerializeObject(content);

        //Execute POST request
        HttpResponseMessage response = await Client.PostAsync(url, jsonContent);
    }
    
    
    
    /// Serialize an object to Json
    private StringContent SerializeObject(undefined content)
    {
        //Serialize Object
        string jsonObject = JsonConvert.SerializeObject(content);

        //Create Json UTF8 String Content
        return new StringContent(jsonObject, Encoding.UTF8, "application/json");
    }
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
}

```

`POST /api/leagues/{id}/standings/recalculate`

<h3 id="post__api_leagues_{id}_standings_recalculate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|none|

> Example responses

> 200 Response

```
{"isSuccess":true,"error":{"type":1,"message":"string","code":"string","validationErrors":{"property1":["string"],"property2":["string"]}},"data":true}
```

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
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[BooleanResult](#schemabooleanresult)|

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
  -H 'Accept: text/plain' \
  -H 'Authorization: Bearer {access-token}'

```

```javascript

const headers = {
  'Accept':'text/plain',
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

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    /// Make a dummy request
    public async Task MakeGetRequest()
    {
      string url = "/api/matches";
      var result = await GetAsync(url);
    }

    /// Performs a GET Request
    public async Task GetAsync(string url)
    {
        //Start the request
        HttpResponseMessage response = await Client.GetAsync(url);

        //Validate result
        response.EnsureSuccessStatusCode();

    }
    
    
    
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
}

```

`GET /api/matches`

<h3 id="get__api_matches-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|tournamentId|query|string(uuid)|false|none|
|date|query|string(date)|false|none|

> Example responses

> 200 Response

```
{"isSuccess":true,"error":{"type":1,"message":"string","code":"string","validationErrors":{"property1":["string"],"property2":["string"]}},"data":[{"id":"497f6eca-6276-4993-bfeb-53cbbbba6f08","tournamentId":"4a951104-9f98-4996-b388-a0ef2c00bb2a","homeTeamId":"fb7b8236-8f4a-4255-b25d-a64d7c4d6968","homeTeamName":"string","homeTeamLogoUrl":"string","homeTeamFifaRank":0,"awayTeamId":"aa1734e3-668a-43b1-918b-ecab48ec02f9","awayTeamName":"string","awayTeamLogoUrl":"string","awayTeamFifaRank":0,"groupName":"string","venue":"string","matchDate":"2019-08-24T14:15:22Z","stage":0,"status":0,"homeScore":0,"awayScore":0}]}
```

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
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[MatchListItemDtoIReadOnlyListResult](#schemamatchlistitemdtoireadonlylistresult)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

## get__api_matches_{id}

> Code samples

```shell
# You can also use wget
curl -X GET /api/matches/{id} \
  -H 'Accept: text/plain' \
  -H 'Authorization: Bearer {access-token}'

```

```javascript

const headers = {
  'Accept':'text/plain',
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

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    /// Make a dummy request
    public async Task MakeGetRequest()
    {
      string url = "/api/matches/{id}";
      var result = await GetAsync(url);
    }

    /// Performs a GET Request
    public async Task GetAsync(string url)
    {
        //Start the request
        HttpResponseMessage response = await Client.GetAsync(url);

        //Validate result
        response.EnsureSuccessStatusCode();

    }
    
    
    
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
}

```

`GET /api/matches/{id}`

<h3 id="get__api_matches_{id}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|none|

> Example responses

> 200 Response

```
{"isSuccess":true,"error":{"type":1,"message":"string","code":"string","validationErrors":{"property1":["string"],"property2":["string"]}},"data":{"id":"497f6eca-6276-4993-bfeb-53cbbbba6f08","tournamentId":"4a951104-9f98-4996-b388-a0ef2c00bb2a","homeTeamId":"fb7b8236-8f4a-4255-b25d-a64d7c4d6968","homeTeam":{"id":"497f6eca-6276-4993-bfeb-53cbbbba6f08","tournamentId":"4a951104-9f98-4996-b388-a0ef2c00bb2a","name":"string","code":"string","flagUrl":"string","groupName":"string","fifaRank":0,"apiFootballId":0},"awayTeamId":"aa1734e3-668a-43b1-918b-ecab48ec02f9","awayTeam":{"id":"497f6eca-6276-4993-bfeb-53cbbbba6f08","tournamentId":"4a951104-9f98-4996-b388-a0ef2c00bb2a","name":"string","code":"string","flagUrl":"string","groupName":"string","fifaRank":0,"apiFootballId":0},"matchDate":"2019-08-24T14:15:22Z","stage":0,"status":0,"homeScore":0,"awayScore":0,"venue":"string","updatedAt":"2019-08-24T14:15:22Z"}}
```

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
      "code": "string",
      "flagUrl": "string",
      "groupName": "string",
      "fifaRank": 0,
      "apiFootballId": 0
    },
    "awayTeamId": "aa1734e3-668a-43b1-918b-ecab48ec02f9",
    "awayTeam": {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "tournamentId": "4a951104-9f98-4996-b388-a0ef2c00bb2a",
      "name": "string",
      "code": "string",
      "flagUrl": "string",
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
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[MatchDetailDtoResult](#schemamatchdetaildtoresult)|

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
  -H 'Accept: text/plain' \
  -H 'Authorization: Bearer {access-token}'

```

```javascript
const inputBody = '{
  "homeScore": 0,
  "awayScore": 0,
  "status": 0
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'text/plain',
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

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    
    
    /// Make a dummy request
    public async Task MakePutRequest()
    {
      int id = 1;
      string url = "/api/matches/{id}/result";

      
      string json = @"{
  ""homeScore"": 0,
  ""awayScore"": 0,
  ""status"": 0
}";
      UpdateMatchResultRequest content = JsonConvert.DeserializeObject(json);
      var result = await PutAsync(id, content, url);
      
          
    }

    /// Performs a PUT Request
    public async Task PutAsync(int id, UpdateMatchResultRequest content, string url)
    {
        //Serialize Object
        StringContent jsonContent = SerializeObject(content);

        //Execute PUT request
        HttpResponseMessage response = await Client.PutAsync(url + $"/{id}", jsonContent);

        //Return response
        return await DeserializeObject(response);
    }
    
    
    /// Serialize an object to Json
    private StringContent SerializeObject(UpdateMatchResultRequest content)
    {
        //Serialize Object
        string jsonObject = JsonConvert.SerializeObject(content);

        //Create Json UTF8 String Content
        return new StringContent(jsonObject, Encoding.UTF8, "application/json");
    }
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
}

```

`PUT /api/matches/{id}/result`

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
|id|path|string(uuid)|true|none|
|body|body|[UpdateMatchResultRequest](#schemaupdatematchresultrequest)|false|none|

> Example responses

> 200 Response

```
{"isSuccess":true,"error":{"type":1,"message":"string","code":"string","validationErrors":{"property1":["string"],"property2":["string"]}},"data":true}
```

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
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[BooleanResult](#schemabooleanresult)|

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
  -H 'Accept: text/plain' \
  -H 'Authorization: Bearer {access-token}'

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
  'Accept':'text/plain',
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

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    
    /// Make a dummy request
    public async Task MakePostRequest()
    {
      string url = "/api/predictions";
      
      string json = @"{
  ""leagueId"": ""58549e12-c6e6-4e03-99d1-6e916f71ce9a"",
  ""matchId"": ""685569fd-95e6-4335-9aa5-fdd22382bd9e"",
  ""homeScore"": 0,
  ""awayScore"": 0
}";
      SubmitPredictionRequest content = JsonConvert.DeserializeObject(json);
      await PostAsync(content, url);
      
      
    }

    /// Performs a POST Request
    public async Task PostAsync(SubmitPredictionRequest content, string url)
    {
        //Serialize Object
        StringContent jsonContent = SerializeObject(content);

        //Execute POST request
        HttpResponseMessage response = await Client.PostAsync(url, jsonContent);
    }
    
    
    
    /// Serialize an object to Json
    private StringContent SerializeObject(SubmitPredictionRequest content)
    {
        //Serialize Object
        string jsonObject = JsonConvert.SerializeObject(content);

        //Create Json UTF8 String Content
        return new StringContent(jsonObject, Encoding.UTF8, "application/json");
    }
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
}

```

`POST /api/predictions`

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
|body|body|[SubmitPredictionRequest](#schemasubmitpredictionrequest)|false|none|

> Example responses

> 200 Response

```
{"isSuccess":true,"error":{"type":1,"message":"string","code":"string","validationErrors":{"property1":["string"],"property2":["string"]}},"data":"808ac6e4-93ed-4040-85a5-6c71a2444e90"}
```

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
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[GuidResult](#schemaguidresult)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

## get__api_predictions

> Code samples

```shell
# You can also use wget
curl -X GET /api/predictions \
  -H 'Accept: text/plain' \
  -H 'Authorization: Bearer {access-token}'

```

```javascript

const headers = {
  'Accept':'text/plain',
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

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    /// Make a dummy request
    public async Task MakeGetRequest()
    {
      string url = "/api/predictions";
      var result = await GetAsync(url);
    }

    /// Performs a GET Request
    public async Task GetAsync(string url)
    {
        //Start the request
        HttpResponseMessage response = await Client.GetAsync(url);

        //Validate result
        response.EnsureSuccessStatusCode();

    }
    
    
    
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
}

```

`GET /api/predictions`

<h3 id="get__api_predictions-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|leagueId|query|string(uuid)|false|none|

> Example responses

> 200 Response

```
{"isSuccess":true,"error":{"type":1,"message":"string","code":"string","validationErrors":{"property1":["string"],"property2":["string"]}},"data":[{"id":"497f6eca-6276-4993-bfeb-53cbbbba6f08","userId":"2c4a230c-5085-4924-a3e1-25fb4fc5965b","leagueId":"58549e12-c6e6-4e03-99d1-6e916f71ce9a","matchId":"685569fd-95e6-4335-9aa5-fdd22382bd9e","homeScore":0,"awayScore":0,"pointsEarned":0,"createdAt":"2019-08-24T14:15:22Z","updatedAt":"2019-08-24T14:15:22Z"}]}
```

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
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[PredictionDtoListResult](#schemapredictiondtolistresult)|

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
  -H 'Accept: text/plain' \
  -H 'Authorization: Bearer {access-token}'

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
  'Accept':'text/plain',
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

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    
    /// Make a dummy request
    public async Task MakePostRequest()
    {
      string url = "/api/predictions/bulk";
      
      string json = @"{
  ""leagueId"": ""58549e12-c6e6-4e03-99d1-6e916f71ce9a"",
  ""predictions"": [
    {
      ""matchId"": ""685569fd-95e6-4335-9aa5-fdd22382bd9e"",
      ""homeScore"": 0,
      ""awayScore"": 0
    }
  ]
}";
      BulkSubmitPredictionsRequest content = JsonConvert.DeserializeObject(json);
      await PostAsync(content, url);
      
      
    }

    /// Performs a POST Request
    public async Task PostAsync(BulkSubmitPredictionsRequest content, string url)
    {
        //Serialize Object
        StringContent jsonContent = SerializeObject(content);

        //Execute POST request
        HttpResponseMessage response = await Client.PostAsync(url, jsonContent);
    }
    
    
    
    /// Serialize an object to Json
    private StringContent SerializeObject(BulkSubmitPredictionsRequest content)
    {
        //Serialize Object
        string jsonObject = JsonConvert.SerializeObject(content);

        //Create Json UTF8 String Content
        return new StringContent(jsonObject, Encoding.UTF8, "application/json");
    }
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
}

```

`POST /api/predictions/bulk`

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
|body|body|[BulkSubmitPredictionsRequest](#schemabulksubmitpredictionsrequest)|false|none|

> Example responses

> 200 Response

```
{"isSuccess":true,"error":{"type":1,"message":"string","code":"string","validationErrors":{"property1":["string"],"property2":["string"]}},"data":{"successCount":0,"failedCount":0,"results":[{"matchId":"685569fd-95e6-4335-9aa5-fdd22382bd9e","predictionId":"07ef3e55-acee-4631-909a-2d5902a608e6","success":true,"errorMessage":"string","errorCode":"string"}]}}
```

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
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[BulkSubmitPredictionsResultResult](#schemabulksubmitpredictionsresultresult)|

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
  -H 'Accept: text/plain' \
  -H 'Authorization: Bearer {access-token}'

```

```javascript
const inputBody = '{
  "homeScore": 0,
  "awayScore": 0
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'text/plain',
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

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    
    
    /// Make a dummy request
    public async Task MakePutRequest()
    {
      int id = 1;
      string url = "/api/predictions/{id}";

      
      string json = @"{
  ""homeScore"": 0,
  ""awayScore"": 0
}";
      UpdatePredictionRequest content = JsonConvert.DeserializeObject(json);
      var result = await PutAsync(id, content, url);
      
          
    }

    /// Performs a PUT Request
    public async Task PutAsync(int id, UpdatePredictionRequest content, string url)
    {
        //Serialize Object
        StringContent jsonContent = SerializeObject(content);

        //Execute PUT request
        HttpResponseMessage response = await Client.PutAsync(url + $"/{id}", jsonContent);

        //Return response
        return await DeserializeObject(response);
    }
    
    
    /// Serialize an object to Json
    private StringContent SerializeObject(UpdatePredictionRequest content)
    {
        //Serialize Object
        string jsonObject = JsonConvert.SerializeObject(content);

        //Create Json UTF8 String Content
        return new StringContent(jsonObject, Encoding.UTF8, "application/json");
    }
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
}

```

`PUT /api/predictions/{id}`

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
|id|path|string(uuid)|true|none|
|body|body|[UpdatePredictionRequest](#schemaupdatepredictionrequest)|false|none|

> Example responses

> 200 Response

```
{"isSuccess":true,"error":{"type":1,"message":"string","code":"string","validationErrors":{"property1":["string"],"property2":["string"]}},"data":true}
```

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
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[BooleanResult](#schemabooleanresult)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

## get__api_predictions_match_{matchId}

> Code samples

```shell
# You can also use wget
curl -X GET /api/predictions/match/{matchId} \
  -H 'Accept: text/plain' \
  -H 'Authorization: Bearer {access-token}'

```

```javascript

const headers = {
  'Accept':'text/plain',
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

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    /// Make a dummy request
    public async Task MakeGetRequest()
    {
      string url = "/api/predictions/match/{matchId}";
      var result = await GetAsync(url);
    }

    /// Performs a GET Request
    public async Task GetAsync(string url)
    {
        //Start the request
        HttpResponseMessage response = await Client.GetAsync(url);

        //Validate result
        response.EnsureSuccessStatusCode();

    }
    
    
    
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
}

```

`GET /api/predictions/match/{matchId}`

<h3 id="get__api_predictions_match_{matchid}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|matchId|path|string(uuid)|true|none|
|leagueId|query|string(uuid)|false|none|

> Example responses

> 200 Response

```
{"isSuccess":true,"error":{"type":1,"message":"string","code":"string","validationErrors":{"property1":["string"],"property2":["string"]}},"data":{"id":"497f6eca-6276-4993-bfeb-53cbbbba6f08","userId":"2c4a230c-5085-4924-a3e1-25fb4fc5965b","leagueId":"58549e12-c6e6-4e03-99d1-6e916f71ce9a","matchId":"685569fd-95e6-4335-9aa5-fdd22382bd9e","homeScore":0,"awayScore":0,"pointsEarned":0,"createdAt":"2019-08-24T14:15:22Z","updatedAt":"2019-08-24T14:15:22Z"}}
```

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
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[PredictionDtoResult](#schemapredictiondtoresult)|

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
  -H 'Accept: text/plain' \
  -H 'Authorization: Bearer {access-token}'

```

```javascript

const headers = {
  'Accept':'text/plain',
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

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    /// Make a dummy request
    public async Task MakeGetRequest()
    {
      string url = "/api/teams";
      var result = await GetAsync(url);
    }

    /// Performs a GET Request
    public async Task GetAsync(string url)
    {
        //Start the request
        HttpResponseMessage response = await Client.GetAsync(url);

        //Validate result
        response.EnsureSuccessStatusCode();

    }
    
    
    
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
}

```

`GET /api/teams`

<h3 id="get__api_teams-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|tournamentId|query|string(uuid)|false|none|

> Example responses

> 200 Response

```
{"isSuccess":true,"error":{"type":1,"message":"string","code":"string","validationErrors":{"property1":["string"],"property2":["string"]}},"data":[{"id":"497f6eca-6276-4993-bfeb-53cbbbba6f08","tournamentId":"4a951104-9f98-4996-b388-a0ef2c00bb2a","name":"string","code":"string","flagUrl":"string","groupName":"string","fifaRank":0,"apiFootballId":0}]}
```

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
      "code": "string",
      "flagUrl": "string",
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
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[TeamDtoIReadOnlyListResult](#schemateamdtoireadonlylistresult)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

## get__api_teams_{id}

> Code samples

```shell
# You can also use wget
curl -X GET /api/teams/{id} \
  -H 'Accept: text/plain' \
  -H 'Authorization: Bearer {access-token}'

```

```javascript

const headers = {
  'Accept':'text/plain',
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

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    /// Make a dummy request
    public async Task MakeGetRequest()
    {
      string url = "/api/teams/{id}";
      var result = await GetAsync(url);
    }

    /// Performs a GET Request
    public async Task GetAsync(string url)
    {
        //Start the request
        HttpResponseMessage response = await Client.GetAsync(url);

        //Validate result
        response.EnsureSuccessStatusCode();

    }
    
    
    
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
}

```

`GET /api/teams/{id}`

<h3 id="get__api_teams_{id}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|none|

> Example responses

> 200 Response

```
{"isSuccess":true,"error":{"type":1,"message":"string","code":"string","validationErrors":{"property1":["string"],"property2":["string"]}},"data":{"id":"497f6eca-6276-4993-bfeb-53cbbbba6f08","tournamentId":"4a951104-9f98-4996-b388-a0ef2c00bb2a","name":"string","code":"string","flagUrl":"string","groupName":"string","fifaRank":0,"apiFootballId":0}}
```

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
    "code": "string",
    "flagUrl": "string",
    "groupName": "string",
    "fifaRank": 0,
    "apiFootballId": 0
  }
}
```

<h3 id="get__api_teams_{id}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[TeamDtoResult](#schemateamdtoresult)|

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
  -H 'Accept: text/plain' \
  -H 'Authorization: Bearer {access-token}'

```

```javascript

const headers = {
  'Accept':'text/plain',
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

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    /// Make a dummy request
    public async Task MakeGetRequest()
    {
      string url = "/api/tournaments";
      var result = await GetAsync(url);
    }

    /// Performs a GET Request
    public async Task GetAsync(string url)
    {
        //Start the request
        HttpResponseMessage response = await Client.GetAsync(url);

        //Validate result
        response.EnsureSuccessStatusCode();

    }
    
    
    
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
}

```

`GET /api/tournaments`

<h3 id="get__api_tournaments-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|onlyActive|query|boolean|false|none|

> Example responses

> 200 Response

```
{"isSuccess":true,"error":{"type":1,"message":"string","code":"string","validationErrors":{"property1":["string"],"property2":["string"]}},"data":[{"id":"497f6eca-6276-4993-bfeb-53cbbbba6f08","name":"string","year":0,"type":0,"startDate":"2019-08-24T14:15:22Z","endDate":"2019-08-24T14:15:22Z","country":"string","logoUrl":"string","isActive":true}]}
```

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
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[TournamentDtoIReadOnlyListResult](#schematournamentdtoireadonlylistresult)|

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
  -H 'Accept: text/plain' \
  -H 'Authorization: Bearer {access-token}'

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
  'Accept':'text/plain',
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

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    
    /// Make a dummy request
    public async Task MakePostRequest()
    {
      string url = "/api/tournaments";
      
      string json = @"{
  ""name"": ""string"",
  ""year"": 0,
  ""type"": 0,
  ""startDate"": ""2019-08-24T14:15:22Z"",
  ""endDate"": ""2019-08-24T14:15:22Z"",
  ""country"": ""string"",
  ""logoUrl"": ""string""
}";
      CreateTournamentCommand content = JsonConvert.DeserializeObject(json);
      await PostAsync(content, url);
      
      
    }

    /// Performs a POST Request
    public async Task PostAsync(CreateTournamentCommand content, string url)
    {
        //Serialize Object
        StringContent jsonContent = SerializeObject(content);

        //Execute POST request
        HttpResponseMessage response = await Client.PostAsync(url, jsonContent);
    }
    
    
    
    /// Serialize an object to Json
    private StringContent SerializeObject(CreateTournamentCommand content)
    {
        //Serialize Object
        string jsonObject = JsonConvert.SerializeObject(content);

        //Create Json UTF8 String Content
        return new StringContent(jsonObject, Encoding.UTF8, "application/json");
    }
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
}

```

`POST /api/tournaments`

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
|body|body|[CreateTournamentCommand](#schemacreatetournamentcommand)|false|none|

> Example responses

> 200 Response

```
{"isSuccess":true,"error":{"type":1,"message":"string","code":"string","validationErrors":{"property1":["string"],"property2":["string"]}},"data":"808ac6e4-93ed-4040-85a5-6c71a2444e90"}
```

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
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[GuidResult](#schemaguidresult)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Bearer
</aside>

## get__api_tournaments_{id}

> Code samples

```shell
# You can also use wget
curl -X GET /api/tournaments/{id} \
  -H 'Accept: text/plain' \
  -H 'Authorization: Bearer {access-token}'

```

```javascript

const headers = {
  'Accept':'text/plain',
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

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    /// Make a dummy request
    public async Task MakeGetRequest()
    {
      string url = "/api/tournaments/{id}";
      var result = await GetAsync(url);
    }

    /// Performs a GET Request
    public async Task GetAsync(string url)
    {
        //Start the request
        HttpResponseMessage response = await Client.GetAsync(url);

        //Validate result
        response.EnsureSuccessStatusCode();

    }
    
    
    
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
}

```

`GET /api/tournaments/{id}`

<h3 id="get__api_tournaments_{id}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|none|

> Example responses

> 200 Response

```
{"isSuccess":true,"error":{"type":1,"message":"string","code":"string","validationErrors":{"property1":["string"],"property2":["string"]}},"data":{"id":"497f6eca-6276-4993-bfeb-53cbbbba6f08","name":"string","year":0,"type":0,"startDate":"2019-08-24T14:15:22Z","endDate":"2019-08-24T14:15:22Z","country":"string","logoUrl":"string","isActive":true}}
```

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
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[TournamentDtoResult](#schematournamentdtoresult)|

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
  -H 'Accept: text/plain' \
  -H 'Authorization: Bearer {access-token}'

```

```javascript
const inputBody = '{
  "File": "string"
}';
const headers = {
  'Content-Type':'multipart/form-data',
  'Accept':'text/plain',
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

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    
    /// Make a dummy request
    public async Task MakePostRequest()
    {
      string url = "/api/users/avatar";
      
      
      await PostAsync(null, url);
      
    }

    /// Performs a POST Request
    public async Task PostAsync(undefined content, string url)
    {
        //Serialize Object
        StringContent jsonContent = SerializeObject(content);

        //Execute POST request
        HttpResponseMessage response = await Client.PostAsync(url, jsonContent);
    }
    
    
    
    /// Serialize an object to Json
    private StringContent SerializeObject(undefined content)
    {
        //Serialize Object
        string jsonObject = JsonConvert.SerializeObject(content);

        //Create Json UTF8 String Content
        return new StringContent(jsonObject, Encoding.UTF8, "application/json");
    }
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
}

```

`POST /api/users/avatar`

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

```
{"isSuccess":true,"error":{"type":1,"message":"string","code":"string","validationErrors":{"property1":["string"],"property2":["string"]}},"data":"string"}
```

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
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[StringResult](#schemastringresult)|

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
  "homeTeamFlagUrl": "string",
  "awayTeamId": "aa1734e3-668a-43b1-918b-ecab48ec02f9",
  "awayTeamName": "string",
  "awayTeamCode": "string",
  "awayTeamFlagUrl": "string",
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
|homeTeamFlagUrl|string¦null|false|none|none|
|awayTeamId|string(uuid)|false|none|none|
|awayTeamName|string¦null|false|none|none|
|awayTeamCode|string¦null|false|none|none|
|awayTeamFlagUrl|string¦null|false|none|none|
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
    "homeTeamFlagUrl": "string",
    "awayTeamId": "aa1734e3-668a-43b1-918b-ecab48ec02f9",
    "awayTeamName": "string",
    "awayTeamCode": "string",
    "awayTeamFlagUrl": "string",
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
  "flagUrl": "string",
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
|flagUrl|string¦null|false|none|none|
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
    "flagUrl": "string",
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
  "displayName": "string",
  "avatarUrl": "string",
  "lastLoginAt": "2019-08-24T14:15:22Z",
  "role": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|userId|string(uuid)|false|none|none|
|email|string¦null|false|none|none|
|displayName|string¦null|false|none|none|
|avatarUrl|string¦null|false|none|none|
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
    "displayName": "string",
    "avatarUrl": "string",
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
    "code": "string",
    "flagUrl": "string",
    "groupName": "string",
    "fifaRank": 0,
    "apiFootballId": 0
  },
  "awayTeamId": "aa1734e3-668a-43b1-918b-ecab48ec02f9",
  "awayTeam": {
    "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
    "tournamentId": "4a951104-9f98-4996-b388-a0ef2c00bb2a",
    "name": "string",
    "code": "string",
    "flagUrl": "string",
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
      "code": "string",
      "flagUrl": "string",
      "groupName": "string",
      "fifaRank": 0,
      "apiFootballId": 0
    },
    "awayTeamId": "aa1734e3-668a-43b1-918b-ecab48ec02f9",
    "awayTeam": {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "tournamentId": "4a951104-9f98-4996-b388-a0ef2c00bb2a",
      "name": "string",
      "code": "string",
      "flagUrl": "string",
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
  "code": "string",
  "flagUrl": "string",
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
|code|string¦null|false|none|none|
|flagUrl|string¦null|false|none|none|
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
      "code": "string",
      "flagUrl": "string",
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
    "code": "string",
    "flagUrl": "string",
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

