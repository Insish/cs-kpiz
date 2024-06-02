#include <iostream>
#include <stack>
#include <string>

using namespace std;

class Note {
private:
    string name;
    int octave;
    int duration;

public:
    Note(string _name, int _octave, int _duration) : name(_name), octave(_octave), duration(_duration) {}

    void print() {
        cout << "Note: " << name << ", Octave: " << octave << ", Duration: " << duration << " ms\n";
    }
};

int main() {
    stack<Note> notes;

    notes.push(Note("Do", 4, 500));
    notes.push(Note("Re", 4, 300));
    notes.push(Note("Mi", 4, 400));

    int choice;
    string name;
    int octave;
    int duration;

    do {
        cout << "\nMenu:\n";
        cout << "1. Add a note\n";
        cout << "2. Remove a note\n";
        cout << "3. Display all notes\n";
        cout << "4. Exit\n";
        cout << "Choose an option: ";
        cin >> choice;

        switch (choice) {
        case 1:
            cout << "Enter the name of the note: ";
            cin >> name;
            cout << "Enter the octave: ";
            cin >> octave;
            cout << "Enter the duration (in milliseconds): ";
            cin >> duration;
            notes.push(Note(name, octave, duration));
            cout << "Note added to the stack.\n";
            break;
        case 2:
            if (!notes.empty()) {
                notes.pop();
                cout << "Note removed from the stack.\n";
            }
            else {
                cout << "The stack is empty, no notes to remove.\n";
            }
            break;
        case 3:
            cout << "Notes in the stack:\n";
            {
                stack<Note> tempStack;
                while (!notes.empty()) {
                    Note currentNote = notes.top();
                    currentNote.print();
                    tempStack.push(currentNote);
                    notes.pop();
                }

                while (!tempStack.empty()) {
                    notes.push(tempStack.top());
                    tempStack.pop();
                }
            }
            break;
        case 4:
            cout << "Exiting the program.\n";
            break;
        default:
            cout << "Invalid choice. Please try again.\n";
        }
    } while (choice != 4);
}

