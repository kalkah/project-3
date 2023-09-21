# project-3
# Shell Scripting

## First Shell Script

shell-scripting directory was created using the command below:

**`mkdir shell-scripting`**

user-input.sh file was created using the command below:

**`touch user-input.sh`**

The code below was copied into the user-input.sh file
```
#!/bin/bash

# Prompt the user for their name
echo "Enter your name:"
read name

# Display a greeting with the entered name
echo "Hello, $name! Nice to meet you."
```
The command below was used to make the user-input.sh executable

**`sudo chmod +x user-input.sh`**

The script was run using this command below:

**`./user-input.sh`**

<img width="466" alt="image" src="https://github.com/kalkah/project-3/assets/95209274/53e562d8-edfe-43ba-b243-a5dcc1e94461">

## Directory Manipulation and Navigation

A script was written to display the current directory, create a new directory called "my_directory", change to that directory, create two new files inside it, list the files, move back one level up, remove "my_directory" and its contents, and finally list the files in the current directory again.

A new file was created using the command below:

**`touch navigating-linuxfilesystem.sh`**

The code below was written in the file
```
#!/bin/bash

# Display current directory
echo "Current directory: $PWD"

# Create a new directory
echo "Creating a new directory..."
mkdir my_directory
echo "New directory created."

# Change to the new directory
echo "Changing to the new directory..."
cd my_directory
echo "Current directory: $PWD"

# Create some files
echo "Creating files..."
touch file1.txt
touch file2.txt
echo "Files created."

# List the files in the current directory
echo "Files in the current directory:"
ls

# Move one level up
echo "Moving one level up..."
cd ..
echo "Current directory: $PWD"

# Remove the new directory and its contents
echo "Removing the new directory..."
rm -rf my_directory
echo "Directory removed."

# List the files in the current directory again
echo "Files in the current directory:"
ls
```

The command below was used to make the user-input.sh executable

**`sudo chmod +x navigating-linux-filesystem.sh`**

The script was run using this command below:

**`./navigating-linux-filesystem.sh`**

<img width="562" alt="image" src="https://github.com/kalkah/project-3/assets/95209274/e0ec4402-44ce-4050-b289-73af71a0fd26">

## File Operations and Sorting

A script was created that creates three files (file1.txt, file2.txt, file3.txt), displays the file in their current order, sorts them alphabetically, saves the sorted files in sorted_files.txt, display the sorted files, removes the original files, renames the sorted file to sorted _files_alphabetically.txt, and finally displays the contents of the final sorted file

sorting.sh file was created using the command below

**`touch sorting.sh`**

The code below was written in the sorting.sh file.

```
#!/bin/bash

# Create three files
echo "Creating files..."
echo "This is file3." > file3.txt
echo "This is file1." > file1.txt
echo "This is file2." > file2.txt
echo "Files created."

# Display the files in their current order
echo "Files in their current order:"
ls

# Sort the files alphabetically
echo "Sorting files alphabetically..."
ls | sort > sorted_files.txt
echo "Files sorted."

# Display the sorted files
echo "Sorted files:"
cat sorted_files.txt

# Remove the original files
echo "Removing original files..."
rm file1.txt file2.txt file3.txt
echo "Original files removed."

# Rename the sorted file to a more descriptive name
echo "Renaming sorted file..."
mv sorted_files.txt sorted_files_sorted_alphabetically.txt
echo "File renamed."

# Display the final sorted file
echo "Final sorted file:"
cat sorted_files_sorted_alphabetically.txt

```
Executable permission was set on the sort.sh using the command below:

**`sudo chmod +x sorting.sh`**

The script was run using **`./sorting.sh`**

<img width="483" alt="image" src="https://github.com/kalkah/project-3/assets/95209274/897907eb-a5c1-402a-911b-a76143e558e2">

## Working with Numbers and Calculations
Calculation.sh script defines two variables num1 and num2 with numeric values, performs basic arithmetric operations (addition, subtraction, multiplication, division and modulus), and displays the results. It also performs more complex calculations such as raising num1 to the power of 2 and calulating the square root of num2, and displays those results as well.

The file calculations.sh was created with this command **`touch calculations.sh`**

The following code was written in the calculations.sh using the nano editor

```
#!/bin/bash

# Define two variables with numeric values
num1=10
num2=5

# Perform basic arithmetic operations
sum=$((num1 + num2))
difference=$((num1 - num2))
product=$((num1 * num2))
quotient=$((num1 / num2))
remainder=$((num1 % num2))

# Display the results
echo "Number 1: $num1"
echo "Number 2: $num2"
echo "Sum: $sum"
echo "Difference: $difference"
echo "Product: $product"
echo "Quotient: $quotient"
echo "Remainder: $remainder"

# Perform some more complex calculations
power_of_2=$((num1 ** 2))
square_root=$(awk "BEGIN{ n=$num2; print sqrt(n) }")

# Display the results
echo "Number 1 raised to the power of 2: $power_of_2"
echo "Square root of number 2: $square_root"

```

Executable permission was set on the calculations.sh using the command below:

**`sudo chmod +x calculations.sh`**

The script was run using **`./calculations.sh`** command

<img width="374" alt="image" src="https://github.com/kalkah/project-3/assets/95209274/46bab60c-7f64-42ae-be58-935784ad2beb">


## File Backup and Timestamping

The backup.sh script focus on file backup and timestamp. The script defines the source directory paths, it then creates a timestamp using the current date and time, and created a backup directory with the timestamp appended to its name. The script then copies all files from the source directory to the backup directory using the cp command with the -r option for recursive copying. Finally, it displays a message indicating the completion of teh backup process and shows the path of the backup directory with the timestamps.

The backup.sh file was created using this command: **`touch backup.sh`**

The code below was written in the backup.sh file
```
#!/bin/bash

# Define the source directory and backup directory
source_dir="/path/to/source_directory"
backup_dir="/path/to/backup_directory"

# Create a timestamp with the current date and time
timestamp=$(date +"%Y%m%d%H%M%S")

# Create a backup directory with the timestamp
backup_dir_with_timestamp="$backup_dir/backup_$timestamp"

# Create the backup directory
mkdir -p "$backup_dir_with_timestamp"

# Copy all files from the source directory to the backup directory
cp -r "$source_dir"/* "$backup_dir_with_timestamp"

# Display a message indicating the backup process is complete
echo "Backup completed. Files copied to: $backup_dir_with_timestamp"

```

Executable permission was set on the sort.sh using the command below:

**`sudo chmod +x backup.sh`**

The script was run using **`./backup.sh`** command

<img width="523" alt="image" src="https://github.com/kalkah/project-3/assets/95209274/c2945ba4-c763-497e-9509-8e95391d275f">

