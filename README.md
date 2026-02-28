# Social to Mealie PWA

This project is a modern, standalone Progressive Web App (PWA) client built for the [Social to Mealie](https://github.com/GerardPolloRebozado/social-to-mealie) backend service.

It allows you to easily import recipes from social media platforms directly into your [Mealie](https://github.com/mealie-recipes/mealie) instance using a beautiful, responsive mobile-first interface. Because it is a PWA, you can install it directly to your phone's home screen and use it just like a native app.

This app is designed to work alongside the separate backend API.

## 🌟 Features

- **PWA Ready**: Installable on iOS and Android devices directly from the browser. Looks and feels like a native app.
- **Easy Recipe Import**: Paste a social media video link and quickly send it to the backend for AI parsing and import.
- **Modern UI**: Clean, Dark Mode-ready interface built with Next.js, React, and Tailwind CSS.
- **Standalone Frontend**: Can be hosted anywhere independently of the backend.

## 🚀 Getting Started

To run this application, you will need the backend API running.

### Prerequisites

- Node.js (v18+)
- `pnpm` package manager
- A running instance of the [social-to-mealie backend](https://github.com/GerardPolloRebozado/social-to-mealie).

### Local Development

1. **Clone the repository:**
   ```bash
   git clone https://github.com/jg3615207/social-to-mealie_app.git
   cd social-to-mealie_app
   ```

2. **Install dependencies:**
   ```bash
   pnpm install
   ```

3. **Configure the Environment:**
   You will need to point the frontend to your backend API. In your deployment or local `.env` file, ensure the API routes correctly point to your social-to-mealie instance.
   *(Note: The app is currently configured to use `/api/import` which you can proxy to your backend).*

4. **Run the development server:**
   ```bash
   pnpm dev
   ```

   Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

## 📦 Docker Deployment

This project includes a `Dockerfile` for easy deployment. The image is automatically built and pushed to Docker Hub upon updates to the `main` branch.

You can pull the latest image using:

```bash
docker pull jg3615207/social-to-mealie_app:latest
```

### Running with Docker

Run the container using docker run:

```bash
docker run -d \
  -p 3000:3000 \
  --name social-to-mealie-pwa \
  jg3615207/social-to-mealie_app:latest
```

Then, access the app at `http://your-server-ip:3000`.

## 📱 How to Use (Walkthrough)

1. **Install the App**: 
   - Open the web app URL in your mobile browser (Safari on iOS, Chrome on Android).
   - In Safari: Tap the Share button and select "Add to Home Screen".
   - In Chrome: Tap the menu and select "Install app".
2. **Find a Recipe**: 
   - Find a cooking video you like on Instagram, TikTok, YouTube Shorts, etc.
   - Copy the link to the video.
3. **Import to Mealie**:
   - Open the `Social to Mealie` PWA on your phone.
   - Paste the copied link into the input field.
   - Tap **"Import Recipe"**.
   - The app will send the request to the backend, which downloads the video, transcribes the audio, generates a recipe using AI, and saves it to your Mealie instance.

## 🛠️ Built With

- [Next.js](https://nextjs.org/)
- [React](https://reactjs.org/)
- [Tailwind CSS](https://tailwindcss.com/)
- [Lucide Icons](https://lucide.dev/)

## 📄 License
This project is an independent frontend addition based on the functionality of the original `social-to-mealie` service.
