# [Vigenere Cipher C++ implementation](https://github.com/KacperBiedka/vigenere-cipher)
## Simple implementation of basic file encryption and decryption using the Vigenere algorithm.
### After running the build and choosing the operation you will be required to pass 3 values: 
- #### `inputPath` - an absolute path to a file containing values for transform
- #### `outputPath` - an absolute path to a file where your result will be stored
- #### `keyword` - mandatory string used for calculating the char position in the alphabet, this value is needed to perform both the encryption and decryption - eg. `test`

---
note: double slash - `\\` - is only required on windows, you can use a single slash in the unix based operating system

## How does it work ?
### Encryption and Decryption
#### To encrypt a character the position of the sign is evaluated based on the current key character and current word character
![Vigenere](https://pages.mtu.edu/~shene/NSF-4/Tutorial/VIG/FIG-VIG-Table-EX-M.jpg)
#### In the example above you can see that we treat both word chars index as a position of a final character, so for this case the index of `M` is our `xOffset` and index of `H` is our `yOffset` and we find a character that's located at the `x, y` coordinates.
#### To decrypt the character we basically treat the encrypted char index as our `xOffset` value and subtract the `yOffset` from it to revert the ecryption operation
### Changing file content
#### To output the converted value to a new file the code iterates through all lines of the `inputPath` file. The Vigenere Cipher `transformLine` method is called for each line and a new converted line is returned as a result.
