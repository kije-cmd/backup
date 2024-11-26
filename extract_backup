#!/bin/bash

# Get the input file name from command line arguments
input_file="$1"

echo $input_file

# make file name without  .gpg
archive_file=$(basename "$input_file" .gpg)

# without .tar.gz
make_directory=$(basename "$archive_file" .tar.gz)

echo "$archive_file"
# Decrypt file with gpg 
gpg --output "$archive_file" --decrypt "$input_file"

mkdir $make_directory
# extract tar.gz file
tar -xvf "$archive_file" -C "$make_directory"

rm "$archive_file"
