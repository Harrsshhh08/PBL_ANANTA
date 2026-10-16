# PeerLearn File-Based

Beginner-friendly console C++ project using fixed arrays, linked lists, a simple skill tree, a simple student graph, matching, and text files.

## Simple input

`main.cpp` uses direct `cin` and `cout`. It does not use `numeric_limits`, exception handling, EOF handling, or advanced input-validation loops. Enter the requested number or text at each menu.

## Build

```powershell
g++ -std=c++11 main.cpp Student.cpp FileStorage.cpp RequestQueue.cpp Rating.cpp Admin.cpp SkillTree.cpp Graph.cpp Matching.cpp -o PeerLearnFileBased.exe
.\PeerLearnFileBased.exe
```
