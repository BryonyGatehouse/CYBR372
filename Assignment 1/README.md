# Assignment 1 : Implementation

## Part 1 : File Encryption

Create a program which can encrypt and decrypt a text using the AES algorithm with a given IV.

## Part 2 : IV

Extend Part 1 to hide the IV. This involves saving the IV within the encrypted file and extracting it in the decryption stage.

## Part 3 : Salt

Create a key from the password using a salt and iteration count to further secure the message.

## Part 4 : Metadata

Extend Part 3 to include metadata about the file. Include a logger. 

# Assignment 1 : Report

## Part 1 : File Encryption

Explain the design choices made in the code. 

## Part 2 : IV

Explain how you implemented the IV into the code written for Part 1 and the design choices you made.

## Part 3 : Salt

Describe how you created a unique key so each message has a unique key using the message count. Explain why this makes the communication more secure.

## Part 4 : Metadata

Describe how you implemented the metadata. Explore how secure your program is considering Kerckhoff's Princple. 
