# 🎧 DJS05 – Show Detail Page with Routing and Navigation  
### **By Kyle Patterson**

Welcome to the Show Detail Page portion of my Podcast Browser App.  
This project demonstrates my ability to work with **dynamic routing**, **asynchronous data fetching**, **state preservation**, and **multi-level UI navigation** in React.

Users can browse podcasts on the homepage, click any show, and navigate to a fully dynamic detail page that loads show-specific information — including seasons and episodes — directly from the API.

---

# 🌟 Project Overview

The goal of this project was to build a **dynamic, data-driven show detail page** that works seamlessly with the existing homepage. Each show has its own route, loads its data using the ID in the URL, and allows users to browse episodes using custom season navigation.

This project puts strong emphasis on:

- Clean component structure  
- Handling loading/error states smoothly  
- Preserving user search/filters  
- Creating intuitive season and episode browsing  
- Maintaining reliable, well-organised code  

---

# ✅ How Core Objectives Were Achieved

Below is a breakdown of **each objective** and **how my implementation fulfills it**.

---

## 1️⃣ Dynamic Routing for Show Details

Dynamic routing is implemented using **React Router**.

<Route path="/show/:id" element={<ShowDetail />}

Every show card on the homepage links to a URL like:

/show/<ID>

The ShowDetail component extracts the ID using:

<const { id } = useParams();>

This ensures every show has its own unique route and can be visited directly.

### 2️⃣ Fetching Show Data Using the URL Parameter
Once the ID is extracted, the app fetches detailed show data from:

https://podcast-api.netlify.app/id/<ID>
A dedicated fetchShowById() utility handles:

Asynchronous fetching

Error handling

Normalizing the API response

Structuring the seasons and episodes

The data is stored in component state and rendered once loading completes.

### 3️⃣ Graceful Loading & Error Handling
My implementation includes:

A loading spinner while data is being fetched

A user-friendly error message when something goes wrong

A fallback “Show Not Found” message when the API returns no results

All fetch states are fully managed to ensure a smooth experience.

### 4️⃣ Displaying Complete Show Details
The Show Detail page displays:

🎨 Large high-quality show image

🏷️ Title

📝 Show description

🧩 Genre tags (using a local ID → Name map)

🗓️ Last updated date (formatted using formatDate())

All data is presented clearly and responsively.

### 5️⃣ State Preservation When Navigating Back
The app preserves the user’s homepage state, including:

Search input

Genre filters

Sort selections

Pagination

This is achieved using a combination of:

URLSearchParams

State stored at parent component levels

This gives users a smooth “return-to-where-you-left-off” experience.

### 6️⃣ Season Navigation System
A dedicated <SeasonNavigator /> component allows users to:

Expand or collapse seasons

Switch between seasons without scrolling long lists

View all episodes inside each season

Each season shows:

Season image

Season title

Episode count

Each episode displays:

Episode title

Episode number

Episode image

A shortened version of its description

The UI is intuitive, clean, and flexible across screen sizes.

### 7️⃣ High-Quality, Modular, Well-Documented Code
My project uses a clean component architecture with files such as:

ShowDetail.jsx

ShowHeader.jsx

SeasonNavigator.jsx

EpisodeList.jsx

fetchShow.js

formatDate.js

genreMap.js

Every major file includes JSDoc comments, for example:

/**
 * Fetches full show details by ID.
 * @param {string} id - The show ID.
 * @returns {Promise<Object>} The show data.
 */
This ensures the project is maintainable, scalable, and clear.

### 8️⃣ Fully Responsive Design
The layout adapts seamlessly to:

Desktop

Tablet

Mobile devices

Responsive considerations include:

Images scale fluidly

Episode lists wrap cleanly

Season navigation works perfectly on touch devices

Long text stays readable

### 📁 Project File Structure

│ App.jsx
│ data.js
│ index.css
│ main.jsx
│
├───api
│       fetchData.js
│
├───components
│   │   index.js
│   │
│   ├───Filters
│   │       GenreFilter.jsx
│   │       GenreFilter.module.css
│   │       index.js
│   │       SearchBar.jsx
│   │       SearchBar.module.css
│   │       SortSelect.jsx
│   │       SortSelect.module.css
│   │
│   ├───Podcasts
│   │       index.js
│   │       PodcastCard.jsx
│   │       PodcastCard.module.css
│   │       PodcastDetail.jsx
│   │       PodcastDetail.module.css
│   │       PodcastGrid.jsx
│   │       PodcastGrid.module.css
│   │
│   └───UI
│           Error.jsx
│           Error.module.css
│           GenreTags.jsx
│           GenreTags.module.css
│           Header.jsx
│           Header.module.css
│           index.js
│           Loading.jsx
│           Loading.module.css
│           Pagination.jsx
│           Pagination.module.css
│
├───context
│       PodcastContext.jsx
│
├───pages
│       Home.jsx
│       Home.module.css
│       ShowDetail.jsx
│
└───utils
        formatDate.js

The project follows a clean and consistent structure.

### 🚀 Running the Project Locally
- Clone the repository:

git clone <your-repo-url>
cd djs05-podcast-app

- Install dependencies:
npm install

- Start development server:
npm run dev

The application will be available at:
http://localhost:5173/

### ✨ Main Features Summary
Dynamic show pages

Episode and season browsing

Full API integration

State-preserving homepage

Responsive UI

Clean React component structure

Genre mapping included

Friendly loading and error handling

### ⚠️ Known Limitations
The API can sometimes be slow (3–5 seconds).

Some podcasts include missing or minimal descriptions.

Genre IDs must be manually mapped (as required by the project).

### 🎉 Final Notes
This project highlights my ability to develop:

Data-driven, dynamic interfaces

Smooth multi-page navigation

Well-structured, modular React applications

User-friendly UI/UX with preserved state