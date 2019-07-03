# Basic-Blockchain
Blockchain that stores the hash and relevant data of a file that is saved in IPFS with asymmetric encryption

Steps to run the project:

1. Request Privilages
2. Run the command => . env.sh
3. Run the command => go run main.go
4. Open localhost:8080 to see the blockchain with the genesis block
5. Append a new block using POSTMAN {"SK": 12345}
6. See the block appended to the blockchain
7. After installing GPG, generate a key using the command => gpg --gen-key
8. Export the public key using the command => gpg --export --armor -email > pubkey.asc
9. A file named pubkey.asc should be generated. Move this pubkey.asc to the first computer.
10. Now, import the public key using the command => gpg --import pubkey.asc
11. To see that the import is successful, check if the public key is listed in the keys using the command => gpg --list-keys
12. Now, initialize IPFS and start Daemon using commands => ipfs init, ipfs daemon
13. Encrypt the file => gpg --encrypt --recipient "Iron Man" Sample.pdf 
14. You should see a new file created with name Sample.pdf.gpg
15. Now upload the encrypted file to ipfs using the command => ipfs add Sample.pdf.gpg
16. We get the output => added QmXSpgc7NpoZ63sethdmoBxqHe7dg9FBs5XuPGtwkBct5b Sample.pdf.gpg
17. Let's double check that our file is available on IPFS using the command => ipfs pin ls
18. On the second computer, download the file using the command => ipfs get QmXSpgc7NpoZ63sethdmoBxqHe7dg9FBs5XuPGtwkBct5b
19. Decrypt using the command => gpg --decrypt QmXSpgc7NpoZ63sethdmoBxqHe7dg9FBs5XuPGtwkBct5b > SampleDecrypted.pdf
20 . Open the file and view the content.
