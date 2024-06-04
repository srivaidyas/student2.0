---
toc: true
comments: false
layout: post
title: Movie and TV Series Search Box
description: This search box uses the TMDb API to extract details about movies and TV series. It provides the name, poster, overview, rating, release date, genre, MPAA rating, and a YouTube trailer link. The CSS formatting, genre mapping, and MPAA rating mapping were done with help from family, friends, and chat.
type: hacks
courses: { compsci: {week: 3} }
image: images/djfhg.avif
---

***Link to the original website:*** [The Movie Database (TMDb)](https://www.themoviedb.org/?language=en-US) 

<br><br>

<html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Movie/TV Series Search</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f0f0f0;
            display: flex;
            justify-content: center;
            margin: 0;
        }
        .container {
            text-align: center;
            background-color: #333;
            padding: 20px;
            border-radius: 20px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
            max-width: 800px;
            width: 100%;
        }
        h1 {
            color: #fff;
        }
        #searchInput {
            padding: 15px;
            font-size: 18px;
            width: 70%;
            max-width: 500px;
            box-sizing: border-box;
            border: none;
            border-radius: 20px;
            text-align: center;
            box-shadow: 0 0 0 2px #fff; /* 2px white outline */
        }
        #searchButton {
            width: 100px; 
            height: 40px; 
            font-size: 16px; 
            border-radius: 20px; 
                    margin-top: 45px;
            padding: 5px 10px;
        }
        #searchButton:hover {
            background-color: #45a049;
        }
        #result {
            margin-top: 20px;
            color: #fff;
            align: left;
        }
        img {
            border-radius: 10px;
            margin-top: 10px;
            max-width: 300px;
            height: auto;
            align: center;
        }
        p {
            margin: 5px 0;
        }
        a {
            color: #4CAF50;
            text-decoration: none;
        }
        a:hover {
            text-decoration: underline;
        }
    </style>

</head>
<body>
    <div class="container">
        <h1>Movie/TV Series Search</h1>
        <input type="text" id="searchInput" placeholder="Enter a movie or TV series name">
        <button id="searchButton">Search</button>
        <div id="result"></div>
    </div>
    <script>
        const searchInput = document.getElementById('searchInput');
        const searchButton = document.getElementById('searchButton');
        const resultDiv = document.getElementById('result');
        const apiKey = '8b9514e6242bb1620afcbec32775e783';

        
        const genreMap = {
               12: "Adventure",
               14: "Fantasy",
               16: "Animation",
               18: "Drama",
               27: "Horror",
               28: "Action",
               35: "Comedy",
               36: "History",
               37: "Western",
               53: "Thriller",
               80: "Crime",
               99: "Documentary",
               9648: "Mystery",
               10402: "Music",
               10749: "Romance",
               10751: "Family",
               10752: "War",
               10759: "Action & Adventure",
               10762: "Kids",
               10763: "News",
               10764: "Reality",
               10765: "Sci-Fi & Fantasy",
               10766: "Soap",
               10767: "Talk",
               10768: "War & Politics",
               878: "Science Fiction",
            
        };


       
        const mpaaRatingMap = {
            "G": "General Audiences",
            "PG": "Parental Guidance Suggested",
            "PG-13": "Parents Strongly Cautioned",
            "TV-14": "For TV Shows above 14",
            "R": "Restricted",
            "NC-17": "Adults Only",
            "NR": "Not Rated",
            "Unrated": "Unrated",
            
        };
        

        
        const languageMap = {
            "en": "English",
            "es": "Spanish",
            "fr": "French",
            "de": "German",
            "el": "Greek",
            "ga": "Irish",
            "hi": "Hindi",
            "ru": "Russian",
            "ta": "Tamil",
            "zh": "Chinese",
            "ko": "Korean",
            "ml": "Malayalam",
            
        };

        // Event listener for the search button
        searchButton.addEventListener('click', () => {
            const searchTerm = searchInput.value.trim();

            if (searchTerm) {

                resultDiv.innerHTML = '';

                
                fetchMovieData(searchTerm);
            }
        });

        
        function fetchMovieData(searchTerm) {
            // Construct the TMDb API URL for searching movies/TV series
            const apiUrl = `https://api.themoviedb.org/3/search/multi?api_key=${apiKey}&query=${encodeURIComponent(searchTerm)}`;

            
            fetch(apiUrl)
                .then((response) => response.json())
                .then((data) => {
                    if (data.results && data.results.length > 0) {
                        // Get the first result (most relevant)
                        const result = data.results[0];


                        const title = result.title || result.name || "Title: N/A";
                        const overview = result.overview || "Overview: N/A";
                        const ratings = result.vote_average
                            ? `Ratings: ${result.vote_average} / 10`
                            : "Ratings: N/A";
                        const releaseDate = result.release_date || result.first_air_date || "Release Date: N/A";
                        const formattedReleaseDate = formatDate(releaseDate);
                        const genre = result.genre_ids
                            ? `Genre: ${getGenre(result.genre_ids)}`
                            : "Genre: N/A";
                        const mpaaRating = result.content_ratings
                            ? `MPAA Rating: ${getMPAARating(result.content_ratings)}`
                            : "MPAA Rating: N/A";
                        const originalLanguage = result.original_language
                            ? `Original Language: ${getOriginalLanguage(result.original_language)}`
                            : "Original Language: N/A";
                        const posterPath = result.poster_path
                            ? `https://image.tmdb.org/t/p/w300${result.poster_path}`
                            : "https://via.placeholder.com/300x450"; // Placeholder image if no poster available;
                        const youtubeTrailerLink = getYouTubeTrailerLink(searchTerm);

                        
                        const updatedSummary = `
                            <h2>${title}</h2>
                            <img src="${posterPath}" alt="${title} Poster" style="max-width: 300px; height: auto;">
                            <p>${overview}</p>
                            <p>${ratings}</p>
                            <p>${formattedReleaseDate}</p>
                            <p>${genre}</p>
                            <p>${mpaaRating}</p>
                            <p>${originalLanguage}</p>
                            <p><a href="${youtubeTrailerLink}" target="_blank">Watch Trailer on YouTube</a></p>
                        `;

                        resultDiv.innerHTML = updatedSummary;
                    } else {
                        resultDiv.innerHTML = '<p>No results found.</p>';
                    }
                })
                .catch((error) => {
                    console.error('Error fetching data from TMDb:', error);
                });
        }

        
        function getGenre(genreIds) {
            const genres = genreIds.map((id) => genreMap[id] || "Unknown");
            return genres.join(', ');
        }

        
        function getMPAARating(contentRatings) {
            if (contentRatings && contentRatings.length > 0) {
                const rating = contentRatings[0].rating;
                return mpaaRatingMap[rating] || rating;
            } else {
                return "N/A";
            }
        }

        
        function getOriginalLanguage(languageCode) {
            return languageMap[languageCode] || "N/A";
        }

        
        function formatDate(dateString) {
            if (!dateString) return "Release Date: N/A";

            const date = new Date(dateString);
            const options = { year: 'numeric', month: '2-digit', day: '2-digit' };
            return "Release Date: " + date.toLocaleDateString('en-US', options);
        }

        
        function getYouTubeTrailerLink(searchTerm) {
            
            const youtubeSearchQuery = encodeURIComponent(`${searchTerm} trailer`);
            return `https://www.youtube.com/results?search_query=${youtubeSearchQuery}`;
        }
    </script>
</body>
</html>


<br><br><br><br>
<br><br>

<hr>

<script src="https://utteranc.es/client.js"
    repo="srivaidyas/student2.0"
    issue-term="pathname"
    label="comments"
    theme="github-light"
    crossorigin="anonymous"
    async>
</script>




<br><hr>
<br>
<h3> Attribution </h3>

<center>
<img src = "https://upload.wikimedia.org/wikipedia/commons/thumb/8/89/Tmdb.new.logo.svg/1024px-Tmdb.new.logo.svg.png?20200406190906" alt= "The TMDb logo" width= "200" height= "165">
</center><br><br>
This product uses the TMDB API but is not endorsed or certified by TMDB
