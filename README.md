# os-copy-file
import os
import shutil
import sys

def copy_file(source, destination):
    try:
        # Use shutil.copy2 to copy the file along with its metadata
        shutil.copy2(source, destination)
        print(f"File {source} copied to {destination} successfully.")
    except FileNotFoundError:
        print(f"The file {source} does not exist.")
    except PermissionError:
        print(f"Permission denied to access {source} or {destination}.")
    except Exception as e:
        print(f"An error occurred: {e}")

def main():
    if len(sys.argv) != 3:
        print("Usage: python copy_file.py <source_file> <destination_file>")
        return

    source = sys.argv[1]
    destination = sys.argv[2]
    copy_file(source, destination)

if __name__ == "__main__":
    main()
















cmd command
python copy_file.py C:\Users\saniy\OneDrive\Documents\ambivert.docx "C:\Users\saniy\OneDrive\Desktop\copied ambivert.docx"
