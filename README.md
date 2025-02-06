# Week-4-File-Handling-and-Exception-HandlingAssignment-
# Function to read a file, modify its content, and write to a new file
def read_and_modify_file():
    try:
        # Ask for the filename
        input_filename = input("Enter the name of the file to read: ")
        
        # Try to open the input file for reading
        with open(input_filename, 'r') as infile:
            content = infile.read()  # Read the entire file content
        
        # Modify content (for example, convert to uppercase)
        modified_content = content.upper()
        
        # Ask for the output filename to save the modified content
        output_filename = input("Enter the name of the file to write the modified content to: ")
        
        # Write the modified content to the new file
        with open(output_filename, 'w') as outfile:
            outfile.write(modified_content)
        
        print(f"File modified successfully! The modified content has been written to {output_filename}.")
    
    except FileNotFoundError:
        print("Error: The file you specified does not exist.")
    except IOError:
        print("Error: There was a problem reading or writing the file.")
    except Exception as e:
        print(f"An unexpected error occurred: {e}")

# Call the function
read_and_modify_file()
