## Encryption


**End-to-End Encryption**
- Only recipient can decrypt message
- Can only be decrypted by sender/recipient

**Is it a good idea?**
- If privacy is main goal, yes
- If security is important, then no


### Caesar Cipher

**How does it work?**
- The cipher works by giving a number value to a key. 
  Each plaintext letter is replaced by a new letter - the one found at the original letter's position in the alphabet plus or minus the value of the key.

**How can you break it?**
- Keep shifting the letters or frequency analysis. ombinations of letters appear more frequently than others in a given language

**What are the core weaknesses?**
- Only has 26 keys
- Fixed alphabet size
- Modifications to the ciphertext can also go undetected because it lacks authentication.

**What can be done to make it stronger?**
- Polyalphabetic encryption (Vigenere cipher)

**Decryption Task:**
Most common letter = n therefore the key is 17 to decrypt and 9 to encrypt	

Slave, I have set my life upon a cast,
And I will stand the hazard of the die.
I think there be six Richmonds in the field;
Five have I slain today instead of him.
A horse, a horse, my kingdom for a horse!


### Vernam Cipher

The encryption key, also known as the one time pad, is the only cipher proven to be unbreakable
The key must be:
- a truly random sequence greater or equal in length than the palintext and only ever used once
- shared with the recipient by hand, independently of the message and destroyed immediately after use
<br><br>

Rules for perfect secrecy:
- Key is never re-used
- Key is deisposed of securely
- Key is truly random
- Key is transferred securely


#### Computational Security

The keys are determined using a computer algorithm
A key derived from an algorithm can also be unpicked
Give enough ciphertext, computer power and time, any key can be determined and the message cracked
What makes things computationally secure is the amount of time it takes


By saying a cipher is computationally secure means that it can be decrypted however it will take a really long time to decrypt to the point its not worth.
