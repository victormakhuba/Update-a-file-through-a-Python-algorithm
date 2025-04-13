# Update a File Through a Python Algorithm

# 📌 Project Description

At my organisation, access to restricted content is controlled via an **allow list** of IP addresses (`allow_list.txt`). A separate **remove list** identifies IP addresses that should no longer have access. I created a Python algorithm to **automate the process of updating the allow list** by removing the specified IPs in the remove list.

---

# 📂 Step-by-Step Breakdown

### 1. Open the File That Contains the Allow List

First, assign the file name to a variable:


#Assign 'import_file' to the name of the file

import_file = "allow_list.txt"


### Use a with statement to open and read the file:

#Build 'with' statement to read the initial contents of the file

with open(import_file, "r") as file:

    # Use '.read()' to store the contents in a variable named 'ip_addresses'
    ip_addresses = file.read()
    
### 2. Convert the String to a List

## Split the string into a list of IP addresses:


#Use '.split()' to convert 'ip_addresses' from a string to a list
ip_addresses = ip_addresses.split()

### 3. Iterate Through the Remove List

## Use a for loop to iterate through each item in remove_list:


#Loop through 'remove_list'

## for element in remove_list:

    # Check if 'element' is in 'ip_addresses'
    
    if element in ip_addresses:
    
        # Use '.remove()' to remove the element
        
        ip_addresses.remove(element)
        
### 4. Update the File With the Revised List

## Convert the list back into a newline-separated string and write it back to the file:


#Convert 'ip_addresses' back to a string for writing
ip_addresses = "\n".join(ip_addresses)

#Rewrite the file with the updated list
with open(import_file, "w") as file:
    file.write(ip_addresses)
    
### ✅ Summary
This project demonstrates how I:

Opened and read from allow_list.txt

Converted the file contents from a string to a list

Iterated through a separate remove_list and removed matching IPs from the list

Wrote the updated list back to the file in the correct format

This script helps automate access control in environments using allow lists for restricted content access.

### 🛠️ Technologies Used

Python 3

File handling (open, read, write)

List methods (split, remove, join)

Control flow (for, if)

## 📁 Files Included

allow_list.txt – File containing allowed IP addresses

remove_list – List (in code or separate file) of IPs to be removed

Python script – Automates the update process

