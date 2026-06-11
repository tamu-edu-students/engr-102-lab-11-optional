# ENGR 102 Lab Topic 11 (optional)

## Activities
This **optional** lab consists of four activities. Please submit the following files to Gradescope.

1. [Dozenal Math](#dozenal-math)
2. [Romeo in Love](#romeo-in-love)
3. [Counting Coins](#counting-coins)
4. [Pixel Painter](#pixel-painter)

## Dozenal Math
Base twelve, also known as duodecimal or dozenal, is a number system that uses twelve as its base. In dozenal, the number twelve is denoted `10` which means `1` twelve and `0` ones. For contrast, in base ten (the decimal system) the number `12` means `1` ten and `2` ones. In dozenal, `100` means twelve squared, `1000` means twelve cubed, and so on. Various symbols have been used to stand for ten and eleven in dozenal; **for this lab use `X` for ten and `E` for eleven**.

An egg distributer is tasked with loading delivery trucks each day to ensure all customers receive eggsactly as many eggs as they ordered. Customers indicate how many crates, grosses, dozens, and single eggs they need on a simple order form. There are twelve eggs in one dozen, twelve dozens in one gross, and twelve grosses in one crate. This order is represented as a 4-digit number, from large to small. For example, a supermarket might have an order of `3400` which calls for `3` crates and `4` grosses, or a total of `5760` eggs. A resident might have an order of `0014` which calls for `1` dozen and `4` single eggs, or a total of `16` eggs.

Write a program named `dozenal_math.py` that takes as input a filename that contains 4-digit egg orders. Have your program read the file, add up the total number of eggs needed in base ten to place on the delivery truck, and print how many crates, grosses, dozens, and single eggs that is using the example output below.

Example file [`eggs.txt`](eggs.txt):
```
3400
0014
00X0
```

Example output using `eggs.txt`:
```
Enter the filename: eggs.txt
There are a total of 5896 eggs
3 crates, 4 gross, 11 dozen, and 4 eggs: 34E4
```

This lab is inspired by [Eggsactly a Dozen](https://dozenal.org/drupal/content/eggsactly-dozen.html) from [The Dozenal Society of America](https://dozenal.org/)


## Romeo in Love
Romeo is in love with Juliet, but he's also kind of vain. Romeo wants to know whose name is said more in the Shakespeare play `Romeo and Juliet` – his name or Juliet's. By "said more" it means appears in the dialogue among the characters. Note that a name can appear in places that are not dialogue. For example, the first line of the text file is the title of the play – that isn't dialogue. Then there is a listing of the characters of the play – that isn't dialogue either. Most importantly, in the play there are stage instructions like `[Juliet moves toward her mother.]`. The square brackets indicate that these are stage instructions and not dialogue. If the name Romeo or Juliet appears in a stage instruction, then it isn't in the dialogue.

Once again, Romeo is in love with Juliet. He never wants to be too far away from her. What is the largest number of characters which separate the words `Romeo` and `Juliet` in the entire text? Remember that case matters, so `ROMEO` is not the same as `Romeo`. Also, it doesn't matter if `Romeo` appears before `Juliet` or `Juliet` appears before `Romeo` in the text, however the occurrences must be consecutive. When counting characters, include spaces and new line `\n` characters. For example, the very first line of the file is `Romeo and Juliet`. There are 5 characters between `Romeo` and `Juliet` here – `a`, `n`, `d`, and two spaces. Likewise, `Juliet` appears on line `4998`, while `Romeo` appears on line `5001`. The `25` characters between these two words include three new line `\n` characters.

Romeo thinks that the phrase `Romeo and Juliet` is the most beautiful phrase in the world, and should appear everywhere. What is the most common word that appears after `Romeo` in the dialogue? What is the most common word that appears before `Juliet` in the dialogue? What do you conclude about the possibility of Romeo's wish?

Write a program named `romeo_in_love.py` that takes as input from the user a filename. Have your program count and print how many times Romeo's and Juliet's names appear in the dialogue, the largest number of characters between `Romeo` and `Juliet`, the most common word after `Romeo`, and the most common word before `Juliet`. Format your output as shown in the example below.

Example output using [`romeo_and_juliet.txt`](romeo_and_juliet.txt):
```
Enter the filename: romeo_and_juliet.txt
Romeo's name is spoken ??? times
Juliet's name is spoken ?? times
Largest number of characters between "Romeo" and "Juliet": ????
Most common word after "Romeo": ?
Most common word before "Juliet": ?
```

Note: Parsing out specific words, where they are in a text body, and what words are around them is in an important task in developing large-language models for programs like Chat-GPT.


## Counting Coins
While digging through a box of very old handheld game consoles, you find one that piques your interest. Wondering how it works, you access the source code and find a text file named [`game.txt`](game.txt) full of instructions, one per line. Each instruction consists of an operation (`coin`, `jump`, or `none`) and a signed number (like `+28` or `-3`). You quickly figure out that `coin` increases or decreases a value that stores the number of coins earned by the player, `jump` will jump to a new instruction relative to itself, and `none` does absolutely nothing. After executing a `coin` or `none` operation, the instruction immediately below is executed next. However, `jump +2` would continue to the instruction `2` lines below it, and `jump -5` causes the instruction `5` lines above to be executed next. The program ends when it attempts to execute an instruction immediately after the last instruction in the file.

Write a program named `count_coins.py` that opens the game file [`game.txt`](game.txt), executes the instructions, and creates a new file named `coins.txt` that contains only the numbers of coins gained or lost in the order the program is executed. Have your program output the total number of coins earned using the example output below.

Example output:
```
Total coins collected: ???
```

Example `coins.txt` file created by your program:
```
28
...
-87
4
8
```


## Pixel Painter
Run length encoding is a form of data storage where runs of data are stored as a single data value. A run of data is a sequence of the same value that occurs in many consecutive elements. This type of data storage is efficient for simple graphic images such as icons, line drawings, and [Conway's Game of Life](https://en.wikipedia.org/wiki/Conway%27s_Game_of_Life). For this activity, consider a binary image where each pixel is either light (a space) or dark (a character). Each line of the image is represented by comma separated values that indicate the number of consecutive pixels that are light and dark. The first value in a line always corresponds to the number of light pixels, and following values alternate between dark and light. For example, the line `1,2,3,4` represents `1` light pixel, followed by `2` dark pixels, `3` light pixels, and finally `4` dark pixels. If a space is used to represent light pixels and the character `●` is used to represent dark pixels, the line would look like this (spaces underlined for clarity): `_●●___●●●●`

Write a program named `pixel_painter.py` that takes as input a filename and a character, converts the contents of the file to pixel art, and writes the art to a new file of the same name but with the `.txt` extension. The first value in a line always corresponds to the number of light pixels.

Example file `pixel_triangle.csv`:
```
2,1,2
1,1,1,1,1
0,5
```

Example output using inputs `pixel_triangle.csv` and `A`:
```
Enter the filename: pixel_triangle.csv
Enter a character: A
pixel_triangle.txt created!
```

Example `pixel_triangle.txt` file created by your program:
```
  A  
 A A 
AAAAA
```

Files for testing your program:
- [`pixel_triangle.csv`](pixel_triangle.csv)
- [`pixel_tea.csv`](pixel_tea.csv)
- [`pixel_cat.csv`](pixel_cat.csv)
- [`pixel_star.csv`](pixel_star.csv)
- [`pixel_balloon.csv`](pixel_balloon.csv)


Revised Summer 2026 SNR
