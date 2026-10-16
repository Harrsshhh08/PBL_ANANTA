# PeerLearn File-Based Version

This is a separate simple console project. It does not use graph, tree, matching, hashing, or STL containers.

It uses:

- a fixed array of student objects;
- Student and Admin login;
- a manual linked request queue and manual linked rating records;
- `fstream` files: `students.txt`, `requests.txt`, and `ratings.txt`;
- automatic loading of saved records at program start.

Run the program from this folder so `students.txt` is created and read here.

## Build

```powershell
g++ -std=c++11 -Wall -Wextra -pedantic main.cpp Student.cpp FileStorage.cpp RequestQueue.cpp Rating.cpp Admin.cpp -o PeerLearnFileBased.exe
.\PeerLearnFileBased.exe
```

Starter Admin login: `admin` / `admin123`.

The first run starts with no records. Every registration, request, response, rating, or Admin change is saved and loaded automatically on later runs.
