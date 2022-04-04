# Assignment 2 : Analysis

## Part 1 : Asymmetric Encryption

Create an application that can encode using Asymmetric Encryption.

The application has two programs, the client and server. The server initialises a public and private key, then sets up a server socket. The client also initalises a set of keys, then connects to the server socket. The public keys are shared manually between the two programs by the user. Once the public keys are recieved, the client sends an encrypted message to the server.

The message is encrypted with the server's public key (which can be decrypted with the server's private key) and signed with the client's private key (which can be authenticated by the client's public key).

## Part 2 : Key Management

Create a application that encrypts using a Keystore which securely saves the private and public keys.

The Keystore requires a password to access all the public keys, then another password to access the private key of a particular "alias". 

The application has two programs, the client and server. The server creates a server socket and retrieves it's private key and the client's public key from the keystore. The client connects to the server socket and retrieves it's private key and the server's public key from the keystore. These keys can then be used to encrypt, send, and decrypt a message sent between the client and server. 

## Part 3 : Secure Channel

Using a Keystore, create an application which sends messages between a client and server using a secure channel. 

A secure channel uses a shared secret that both the client and server know (i.e. a key K). Everytime the secure channel is initialized, a new value is generated for the key K (a new secret is shared). 
Messages are numbered, authenticated and encrypted. The authenication is completed using a MAC which contains the message, the message index, and the length of the message. This prevents a malicious person from tampering with the file without going unnoticed. 

Master Key (K) is sent via asymmetric encryption:
- Retrieve private/public keys from Keystore
- Create new Master Key
- Encrypt and Authenticate Master Key
- Send via socket connection
- Master Key can then be used for messaging

To do this, four keys are created using the Master Key:
- A key to encrypt messages to be sent
- A key to decrypt messages recieved
- A key to authorise messages to be sent
- A key to authenticate messages recieved

Message is sent via secure channel:
- Split message into 32 bytes
- For each 32 byte piece:
  - Get the message number (one more than the previous)
  - Authenticate the length, number, and piece
  - Encrypt the piece and authentication using a keystream
