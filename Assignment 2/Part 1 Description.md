# Part 1 : Asymmetric Encryption

Create an application that can encode using Asymmetric Encryption.

The application has two programs, the client and server. The server initialises a public and private key, then sets up a server socket. The client also initalises a set of keys, then connects to the server socket. The public keys are shared manually between the two programs by the user. Once the public keys are recieved, the client sends an encrypted message to the server.

The message is encrypted with the server's public key (which can be decrypted with the server's private key) and signed with the client's private key (which can be authenticated by the client's public key).
