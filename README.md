# Detective RSA

In this assignment, you will use RSA functions to discover the secret behind the mysterious `sus.txt` and `rev.txt` files.

The content of the file `sus.txt` is encrypted using a public key. Your task is to find the correct
private key out of 20 possible keys in the `key_pairs` directory to decrypt that message.
The starter code is in `rsa.py`. Complete it and submit only `rsa.py` to Gradescope.

## Options to implement

```
a. Generate public and private keys 
b. Find the right key and decrypt the message in sus.txt 
c. Sign a message and verify it 
d. Find Miss Reveille's key pair that she used to sign rev.txt 
q. Quit 
```

### a. Generate a public/private key pair, encrypt, and decrypt
1. Generate a public/private key pair using 2048 bits key length using the function `generate_keys()`. Save the public and private keys in two files.
1. Encrypt a plaintext using the function `encrypt_message()`.
1. Decrypt a cyphertext using the function `decrypt_message()`.

### b. Find the right key and decrypt the message in sus.txt

1. Write the function `find_decrypt_key()`, to find which key in the `key_pairs` directory can decrypt the `sus.txt` message.
1. Once you find the right key, decrypt the file `sus.txt`. 
1. Write the decrypted message in the file `sus_decrypted.txt`. Note: You should realize it was written by Miss Rev.
1. Your next task is to find Miss Rev's signature key in the `key_pairs` directory. **This is not the same key as the one used in part b**.

### c. Sign a message using the private key from part a.1 and verify the signature

Write the functions `sign_message()` and `verify_message()` to sign and verify a message, respectively.
1. Sign a message using the private key from part a.1.
1. Write the signature in a file `signed_msg.txt`.
1. Verify the signature using the public key from part a.1.

### d. Identify the real Reveille's signature
Find the correct Reveille's signature by verifying the signature of the message in `sus_decrypted.txt`.
Use a method similar to **part b** to find which key is used to sign the message`rev.txt`.

## PyCryptodome
We need pycryptodome to run this program. If not installed, to install pycryptodome in Python 3, type:
```
make install
```
or
```
python3 -m pip install pycryptodome
```

## Usage
To run the program, type:

```
make run
```

To clean up the files generated by the program, type:

```
make clean
```

## Important notes:
1. A small starter video here: https://youtu.be/4Le42qqSZeA
2. You only need read(`r`) and write(`w`) access to the files. Use the `b` flag when opening the files along with `r` and `w`. Read more at: https://www.programiz.com/python-programming/methods/built-in/open
3. In the key_pairs directory, the public key suffix is `_pub`, and the private key suffix is `_priv`.
4. Your program will be manually tested for correctness with additional test cases.
5. Your program should execute with no errors and warnings.
