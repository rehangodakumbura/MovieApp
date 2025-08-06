# 🎥 Movie Knowledge & Search App – Android (Kotlin + Jetpack Compose)

An interactive **Android application** built with **Kotlin** and **Jetpack Compose** for exploring and managing movie data.  
The app integrates the **OMDb API** for fetching movie information and uses the **Room database** for local storage.

---

## 📖 Overview
This app helps users to:
- Retrieve detailed movie information from the **OMDb API**.
- Save movie details to a local database.
- Search movies by actor name (partial and case-insensitive match).
- Search movies by title substring directly from the API.
- Seamlessly handle device orientation changes without losing state.

---

## ✨ Features
- **Add Movies to DB** – Preload movies into a local Room database.  
- **Search Movies by Title** – Fetch live data from OMDb API.  
- **Save Movies to DB** – Store retrieved movies in the local database.  
- **Search by Actor** – Find all local database movies matching actor names.  
- **Dynamic Title Search** – Retrieve multiple matching movies from API based on a substring.  
- **Orientation Handling** – Maintains state when device rotates.  
- **Modern UI** – Built with Jetpack Compose for a responsive, clean interface.

---

## 🛠 Tech Stack
- **Language:** Kotlin  
- **UI Framework:** Jetpack Compose  
- **Local Database:** Room (SQLite)  
- **API Integration:** OMDb API  
- **IDE:** Android Studio

---

## 🚀 How to Run
1. **Clone the repository:**
   ```bash
   git clone https://github.com/rehangodakumbura/MovieApp.git
