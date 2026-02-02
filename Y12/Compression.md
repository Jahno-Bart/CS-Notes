#### Compressions

##### Lossless compression 
Lossless - A method of compression which doesnt remove data from the image

| Advantages | Disadvantages |
| -------------- | --------------- |
| No loss in quality | Lower data reduction |
| Can be reversed as original is kept | Bigger file sizes|
| Good for data you'd like to preserve |  |

<br><br>
##### Lossy compression

Lossy- A method of compression which removes unneeded data permanently

| Advantages | Disadvantages |
| -------------- | --------------- |
| Higher data reduction | Quality degrades due to higher rate of compression |
| Lots of tools, plugins, and software to support it | Can't get original back after compressing |
| Negligible loss in quality |  |


Used in images, audio and video

Audio - compression will remove sounds which are either too loud or too quiet to hear

You can also remove the bit-rate, which reduces the number of bit values for every second


<br><br>

##### Run-Length Encoding (RLE)

If you have large blocks of colour this is highly inefficient so instead you can store a colour and a repetition values
E.g. "Blue" 21 pixels, "Green" 40 pixels, "Blue" 39 pixels
So instead of needing 100x24(2400) bits for one line, We need 24+5, 24+6, 24+6 = 89 bits for this line

<br><br>

##### Dictionary based compression

RLE is good in images where there are blocks of colour
However when it comes to the english language it is actually pretty poor because you do not have repeated letters
In text we have alot of the same words, so what we can do is create a dictionary of only he words used and give them a shorter code.
But we'd also need to save the dictionary for it make sense
Which makes dictionary methods impractical for smaller files
But for large documents it becomes very usefil as a way of reducing file sizes
