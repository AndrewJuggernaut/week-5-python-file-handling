# week-5-python-file-handling
Python File Handling

def write_to_file(filename, content):
  """
  Writes content to a file in write mode.

  Args:
    filename: The name of the file to write to.
    content: The content to be written to the file.
  """
  try:
    with open(filename, "w") as file:
      file.write(content)
      print(f"Successfully wrote to {filename}")
  except PermissionError:
    print(f"Error: Permission denied to write to {filename}")
  except Exception as e:
    print(f"Error: An unexpected error occurred: {e}")

def read_from_file(filename):
  """
  Reads the contents of a file and displays them on the console.

  Args:
    filename: The name of the file to read from.
  """
  try:
    with open(filename, "r") as file:
      content = file.read()
      print(f"\nContents of {filename}:\n{content}")
  except FileNotFoundError:
    print(f"Error: File {filename} not found")
  except Exception as e:
    print(f"Error: An unexpected error occurred: {e}")

def append_to_file(filename, content):
  """
  Appends content to a file in append mode.

  Args:
    filename: The name of the file to append to.
    content: The content to be appended to the file.
  """
  try:
    with open(filename, "a") as file:
      file.write(content)
      print(f"\nSuccessfully appended to {filename}")
  except PermissionError:
    print(f"Error: Permission denied to write to {filename}")
  except Exception as e:
    print(f"Error: An unexpected error occurred: {e}")

# Initial content to write
initial_content = """This is the first line of text.
Here's another line with a number: 42.
And a final line for now.
"""

# Write initial content to the file
write_to_file("my_file.txt", initial_content)

# Read the contents of the file
read_from_file("my_file.txt")

# Additional content to append
append_content = """\nHere are some additional lines appended to the file:
Line 1 of the appended content.
Line 2 with some more text.
"""

# Append content to the file
append_to_file("my_file.txt", append_content)

# Read the contents of the file again (including appended content)
read_from_file("my_file.txt")
