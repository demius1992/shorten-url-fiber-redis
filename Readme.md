# Go URL Shortener

This project is a URL shortener implemented using Go, Fiber web framework, and Redis as a database. The URL shortener
allows users to create short aliases for long URLs. When a user visits the short URL, they are redirected to the
original long URL. The purpose of this project is to provide a simple way to shorten URLs for convenience and easy
sharing.

## Requirements

To run this project, you will need to have Go, Docker and docker-compose installed on your system.

1. Go (v1.16 or higher) - Install Go ([go.dev](https://go.dev/dl/))
2. Docker (v 20.10.23) - Install Docker ([docker.com](https://docs.docker.com/engine/install/))
3. Docker-compose (v 1.29.2) - Install Docker-compose([docker.com](https://docs.docker.com/compose/install/))

## Installation

Clone this repository.

```bash
git clone https://github.com/demius1992/shorten-url-fiber-redis
```

Use docker-compose to run the app

```bash
cd shorten-url-fiber-redis
docker-compose up -d
```

## Usage

Once the application is running, you can create short URLs by sending a POST request to the "/api/v1" endpoint with the
url parameter set to the long URL that you want to shorten. The server will respond with a JSON object containing the
short URL.

```Copy code
POST /api/shorten HTTP/1.1
Content-Type: application/json

{"url": "https://www.example.com/very/long/url/that/i/want/to/shorten"}
```

responce

```
{
"shortUrl": "http://localhost:3000/xyz123"
}
```

You can then use the short URL to redirect to the long URL by visiting it in your web browser.

## Configuration

The configuration options for the application are stored in the .env file in the project directory. The available
options are:

- DB_ADDR="db:6379"
- DB_PASS=""
- APP_PORT=":3000"
- DOMAIN="localhost:3000"
- API_QUOTA=10


