🛠️ Update a File Through a Python Algorithm
📄 Project Description
At my organisation, access to restricted content is controlled using an allow list of IP addresses, stored in a file called allow_list.txt. A separate remove list identifies IP addresses that should no longer have access. I created a Python algorithm to automate the update of the allow list by removing these IP addresses.

📂 Step 1: Open the Allow List File
Assign the file name to a variable:


# Assign 'import_file' to the name of the file
import_file = "allow_list.txt"
Use a with statement to open the file in read mode:


# Read the initial contents of the file
with open(import_file, "r") as file:
    ip_addresses = file.read()
The with statement ensures the file is properly closed after reading.

file.read() converts the file's contents into a single string.

🧱 Step 2: Convert the String to a List
Convert the string of IP addresses into a list for easier manipulation:


# Convert 'ip_addresses' from a string to a list
ip_addresses = ip_addresses.split()
.split() separates the string into a list using whitespace by default.

🔁 Step 3: Iterate Through the Remove List
Assuming you already have a list called remove_list, use a for loop to process it:


# Loop through 'remove_list'
for element in remove_list:
    # Check if element is in 'ip_addresses' before removing
    if element in ip_addresses:
        ip_addresses.remove(element)
This ensures you only remove IPs that are actually present in the allow list.

💾 Step 4: Update the File with the Revised IP List
First, convert the list back into a string:


# Convert 'ip_addresses' back to a string for writing
ip_addresses = "\n".join(ip_addresses)
Each IP will be written on a new line using \n as a separator.

Now, overwrite the original file:


# Rewrite the original file with updated IP addresses
with open(import_file, "w") as file:
    file.write(ip_addresses)
"w" mode opens the file for writing and replaces the existing content.

✅ Summary
This algorithm:

Opens and reads the IP addresses from allow_list.txt.

Converts the data from string to list format.

Iterates through a predefined remove_list to eliminate unwanted IP addresses.

Converts the updated list back to a string and writes it to the same file.

As a result, the allow_list.txt file is cleaned and automatically updated based on the remove_list, ensuring only authorised IP addresses retain access to the restricted content.
