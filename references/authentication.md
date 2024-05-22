---
title: Authentication
description: Learn how to authenticate and access Scrapebet.
---

### Create your token

Before doing your first request, you will need to **get or create an API token.** You can do this easily accessing to [our website](https://scrapebet.com).

### Adding your API key

In order to make any request, you will need to attach **to every call** the following request header including your token of course!

If the token format is not valid a `400` HTTP code will be sent. In any other case a `403` HTTP code response will be returned.

| Header      | Value       |
| ----------- | ----------- |
| X-Token-Key | Your token. |

{%hint danger%}
Don't share your token publicly! You **must** keep it on your server side.
{%endhint%}

### Authentication error codes

| Error code               | Meaning                                                                                                                                 |
| ------------------------ | --------------------------------------------------------------------------------------------------------------------------------------- |
| `TOKEN_NOT_SET`          | X-Token-Key header was not set.                                                                                                         |
| `TOKEN_FORMAT_INCORRECT` | <p>The authentication header was set but the value format is not valid.</p><p></p><p>It should be a 32-length alphanumeric string. </p> |
| `TOKEN_NOT_VALID`        | If the token format is valid but we can't still authenticate it may not be vinculated with any account.                                 |


### Make your first request

### API connection examples in different languages

<details>
<summary>PHP</summary>

### PHP

```php
<?php

require 'vendor/autoload.php';

class ScrapebetClient {
    protected $token;
    private $client;

    function __construct($config = []) {
        if (isset($config["token"])) {
            $this->token = $config["token"];
        }

        $this->client = new GuzzleHttp\Client([
            "base_uri" => "https://api.scrapebet.com/v1/",
            'http_errors' => false,
            'headers' => [
                "X-Token-Key" => $this->token
            ]
        ]);

        return $this;
    }

    public function getExampleEndpoint() {
        $response = $this->client->get('example-endpoint');
        return json_decode($response->getBody(), true);
    }
}

$config = ["token" => "your_api_token"];
$scrapebetClient = new ScrapebetClient($config);
$result = $scrapebetClient->getExampleEndpoint();

print_r($result);
?>

```

</details>
<details>
<summary>JavaScript</summary>

### JavaScript

```JavaScript
const axios = require("axios");

const scrapebetClient = axios.create({
  baseURL: "https://api.scrapebet.com/v1",
  heaaders: {
    "X-Token-Key": "your_token_here",
  },
});

async function getEndpoint() {
  try {
    const response = await scrapebetClient.get(
      "/sports?token=your_token_here"
    );
    console.log(response.data);
  } catch (error) {
    console.error("Error fetching data: ", error);
  }
}

getEndpoint();
```

</details>
<details>
<summary>Python</summary>

### Python

```Python
import requests

class ScrapebetClient:
    def __init__(self, config={}):
        self.token = config.get("token")
        self.base_url = "https://api.scrapebet.com/v1"
        self.headers = {
            "X-Token-Key": self.token
        }

    def getEndpoint(self):
        response = requests.get(f"{self.base_url}/endpoint", headers=self.headers)
        if response.status_code == 200:
            return response.json()
        else:
            response.raise_for_status()


config = {"token": "YOUR_TOKEN"}
scrapebet_client = ScrapebetClient(config)


try:
    result = scrapebet_client.getEndpoint()
    print(result)
except requests.exceptions.RequestException as e:
    print(f"Error fetching data: {e}")
```

</details>
<details>
<summary>Go</summary>

### Go

```Go
package main

import (
	"encoding/json"
	"fmt"
	"io/ioutil"
	"net/http"
)

type ScrapebetClient struct {
	token   string
	baseURL string
}

func NewScapebetClient(token string) *ScrapebetClient {
	return &ScrapebetClient{
		token:   token,
		baseURL: "https://api.scrapebet.com/v1",
	}
}

func (client *ScrapebetClient) getEndpoint() (map[string]interface{}, error) {
	req, err := http.NewRequest("GET", client.baseURL+"/your-endpoint", nil)
	if err != nil {
		return nil, err
	}

	req.Header.Set("X-Token-Key", client.token)
	resp, err := http.DefaultClient.Do(req)
	if err != nil {
		return nil, err
	}
	defer resp.Body.Close()

	if resp.StatusCode != http.StatusOK {
		return nil, fmt.Errorf("Unexpected status code: %d", resp.StatusCode)
	}

	body, err := ioutil.ReadAll(resp.Body)
	if err != nil {
		return nil, err
	}

	var result map[string]interface{}
	if err := json.Unmarshal(body, &result); err != nil {
		return nil, err
	}

	return result, nil
}

func main() {
	client := NewScapebetClient("your-token-key")
	result, err := client.getEndpoint()
	if err != nil {
		fmt.Printf("Error fetching data: %v\n", err)
	}

	fmt.Printf("Result: %v\n", result)
}

```

</details>
