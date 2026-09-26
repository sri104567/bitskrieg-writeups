# Timestamped Secrets - cryptography
## Approach
After downloading the message and the code , i used cat on them and got the following info
Hint: The encryption was done around 1790147519 UTC
Ciphertext (hex): 44e98ac8b821d1b561b49f38c114c89405c1895b1f9425b6adc8e0911b68731a
In the code I saw a space for a timestamp, so i used nano test.py and copied the code and made a few changes in it to give me the flag.


## Solution
i wrote this code to get me just the key.

from hashlib import sha256

timestamp = 1790147519

key = sha256(str(timestamp).encode()).digest()[:16]

print(key.hex())

The key turned out to be ebcdce07f676504292b4029eea5a8d75
Then using an online Aes decoder i got the flag as academy{sa3S_sEc9t_3b464909}


## Flag
academy{sa3S_sEc9t_3b464909}

## Takeaway
AES uses the same key for encryption and decryption.
