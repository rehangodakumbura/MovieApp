# Android Movie Database Application

A comprehensive movie database Android application built with **Kotlin** and **Jetpack Compose** that integrates with the OMDb API for movie data retrieval and uses Room database for local storage and search functionality.

## Overview

This application serves as a movie knowledge testing and acquisition platform, allowing users to search for movies, manage a local database, and perform various movie-related queries. It demonstrates modern Android development practices with API integration, local database management, and responsive UI design.

## Features

### Core Functionality
- **Movie Database Management**: Add and manage movies in local SQLite database using Room
- **Online Movie Search**: Search for movies using OMDb API integration
- **Actor-Based Search**: Find movies by actor names with partial matching
- **Title-Based Web Search**: Search movies by title directly from OMDb API
- **Data Persistence**: Local storage with Room database for offline access

### Technical Features
- **RESTful API Integration**: OMDb API for movie data retrieval
- **JSON Parsing**: Native Android JSON parsing without third-party libraries
- **Room Database**: Local SQLite database with proper table relationships
- **State Management**: Jetpack Compose state handling with configuration changes
- **Orientation Support**: Full portrait/landscape compatibility
- **Network Operations**: HTTP requests using standard Android APIs

## Technology Stack

- **Language**: Kotlin
- **UI Framework**: Jetpack Compose
- **Database**: Room (SQLite)
- **API Integration**: OMDb API (http://www.omdbapi.com/)
- **HTTP Client**: Standard Android HTTP libraries
- **JSON Parsing**: Native Android JSON parsing
- **Architecture**: MVVM with Repository pattern

## Prerequisites

- Android Studio Arctic Fox or later
- Android SDK with minimum API level support
- OMDb API key (free registration required)
- Internet connection for API calls
- Kotlin plugin enabled

## Installation & Setup

### 1. Clone the Repository
```bash
git clone https://github.com/rehangodakumbura/MovieApp.git
cd MovieApp
```

### 2. OMDb API Setup
1. Visit [OMDb API](http://www.omdbapi.com/)
2. Register for a free account to get your API key
3. Add your API key to the project:
   ```kotlin
   // In your Constants or Config file
   const val OMDB_API_KEY = "YOUR_API_KEY_HERE"
   ```

### 3. Build and Run
1. Open project in Android Studio
2. Sync Gradle files
3. Connect Android device or start emulator
4. Run the application

## Application Structure

### Main Navigation
The app starts with three primary options:
- **Add Movies to DB**: Populate local database with predefined movies
- **Search for Movies**: Online movie search and database storage
- **Search for Actors**: Local database search by actor names

### Database Schema

The Room database contains tables for storing:
- **Movies**: Title, year, rating, release date, runtime, genre
- **Directors**: Director information
- **Actors**: Actor details with movie relationships
- **Additional metadata**: Plot, ratings, awards, etc.

## Core Features

### 1. Database Population
- Automatically creates and populates SQLite database
- Stores comprehensive movie information from predefined dataset
- Uses Room library for database operations
- Handles all movie fields including:
  - Title, Year, Rated, Released, Runtime
  - Genre, Director, Writer, Actors
  - Plot, Language, Country, Awards
  - Ratings, IMDb information

### 2. Online Movie Search
**Search Interface:**
- Text input for movie title
- "Retrieve Movie" button for API calls
- "Save movie to Database" button for local storage

**Data Display Format:**
```
Title: "The Shawshank Redemption"
Year: 1994
Rated: R
Released: 14 Oct 1994
Runtime: 142 min
Genre: Drama
Director: Frank Darabont
Writer: Stephen King, Frank Darabont
Actors: Tim Robbins, Morgan Freeman, Bob Gunton
Plot: "Two imprisoned men bond over a number of years, finding solace and eventual redemption through acts of common decency."
```

### 3. Actor Search
- **Case-insensitive search**: Search works regardless of case
- **Partial matching**: Find actors with substring matches
- **Comprehensive results**: Displays all matching movies
- **Example**: Searching "rUISE" finds movies with "Tom Cruise" or "Penelope Cruise"

### 4. Title-Based Web Search
- Direct OMDb API integration for title searches
- Case-insensitive partial matching
- Displays multiple results (minimum 10 movies or first page)
- Real-time web service queries (not local database)

## API Integration

### OMDb API Usage
```kotlin
// Example API call structure
val apiUrl = "https://www.omdbapi.com/?t=${movieTitle}&apikey=${API_KEY}"
```

**Response Handling:**
- JSON parsing using native Android libraries
- Error handling for network issues
- Proper data mapping to local models

**Sample API Response:**
```json
{
  "Title": "Matrix",
  "Year": "1993",
  "Rated": "N/A",
  "Released": "01 Mar 1993",
  "Runtime": "60 min",
  "Genre": "Action, Drama, Fantasy",
  "Director": "N/A",
  "Writer": "Grenville Case",
  "Actors": "Nick Mancuso, Phillip Jarrett, Carrie-Anne Moss",
  "Plot": "Steven Matrix is one of the underworld's foremost hitmen...",
  "imdbRating": "8.0",
  "Response": "True"
}
```

## Project Structure

```
app/
├── src/main/java/com/yourpackage/moviedatabase/
│   ├── MainActivity.kt                 # Main activity and navigation
│   ├── ui/
│   │   ├── screens/
│   │   │   ├── MainMenuScreen.kt      # Home screen with navigation buttons
│   │   │   ├── MovieSearchScreen.kt   # Online movie search interface
│   │   │   ├── ActorSearchScreen.kt   # Actor-based search screen
│   │   │   └── TitleSearchScreen.kt   # Title-based web search
│   │   ├── components/                # Reusable UI components
│   │   └── theme/                     # App theming
│   ├── data/
│   │   ├── database/
│   │   │   ├── MovieDatabase.kt       # Room database configuration
│   │   │   ├── entities/              # Database entities
│   │   │   └── dao/                   # Data Access Objects
│   │   ├── repository/
│   │   │   └── MovieRepository.kt     # Data layer abstraction
│   │   └── api/
│   │       └── OMDbService.kt         # API service implementation
│   ├── domain/
│   │   └── models/                    # Domain models
│   └── viewmodels/                    # ViewModels for screens
└── src/main/res/
    └── values/                        # String resources and themes
```

## Key Classes

### Database Components
- **MovieEntity**: Room entity for movie data
- **MovieDao**: Database access operations
- **MovieDatabase**: Room database configuration
- **DatabaseInitializer**: Populates database with initial data

### API Components
- **OMDbService**: HTTP client for API calls
- **ApiResponse**: Data classes for API responses
- **NetworkManager**: Network operations and error handling

### UI Components
- **MovieSearchViewModel**: Manages search state and API calls
- **ActorSearchViewModel**: Handles local database queries
- **DatabaseViewModel**: Manages database operations

## Development Features

### State Management
- **Configuration Changes**: Proper handling of screen rotations
- **Data Persistence**: Maintains search results and input during orientation changes
- **Loading States**: UI feedback during API calls and database operations

### Error Handling
- **Network Errors**: Graceful handling of connectivity issues
- **API Errors**: User-friendly error messages for failed requests
- **Database Errors**: Exception handling for database operations
- **Input Validation**: Prevents crashes from invalid user input

### UI/UX Design
- **Material Design**: Modern Android design principles
- **Responsive Layout**: Adapts to different screen sizes and orientations
- **Loading Indicators**: Visual feedback during operations
- **Search Results**: Clear, readable movie information display

## Testing

### Manual Testing Checklist
- [ ] Database population on first launch
- [ ] Online movie search with valid titles
- [ ] Movie data saving to local database
- [ ] Actor search with partial matches
- [ ] Case-insensitive search functionality
- [ ] Device rotation handling
- [ ] Network error scenarios
- [ ] Invalid input handling

### Test Scenarios
1. **Database Operations**: Create, read, update operations
2. **API Integration**: Valid and invalid API calls
3. **Search Functionality**: Various search patterns and edge cases
4. **Orientation Changes**: State preservation during rotations
5. **Network Conditions**: Offline/online behavior

## Known Limitations

- Requires active internet connection for OMDb API calls
- API rate limits apply based on OMDb plan
- Local database storage limited by device capacity
- Search results dependent on OMDb data quality

## Future Enhancements

- **Offline Mode**: Enhanced offline functionality
- **Advanced Search**: Multiple search criteria combinations
- **Movie Ratings**: User rating and review system
- **Favorites**: Personal movie collection management
- **Image Display**: Movie poster integration
- **Export/Import**: Database backup and restore functionality

## API Documentation

### OMDb API Endpoints Used
- **Search by Title**: `/?t={title}&apikey={key}`
- **Search by Title (Multiple)**: `/?s={title}&apikey={key}`

### Required Parameters
- `apikey`: Your personal API key from OMDb
- `t`: Movie title for single result
- `s`: Search term for multiple results

## Troubleshooting

### Common Issues

1. **API Key Errors**
   - Verify API key is correctly configured
   - Check OMDb account status and usage limits

2. **Database Issues**
   - Clear app data if database corruption occurs
   - Check Room database configuration

3. **Network Problems**
   - Verify internet connection
   - Check firewall settings for API access

4. **Search Not Working**
   - Ensure proper input formatting
   - Check case sensitivity requirements

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/new-feature`)
3. Commit your changes (`git commit -am 'Add new feature'`)
4. Push to the branch (`git push origin feature/new-feature`)
5. Create a Pull Request

### Development Guidelines
- Follow Kotlin coding conventions
- Use Jetpack Compose best practices
- Maintain Room database migrations
- Test API integration thoroughly
- Document any new API usage

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Author

**[Rehan Godakumbura]**
- GitHub: [@rehangodakumbura](https://github.com/rehangodakumbura)
- Email: your.email@example.com

## External Resources

- [OMDb API Documentation](http://www.omdbapi.com/)
- [Android Developer Guides](https://developer.android.com/guide)
- [Jetpack Compose Documentation](https://developer.android.com/jetpack/compose)
- [Room Database Guide](https://developer.android.com/training/data-storage/room)

---
