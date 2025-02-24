# 🖥️ Tech Conference Website (SvelteKit + Bootstrap)

A **modern, fully responsive** Tech Conference website built using **SvelteKit** and **Bootstrap**.

## 🚀 Features
- 📌 **Home Page** – Hero section, featured speakers, and call-to-action.
- 🎤 **Speakers Page** – Grid layout displaying keynote speakers.
- 📅 **Schedule Page** – Well-structured conference timetable.
- 💼 **Sponsors Page** – Showcase of sponsor logos with links.
- ℹ️ **About Page** – Brief introduction to the event.
- ✉️ **Contact Page** – Contact form with validation & social media links.
- 📱 **Fully Responsive** – Works seamlessly on **mobile, tablet, and desktop**.


## 🛠️ Setup & Installation

### 1️⃣ Clone the Repository
```sh
git clone https://github.com/aniketr4j/tech-conference-web.git
cd tech-conference-website
```

### 2️⃣ Install Dependencies
```sh
npm install
```

### 3️⃣ Run the Development Server
```sh
npm run dev
```
This will start the development server. Open `http://localhost:5173/` in your browser.

### 4️⃣ Build for Production
```sh
npm run build
```
This command creates an optimized production build in the `build/` directory.


## 🎯 Create a New SvelteKit Project (If Starting from Scratch)
If you want to create a similar project from the beginning, use the following commands:

```sh
npx sv create tech-conference-website
cd tech-conference-website
npm install
npm run dev
```

## 🎨 Installing Bootstrap
Since **Sveltestrap** is not compatible with the latest SvelteKit version, I have used **Bootstrap** directly.

To install Bootstrap, run:
```sh
npm install bootstrap
```

Then, import Bootstrap CSS in `src/app.html`:
```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/css/bootstrap.min.css">
```
