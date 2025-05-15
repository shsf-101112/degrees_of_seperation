Degrees of Separation

This project finds the shortest connection (in terms of shared movies) between two actors/actresses using breadth-first search (BFS). It's inspired by the concept of "Six Degrees of Kevin Bacon", where any actor can be linked to Kevin Bacon through six or fewer film collaborations.

Dataset Structure
The project expects a folder (large/ or small/) containing 3 CSV files:
people.csv: Information about each person (id, name, birth year)
movies.csv: Information about each movie (id, title, year)
stars.csv: Links people to the movies they've starred in (movie_id, person_id)

How It Works
Loads and parses CSV files into memory.
Builds mappings between people and the movies they've acted in.
Uses Breadth-First Search (BFS) to find the shortest path between two actors, where:
Nodes represent actors.
Edges represent shared movies.

Algorithm:
Frontier: A queue (FIFO) to ensure BFS behavior.
Explored Set: Keeps track of visited nodes to avoid cycles.
Path: Returns a list of (movie_id, person_id) pairs showing the chain of connections.

Usage:
bash
Copy
Edit
python degrees.py [directory]
Replace [directory] with the path to the dataset folder (e.g., small or large).

If no directory is given, it defaults to large.

Example
makefile
Copy
Edit
$ python degrees.py small
Name: Emma Watson
Name: Daniel Radcliffe
2 degrees of separation.
1: Emma Watson and Rupert Grint starred in Harry Potter and the Prisoner of Azkaban
2: Rupert Grint and Daniel Radcliffe starred in Harry Potter and the Prisoner of Azkaban

Requirements:
Python 3.x
Standard libraries (csv, sys)

Notes:
If a name is ambiguous (e.g., multiple actors with the same name), the script will prompt you to choose the correct one using their ID.

Designed for educational purposes and performance is limited to dataset size.

