# Movie App

This is a simple movie application built with React and Vite, utilizing Appwrite for backend services and Firebase Hosting for deployment. The app allows users to search for movies and view trending movie searches.

## Features

*   Search for movies
*   View trending movie searches
*   Displays movie posters, titles, and release dates
*   Uses Appwrite for tracking search counts

## Technologies Used

*   **Frontend:** React, Vite
*   **Backend:** Appwrite (for tracking search counts)
*   **Deployment:** Firebase Hosting

## Setup and Installation

1.  **Clone the repository:**

    ```bash
    git clone <repository-url>
    cd Movie-App
    ```

2.  **Install dependencies:**

    ```bash
    npm install
    ```

3.  **Set up Appwrite:**

    *   Create a new Appwrite project.
    *   Create a database and a collection named "metrics".
    *   Add the following attributes to the "metrics" collection:
        *   `searchTerm` (String, required)
        *   `Count` (Integer, required, default value: 1)
        *   `poster_url` (Url, required)
        *   `movie_id` (Integer, required)
    *   Copy your Appwrite Project ID, Database ID, and Collection ID.

4.  **Create environment variables:**

    Create a `.env` file in the `Movie-App` directory with the following variables:

    ```env
    VITE_APPWRITE_PROJECT_ID=YOUR_APPWRITE_PROJECT_ID
    VITE_APPWRITE_DATABASE_ID=YOUR_APPWRITE_DATABASE_ID
    VITE_APPWRITE_COLLECTION_ID=YOUR_APPWRITE_COLLECTION_ID
    ```

    Replace `YOUR_APPWRITE_PROJECT_ID`, `YOUR_APPWRITE_DATABASE_ID`, and `YOUR_APPWRITE_COLLECTION_ID` with your actual Appwrite credentials.

5.  **Run the application locally:**

    ```bash
    npm run dev
    ```

    The application will be available at `http://localhost:5173/`.

## Deployment to Firebase Hosting

1.  **Install Firebase CLI:**

    ```bash
    npm install -g firebase-tools
    ```

2.  **Log in to Firebase:**

    ```bash
    firebase login
    ```

3.  **Initialize Firebase in your project:**

    In the `Movie-App` directory, run `firebase init` and follow the prompts:
    *   Select "Hosting".
    *   Choose your Firebase project.
    *   Set "public directory" to `dist`.
    *   Configure as a single-page application (Yes).

4.  **Build the application:**

    ```bash
    npm run build
    ```

5.  **Deploy to Firebase:**

    ```bash
    firebase deploy --only hosting
    ```

    The application will be deployed to your Firebase Hosting URL.
