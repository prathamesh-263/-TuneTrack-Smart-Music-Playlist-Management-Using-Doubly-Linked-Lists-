#include <iostream>
#include <string>
#include <limits>
using namespace std;

class Node {
public:
    string song;
    string artist;
    Node* prev;
    Node* next;

    Node(string s, string a) {
        song = s;
        artist = a;
        prev = NULL;
        next = NULL;
    }
};

class Playlist {
private:
    Node* head;
    Node* current;

public:
    Playlist() {
        head = NULL;
        current = NULL;
    }

    void addSong(string s, string a) {
        Node* p = new Node(s, a);

        if (head == NULL) {
            head = p;
            current = p;
        }
        else {
            Node* q = head;

            while (q->next != NULL) {
                q = q->next;
            }

            q->next = p;
            p->prev = q;
        }

        cout << "Song added successfully!\n";
    }

    void deleteSong(string s) {
        Node* q = head;
        Node* p;

        while (q != NULL && q->song != s) {
            q = q->next;
        }

        if (q == NULL) {
            cout << "Song not found!\n";
            return;
        }

        p = q;

        if (p->prev != NULL)
            p->prev->next = p->next;
        else
            head = p->next;

        if (p->next != NULL)
            p->next->prev = p->prev;

        if (current == p) {
            if (p->next != NULL)
                current = p->next;
            else
                current = p->prev;
        }

        delete p;

        cout << "Song deleted successfully!\n";
    }

    void displayPlaylist() {
        Node* q = head;

        if (q == NULL) {
            cout << "Playlist is empty!\n";
            return;
        }

        cout << "\nMusic Playlist:\n";

        while (q != NULL) {
            cout << q->song << " - " << q->artist << endl;
            q = q->next;
        }
    }

    void displayReverse() {
        Node* q = head;

        if (q == NULL) {
            cout << "Playlist is empty!\n";
            return;
        }

        while (q->next != NULL) {
            q = q->next;
        }

        cout << "\nReverse Playlist:\n";

        while (q != NULL) {
            cout << q->song << " - " << q->artist << endl;
            q = q->prev;
        }
    }

    void playCurrent() {
        if (current == NULL) {
            cout << "Playlist is empty!\n";
        }
        else {
            cout << "Now Playing: "
                 << current->song << " - "
                 << current->artist << endl;
        }
    }

    void playNext() {
        if (current == NULL) {
            cout << "Playlist is empty!\n";
        }
        else if (current->next == NULL) {
            cout << "No next song available!\n";
        }
        else {
            current = current->next;
            playCurrent();
        }
    }

    void playPrevious() {
        if (current == NULL) {
            cout << "Playlist is empty!\n";
        }
        else if (current->prev == NULL) {
            cout << "No previous song available!\n";
        }
        else {
            current = current->prev;
            playCurrent();
        }
    }

    void playAll() {
        Node* q = head;

        if (q == NULL) {
            cout << "Playlist is empty!\n";
            return;
        }

        while (q != NULL) {
            current = q;
            playCurrent();
            q = q->next;
        }
    }

    void repeatAll() {
        int n;

        if (head == NULL) {
            cout << "Playlist is empty!\n";
            return;
        }

        cout << "Enter number of repetitions: ";
        cin >> n;

        for (int i = 1; i <= n; i++) {
            cout << "\nRepetition " << i << endl;
            current = head;
            playAll();
        }
    }

    void showCurrent() {
        playCurrent();
    }

    ~Playlist() {
        Node* q = head;

        while (q != NULL) {
            Node* p = q;
            q = q->next;
            delete p;
        }
    }
};

int main() {
    Playlist music;
    int choice;
    string song, artist;

    do {
        cout << "\n===== MUSIC PLAYLIST MANAGER =====\n";
        cout << "1. Add Song\n";
        cout << "2. Delete Song\n";
        cout << "3. Display Playlist\n";
        cout << "4. Display Playlist in Reverse\n";
        cout << "5. Play Current Song\n";
        cout << "6. Play Next Song\n";
        cout << "7. Play Previous Song\n";
        cout << "8. Play Complete Playlist\n";
        cout << "9. Repeat All\n";
        cout << "10. Show Current Song\n";
        cout << "11. Exit\n";

        cout << "\nEnter your choice: ";
        cin >> choice;
        cin.ignore(numeric_limits<streamsize>::max(), '\n');

        switch (choice) {
        case 1:
            cout << "Enter song name: ";
            getline(cin, song);

            cout << "Enter artist name: ";
            getline(cin, artist);

            music.addSong(song, artist);
            break;

        case 2:
            cout << "Enter song name to delete: ";
            getline(cin, song);

            music.deleteSong(song);
            break;

        case 3:
            music.displayPlaylist();
            break;

        case 4:
            music.displayReverse();
            break;

        case 5:
            music.playCurrent();
            break;

        case 6:
            music.playNext();
            break;

        case 7:
            music.playPrevious();
            break;

        case 8:
            music.playAll();
            break;

        case 9:
            music.repeatAll();
            break;

        case 10:
            music.showCurrent();
            break;

        case 11:
            cout << "Exiting Music Playlist Manager...\n";
            break;

        default:
            cout << "Invalid choice! Try again.\n";
        }

    } while (choice != 11);

    return 0;
}
