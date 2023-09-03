<p align="center">
  <a href="http://nestjs.com/" target="blank"><img src="https://nestjs.com/img/logo-small.svg" width="200" alt="Nest Logo" /></a>
</p>

# Search system

## Backend codebase for search system project

<p><strong>Backend Service Overview</strong></p>

<ol>
  <li>Sends a user request to Google Search.</li>
  <li>Analyzes the response and, if the first 10 search results contain a link to Wikipedia, parses the text of the article (first paragraph) and displays it along with an associated picture as a search result.</li>
  <li>If there are no links to Wikipedia in the search results, it simply displays the search results.</li>
  <li>To simulate a slow service, the backend introduces a 5-second delay before providing results.</li>
  <li>The backend caches the last 10 requests and responses in memory. If the result is in the cache, it's served instantly without any delay.</li>
  <li>In the case of a request that is already being processed, it doesn't initiate a second request. Instead, it waits for the first request to complete and then returns the result.</li>
</ol>


### Create .env file

```bash
  cp .env.example .env
```

### Launch docker containers

```bash
  docker compose up -d --build
```

### Request example

```bash
  curl --location 'http://localhost:3000/api/search?q=reddit%20wikipedia'
```
