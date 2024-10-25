import random

# Define the movies and their initial ratings
movies = {
    "Bollywood": {
        "Dangal": 0,
        "PK": 0,
        "3 Idiots": 0
    },
    "Hollywood": {
        "Inception": 0,
        "Interstellar": 0
    }
}

# Define the 10 people and their ratings
people = [
    {"name": "Person 1", "ratings": {}},
    {"name": "Person 2", "ratings": {}},
    {"name": "Person 3", "ratings": {}},
    {"name": "Person 4", "ratings": {}},
    {"name": "Person 5", "ratings": {}},
    {"name": "Person 6", "ratings": {}},
    {"name": "Person 7", "ratings": {}},
    {"name": "Person 8", "ratings": {}},
    {"name": "Person 9", "ratings": {}},
    {"name": "Person 10", "ratings": {}}
]

# Generate random ratings for each person for each movie
for person in people:
    for movie_category, movies_dict in movies.items():
        for movie_name in movies_dict:
            person["ratings"][movie_name] = random.randint(1, 5)
            movies[movie_category][movie_name] += person["ratings"][movie_name]

# Print the ratings of each person
for person in people:
    print(f"{person['name']}'s ratings:")
    for movie_name, rating in person["ratings"].items():
        print(f"- {movie_name}: {rating}")
    print()

# Find the movie with the highest total rating in each category
best_bollywood_movie = max(movies["Bollywood"], key=movies["Bollywood"].get)
best_hollywood_movie = max(movies["Hollywood"], key=movies["Hollywood"].get)

print(f"Best Bollywood Movie: {best_bollywood_movie}")
print(f"Best Hollywood Movie: {best_hollywood_movie}")
