# Ransomware-Simulation
This project demonstrates a basic ransomware simulation written in Python using the cryptography package. The simulation includes both an encryption script (rans.py) and a decryption script (decrypt.py).

Prerequisites
Python 3.x installed on your system.

cryptography library installed. You can install it using:
pip install cryptography
Project Files
rans.py: The script that encrypts files in the current directory.
decrypt.py: The script that decrypts the encrypted files using a previously generated key.
mykey.key: The file where the encryption key is stored.
How It Works
Encryption Script (rans.py)
File Discovery: The script searches for all files in the current directory, excluding itself (rans.py), the key file (mykey.key), and the decryption script (decrypt.py).
Key Generation: The script generates a random encryption key using the cryptography package and saves it to mykey.key.
File Encryption: Each discovered file is read, encrypted using the generated key, and then overwritten with the encrypted contents.
Ransom Note: A message is printed to the console, simulating a ransom demand.
Decryption Script (decrypt.py)
File Discovery: The script searches for all encrypted files in the current directory, excluding itself, the key file, and the encryption script.
Key Retrieval: The script reads the encryption key from mykey.key.
File Decryption: The script decrypts each file using the key and writes the original contents back to the files. If the decryption fails (e.g., due to an incorrect key), an error message is displayed.
Usage Instructions
1. Run the Encryption Script
Caution: Running the encryption script will encrypt all files in the current directory, potentially making them inaccessible without the decryption key. Use this only in a controlled environment.
python3 rans.py
2. Run the Decryption Script
To decrypt the files, run the decryption script. Make sure mykey.key is present in the same directory.
python3 decrypt.py
Error Handling
If the decryption fails, the script will catch the error and notify you, ensuring that you are aware of potential mismatches between the encryption key and the data.
InvalidToken: This error occurs if the provided key does not match the one used for encryption.
Disclaimer
This project is for educational and research purposes only. It is a demonstration of how ransomware might work and should not be used for malicious purposes. The author is not responsible for any misuse of this code. Always use this in a secure, controlled environment.
