# Python_Day_24
#Create the Directory Structure:
personal_diary/
├── diary.py
└── data/
    └── diary_entries.txt



    #Project Framework: Personal Diary Application
#Create diary.py for Main Program Logic:
import os

DIARY_FILE = 'data/diary_entries.txt'

def add_entry():
    date = input("Enter the date (YYYY-MM-DD): ")
    entry = input("Write your diary entry: ")
    with open(DIARY_FILE, 'a') as file:
        file.write(f"{date}\n{entry}\n\n")
    print("Diary entry added successfully.")

def view_entries():
    if os.path.exists(DIARY_FILE):
        with open(DIARY_FILE, 'r') as file:
            entries = file.read()
        if entries:
            print("\nYour Diary Entries:\n")
            print(entries)
        else:
            print("No entries found.")
    else:
        print("No diary file found.")

def delete_entries():
    if os.path.exists(DIARY_FILE):
        os.remove(DIARY_FILE)
        print("All diary entries deleted.")
    else:
        print("No diary file found.")

def main():
    while True:
        print("\nPersonal Diary Application")
        print("1. Add Entry")
        print("2. View Entries")
        print("3. Delete Entries")
        print("4. Exit")

        choice = input("Enter your choice: ")
        if choice == "1":
            add_entry()
        elif choice == "2":
            view_entries()
        elif choice == "3":
            delete_entries()
        elif choice == "4":
            print("Goodbye!")
            break
        else:
            print("Invalid choice, please try again.")

if __name__ == "__main__":
    main()
