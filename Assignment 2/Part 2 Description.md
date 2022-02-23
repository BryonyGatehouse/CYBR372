# Part 2 : Key Management

Create a application that encrypts using a Keystore which securely saves the private and public keys.

The Keystore requires a password to access all the public keys, then another password to access the private key of a particular "alias". 

The application has two programs, the client and server. The server creates a server socket and retrieves it's private key and the client's public key from the keystore. The client connects to the server socket and retrieves it's private key and the server's public key from the keystore. These keys can then be used to encrypt, send, and decrypt a message sent between the client and server. 
