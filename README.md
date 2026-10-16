# PeerLearn — File-Based Version

This is a separate, simpler PeerLearn project. It does **not** use a graph, tree, matching system, hashing, or STL containers.

## Completion status

Approximately **85% of this smaller file-based version** is complete.

Completed features:

- Student registration and login
- Admin login
- Student profile display
- Sending learning requests to another student ID
- Accepting or rejecting received requests
- Rating an accepted peer
- Admin view of students, requests, and ratings
- Admin ban, unban, and student removal
- Saving and loading records after exit

Still to build:

- Contact details and contact sharing after acceptance
- Better duplicate-request validation
- Better validation for damaged text files
- Password protection; passwords are currently stored as plain text for this basic college project
- Successful compile/run testing after the MinGW error is fixed

## Files and their basic purpose

- `main.cpp` — Contains the Student and Admin console menus. It calls the other modules and saves data after every important action.
- `Student.h` / `Student.cpp` — Defines Student and StudentManager. Uses a fixed array for up to 100 students. Handles registration, login, profile data, ratings, bans, and removal.
- `FileStorage.h` / `FileStorage.cpp` — Saves and loads student records from `students.txt` using `fstream`.
- `RequestQueue.h` / `RequestQueue.cpp` — Manual linked request queue. Stores requests in order and saves/loads them from `requests.txt`.
- `Rating.h` / `Rating.cpp` — Manual linked list of rating records. Allows ratings only after an accepted request and saves/loads them from `ratings.txt`.
- `Admin.h` / `Admin.cpp` — Checks the simple starter Admin credentials.
- `README.md` — Explains the project, progress, files, data structures, and build command.

## Data structures and C++ concepts used

- **Fixed array** — `Student students[100]` stores student records.
- **Singly linked list** — Each learning request and rating record is a dynamically allocated node connected by a `next` pointer.
- **Queue behaviour** — New learning requests are added at the rear; the front keeps the earliest request.
- **Pointers and dynamic memory** — The request and rating nodes use `new` and are deleted by `clear()` functions.
- **Classes** — Student, StudentManager, RequestQueue, RatingSystem, FileStorage, and Admin separate the work into simple modules.
- **Character arrays and `cstring`** — Names, usernames, passwords, topics, and file-text parsing use `char[]`, `strncpy`, `strcmp`, and `strtok`.
- **File handling** — `fstream`, `ifstream`, and `ofstream` save and retrieve data.
- **Console input/output** — `iostream`; this version uses `using namespace std;` in its `.cpp` files to keep beginner code shorter.

## Saved data files

Run the program from this folder. These files are created beside the source files when data is saved:

- `students.txt` — Student account/profile records
- `requests.txt` — Request ID, sender, receiver, topic, and request status
- `ratings.txt` — Rater ID, rated student ID, and score

At startup, all three files are loaded. At registration, request, response, rating, Admin change, and exit, data is saved again.

## Starter Admin login

Username: `admin`  
Password: `admin123`

## Build

```powershell
g++ -std=c++11 -Wall -Wextra -pedantic main.cpp Student.cpp FileStorage.cpp RequestQueue.cpp Rating.cpp Admin.cpp -o PeerLearnFileBased.exe
.\PeerLearnFileBased.exe
```

## Verification note

The installed MinGW compiler currently fails to start with an `Illegal System DLL Relocation` error. The code has been manually reviewed, but successful compilation has not yet been confirmed.
