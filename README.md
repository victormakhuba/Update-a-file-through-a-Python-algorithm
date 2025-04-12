# **Update-a-file-through-a-Python-algorithm**

**Project description**

At my organization, access to restricted content is controlled with an allow list of IP addresses. The "allow_list.txt" file identifies these IP addresses. A separate remove list identifies IP addresses that should no longer have access to this content. I created an algorithm to automate updating the "allow_list.txt" file and remove these IP addresses that should no longer have access. 

**Open the file that contains the allow list**

For the first part of the algorithm, I opened the "allow_list.txt" file. First, I assigned this file name as a string to the import_file variable:

#Assign 'import_file' to the name of the file

import_file = "allow_list.txt"

**Then, I used a with statement to open the file:**

#Build 'with' statement to read in the initial contents of the file
with open(import_file, "r") as file:

In my algorithm, the with statement is used with the .open() function in read mode to open the allow list file for the purpose of reading it. The purpose of opening the file is to allow me to access the IP addresses stored in the allow list file. The with keyword will help manage the resources by closing the file after exiting the with statement. In the code with open(import_file, "r") as file:, the open() function has two parameters. The first identifies the file to import, and then the second indicates what I want to do with the file. In this case, "r" indicates that I want to read it. The code also uses the as keyword to assign a variable named file; file stores the output of the .open() function while I work within the with statement.

**Read the file contents**

In order to read the file contents, I used the .read() method to convert it into the string.

**with open(inport_file, "r") as file:**

#Use '.read()' to read the imported and stor it in a variable named       'ip_addresses'
ip_addresses = file.read()

When using an .open() function that includes the argument "r" for “read,” I can call the .read() function in the body of the with statement. The .read() method converts the file into a string and allows me to read it. I applied the .read() method to the file variable identified in the with statement. Then, I assigned the string output of this method to the variable ip_addresses. 

In summary, this code reads the contents of the "allow_list.txt" file into a string format that allows me to later use the string to organize and extract data in my Python program.

**Convert the string into a list**

In order to remove individual IP addresses from the allow list, I needed it to be in list format. Therefore, I next used the .split() method to convert the ip_addresses string into a list:

#Use '.split()' to convert 'ip_addresses' from a string to a list

ip_addresses = ip_addresses.split()

The .split() function is called by appending it to a string variable. It works by converting the contents of a string to a list. The purpose of splitting ip_addresses into a list is to make it easier to remove IP addresses from the allow list. By default, the .split() function splits the text by whitespace into list elements. In this algorithm, the .split() function takes the data stored in the variable ip_addresses, which is a string of IP addresses that are each separated by a whitespace, and it converts this string into a list of IP addresses. To store this list, I reassigned it back to the variable ip_addresses.

**Iterate through the remove list**

A key part of my algorithm involves iterating through the IP addresses that are elements in the remove_list. To do this, I incorporated a for loop:
#Build iterative statement
#Name loop variable 'element'
#Loop through 'remove_list'
for element in remove_list:

The for loop in Python repeats code for a specified sequence. The overall purpose of the for loop in a Python algorithm like this is to apply specific code statements to all elements in a sequence. The for keyword starts the for loop. It is followed by the loop variable element and the keyword in. The keyword in indicates to iterate through the sequence ip_addresses and assign each value to the loop variable element.
  
**Remove IP addresses that are on the remove list**

My algorithm requires removing any IP address from the allow list, ip_addresses, that is also contained in remove_list.  Because there were not any duplicates in ip_addresses, I was able to use the following code to do this:

for element in remove_list:

#Create conditional statement to evaluate if 'element' is in 'ip_addresses'
if element in ip_addresses:
#use the '.remove()' method to remove
#elements from 'ip_addresses'

ip_addresses.remove(element)

