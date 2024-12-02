- 👋 Hi, I’m @ebuse123
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
ebuse123/ebuse123 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
import os
import shutil

def copy_files_with_structure(source_dir, target_dir):
    """
    Copies all files from the source directory to the target directory,
    maintaining the same folder structure.

    Parameters:
    source_dir (str): The path to the source directory.
    target_dir (str): The path to the target directory.
    """
    # Walk through the source directory
    for root, dirs, files in os.walk(source_dir):
        # Create the corresponding directory structure in the target directory
        for dir_name in dirs:
            source_subdir = os.path.join(root, dir_name)
            target_subdir = source_subdir.replace(source_dir, target_dir, 1)
            os.makedirs(target_subdir, exist_ok=True)

        # Copy each file to the corresponding directory in the target directory
        for file_name in files:
            source_file = os.path.join(root, file_name)
            target_file = source_file.replace(source_dir, target_dir, 1)
            shutil.copy2(source_file, target_file)
            print(f"Copied {source_file} to {target_file}")

# Example usage
if __name__ == "__main__":
    source_directory = "path/to/source/folder"
    target_directory = "path/to/target/folder"

    copy_files_with_structure(source_directory, target_directory)
