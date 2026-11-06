# Music Playlist Manager
### C++ | Doubly Linked List | Data Structures and Algorithms



## 1. Project Overview

The **Music Playlist Manager** is a menu-driven application developed in C++ that demonstrates the practical implementation of a Doubly Linked List.

The application provides functionalities to manage a music playlist, including adding and deleting songs, displaying songs in forward and reverse order, navigating between songs, and repeating the playlist.

Each node stores the song title, artist name, and pointers to the previous and next nodes.

This project demonstrates the use of dynamic memory allocation, pointers, object-oriented programming, and linked list operations in a real-world application.



## 2. Objectives

- Implement a Doubly Linked List using C++.
- Perform insertion and deletion operations.
- Maintain song navigation using previous and next pointers.
- Display the playlist in forward and reverse order.
- Implement a menu-driven interface.
- Understand dynamic memory allocation and pointer management.

  

## 3. Technologies Used

| Component | Technology |
|---|---|
| Programming Language | C++ |
| Data Structure | Doubly Linked List |
| Development Environment | Visual Studio Code |
| Compiler | GCC / MinGW |
| Version Control | Git |
| Repository Hosting | GitHub |



## 4. System Features

| No. | Feature | Description |
|---|---|---|
| 1 | Add Song | Insert a song with its title and artist. |
| 2 | Delete Song | Remove a song from the playlist. |
| 3 | Display Playlist | Display all songs in forward order. |
| 4 | Reverse Playlist | Display songs in reverse order. |
| 5 | Play Current Song | Display the currently selected song. |
| 6 | Next Song | Navigate to the next song. |
| 7 | Previous Song | Navigate to the previous song. |
| 8 | Play All | Display all songs sequentially. |
| 9 | Repeat All | Repeat the playlist a specified number of times. |
| 10 | Show Current Song | Display the current song information. |



## 5. Data Structure Implementation

### Doubly Linked List

A Doubly Linked List is used to maintain the playlist.

Each node contains:

- `song` – Stores the song title.
- `artist` – Stores the artist name.
- `prev` – Pointer to the previous node.
- `next` – Pointer to the next node.

### Node Representation

```cpp
class Node {
public:
    string song;
    string artist;
    Node* prev;
    Node* next;
};
```

### Playlist Pointers

- `head` – Points to the first song.
- `current` – Points to the currently selected song.
- `p` – Represents a newly created node.
- `q` – Used for traversal.

The `prev` and `next` pointers allow navigation in both directions.



## 6. Algorithm

1. Initialize an empty playlist.
2. Display the main menu.
3. Accept the user's choice.
4. Execute the selected operation.
5. Update the linked list when required.
6. Display the operation result.
7. Repeat the menu until the Exit option is selected.
8. Release allocated memory and terminate the program.



## 7. Project Structure

```text
Music-Playlist-Manager/
│
├── main.cpp
├── output
└── README.md
```



## 8. Installation and Execution

### Prerequisites

- C++ compiler (GCC or MinGW)
- Visual Studio Code or another C++ development environment
- Git

### Clone the Repository

```bash
git clone YOUR_REPOSITORY_URL
```

### Navigate to the Project Directory

```bash
cd Music-Playlist-Manager
```

### Compile the Program

```bash
g++ main.cpp -o playlist
```

### Execute the Program

**Windows:**

```bash
playlist.exe
```

**Linux:**

```bash
./playlist
```



## 9. Sample Output

### Main Menu

```text
===== MUSIC PLAYLIST MANAGER =====

1. Add Song
2. Delete Song
3. Display Playlist
4. Display Playlist in Reverse
5. Play Current Song
6. Play Next Song
7. Play Previous Song
8. Play Complete Playlist
9. Repeat All
10. Show Current Song
11. Exit

Enter your choice:
```

### Playlist Display

```text
Music Playlist:

Believer - Imagine Dragons
Perfect - Ed Sheeran
Shape of You - Ed Sheeran
```

### Current Song

```text
Now Playing: Believer - Imagine Dragons
```



## 10. Complexity Analysis

Let `n` represent the number of songs in the playlist.

| Operation | Time Complexity |
|---|---|
| Add Song | O(n) |
| Delete Song | O(n) |
| Display Playlist | O(n) |
| Display Reverse | O(n) |
| Play Current Song | O(1) |
| Play Next Song | O(1) |
| Play Previous Song | O(1) |
| Play Complete Playlist | O(n) |

**Space Complexity:** O(n), where `n` is the number of songs stored in the playlist.



## 11. Limitations

The application displays song information but does not play actual audio.

Playlist data is not permanently stored.

Song deletion is performed using the song title.

The application uses a console-based interface.



##12. Future Enhancements

Implement actual audio playback.

Add song search functionality.

Introduce shuffle and repeat-one options.

Implement file handling for permanent playlist storage.

Develop a graphical user interface.

Add song duration and playlist statistics.



##13. Conclusion

The Music Playlist Manager successfully demonstrates the implementation of a Doubly Linked List in C++.

The project provides an efficient way to manage and navigate a playlist while demonstrating important concepts such as pointers, dynamic memory allocation, insertion, deletion, traversal, and object-oriented programming.

This implementation establishes a foundation for developing more advanced music management applications.



##14. Author

Prathamesh  Wakchaure
Second Year Engineering Student
Electronics and Computer Engineering



##15. Project Information

Project Category: Data Structures and Algorithms

Language: C++

Data Structure: Doubly Linked List


