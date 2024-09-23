!/bin/bash

# Function to count the number of files in the current directory
function count_files {
    echo $(ls -1 | wc -l)
}

# Get the correct number of files
file_count=$(count_files)

# Initialize user guess
guess=-1

# Loop until the correct guess
while [[ $guess -ne $file_count ]]
do
    echo "Guess how many files are in the current directory:"
    read guess

    if [[ $guess -lt $file_count ]]
    then
        echo "Your guess is too low."
    elif [[ $guess -gt $file_count ]]
    then
        echo "Your guess is too high."
    else
        echo "Congratulations! You guessed the correct number of files."
    fi
done
