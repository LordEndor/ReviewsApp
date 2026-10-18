# Review Meme Maker

A mobile-first, single-page app for making joke reviews styled like Google, Amazon, Yelp, Tripadvisor, Trustpilot and App Store reviews — for memes with friends.

- Pick a platform, fill in the reviewer, stars, date, title and text
- Live preview, then **Save image** to download a PNG (or share it straight from your phone)
- 🎲 *Surprise me* fills in a ready-made joke review

No build step: open `index.html` in a browser, or enable GitHub Pages on this repo.

For fun only — please don't post these as real reviews.

## Run with Docker Compose

On your server (with Docker and the Compose plugin installed):

```sh
git clone https://github.com/LordEndor/ReviewsApp.git
cd ReviewsApp
docker compose up -d --build
```

The app is then served at `http://<your-server>:8080`. To use another port, set `PORT`:

```sh
PORT=3000 docker compose up -d --build
```

(or put `PORT=3000` in a `.env` file next to `docker-compose.yaml`).

To update after pulling new changes, run `git pull && docker compose up -d --build`. Stop it with `docker compose down`.

## Deploy with Coolify

Create a new resource from this repository and pick **Docker Compose** as the build pack. Coolify reads `/docker-compose.yaml`, builds the image and gives the app a domain automatically (you can change it under the service's **Domains** setting). The host port mapping lives in `docker-compose.override.yaml`, which Coolify ignores, so nothing clashes with other apps on the server.
