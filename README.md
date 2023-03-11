
# Six Degrees of Kevin Beacon

Finds the shortest Path between people who have worked together on movies
This code loads data about people, movies, and stars from CSV files into memory and then implements a search algorithm that finds the shortest path between two given people using a breadth-first search algorithm.

**Prerequisites** <br/>
Python 3.x
pandas
zipfile
Getting Started
Clone this repository using git.

Download the IMDb dataset and extract the files.

Move the extracted CSV files to the project's root directory.

Run the shortest_path.py file and enter the names of the two people you want to find the shortest path between.

**Implementation Details** <br/>
The code reads in three CSV files: people.csv, movies.csv, and stars.csv. These files contain information about people, movies, and which people starred in which movies.

The code defines a function load_data that reads in the data from the CSV files and stores it in three dictionaries: names, people, and movies. names maps each name to a set of corresponding person ids, people maps each person id to a dictionary of name, birth, and movies (a set of movie ids), and movies maps each movie id to a dictionary of title, year, and stars (a set of person ids).

The code then defines a function shortest_path that takes two arguments: the source person and the target person. The function returns the shortest list of (movie_id, person_id) pairs that connect the source to the target using a breadth-first search algorithm. If no possible path exists between the two people, the function returns None.

The algorithm works by creating a start node with the source person id and then adding it to the frontier. The algorithm continues by visiting each node in the frontier, exploring its neighbors, and adding them to the frontier if they have not been visited before. If the target person is found, the algorithm stops and returns the shortest path.

The function neighbors_for_person is defined to find all the neighbors of a given person. It returns a set of (movie_id, person_id) pairs for people who starred with the given person.
