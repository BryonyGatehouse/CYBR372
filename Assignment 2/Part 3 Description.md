# Part 3 : Secure Channel

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
