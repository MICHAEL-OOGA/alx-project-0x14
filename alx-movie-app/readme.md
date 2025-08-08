# alx-project-0x14

## API Overview

The **MoviesDatabase API** is a RESTful API that provides detailed information about movies, TV shows, and actors. It allows developers to search for films, retrieve metadata, access cast and crew information, and explore related content. The API is hosted on RapidAPI and supports pagination, filtering, and sorting to make data retrieval efficient.

Key features include:

- Search movies, TV shows, and people by keyword.
- Retrieve details for specific movies or TV shows using unique IDs.
- Access cast, crew, and production details.
- Explore similar or related titles.
- Paginated responses for large datasets.

## Version

**Current Version:** 1.0.0

## Available Endpoints

| Endpoint                       | Method | Description                                                                 |
| ------------------------------ | ------ | --------------------------------------------------------------------------- |
| `/titles`                      | GET    | Retrieves a list of movie or TV show titles with optional filters.          |
| `/titles/{id}`                 | GET    | Retrieves detailed information about a specific movie or TV show by its ID. |
| `/titles/search/title/{title}` | GET    | Searches for movies or TV shows by title keyword.                           |
| `/titles/{id}/cast`            | GET    | Retrieves cast information for a specific title.                            |
| `/titles/{id}/crew`            | GET    | Retrieves crew and production details for a specific title.                 |
| `/titles/utils/genres`         | GET    | Lists all available genres in the database.                                 |
| `/titles/utils/languages`      | GET    | Lists all available spoken languages in the database.                       |
| `/titles/random`               | GET    | Returns a random title from the database.                                   |

## Request and Response Format

### Request Example

```http
GET /titles/search/title/inception
Host: moviesdatabase.p.rapidapi.com
X-RapidAPI-Key: YOUR_API_KEY
X-RapidAPI-Host: moviesdatabase.p.rapidapi.com

Request Structure
Method: GET

Base URL: https://moviesdatabase.p.rapidapi.com

Headers:

X-RapidAPI-Key: Your personal API key from RapidAPI.

X-RapidAPI-Host: moviesdatabase.p.rapidapi.com

Query Parameters (optional):

page: Specifies the page number for paginated results.

limit: Limits the number of results returned per page.

genre: Filters titles by genre.

Response Structure
page (number): The current page of results.

results (array): An array of movie or TV show objects.

id (string): The IMDb ID of the title.

title (string): The name of the movie or show.

year (number): Release year.

type (string): Type of title (movie, tvSeries, etc.).

genres (array): List of genres.

plot (string): Short description of the movie/show.

Authentication
The MoviesDatabase API requires authentication via RapidAPI. You must:

Sign up or log in to RapidAPI.

Subscribe to the MoviesDatabase API.

Obtain your X-RapidAPI-Key.

Include the following headers in every request:

http
Copy
Edit
X-RapidAPI-Key: YOUR_API_KEY
X-RapidAPI-Host: moviesdatabase.p.rapidapi.com
Error Handling
Status Code	Meaning	Possible Causes	Handling Tips
400	Bad Request	Invalid parameters or malformed request. -	Double-check request syntax and parameters.
401	Unauthorized	Missing or invalid API key. -	Ensure your API key is correct and included in headers.
404	Not Found	Resource does not exist.	- Check the endpoint path and parameters.
429	Too Many Requests	Rate limit exceeded. -	Implement request throttling or delay retries.
500	Internal Server Error	API server issue. -	Retry after some time or report to API provider.

Usage Limits and Best Practices
Usage Limits
Rate Limit: As specified in your RapidAPI subscription plan (typically limited requests per minute/day).

Pagination: Use page and limit parameters to avoid over-fetching data.

Random Endpoint Limitations: The /titles/random endpoint may return the same title if called repeatedly in a short timeframe.

Best Practices
Cache responses for frequently requested data to reduce API calls.

Handle errors gracefully to improve user experience.

Use filters and query parameters to minimize unnecessary data transfer.

Respect the rate limits to avoid temporary bans.

Secure your API key — never expose it in public repositories.
```
