# 1968-FORTH
Original  Forth for IBM 1130 written by Charles Moore in 1968.

This implementation consists of 2 parts, a 645 line file written in IBM 1130 assembly language, and a 235 line text file listing, dumped from the IBM 1130 disk, but originally created as a deck of punched cards.


These listings came to light sometime around 2011, and in March 2018 attracted the interest of Carl Claunch, an IBM 1130 restoration enthusiast. Most of the detective work concerning the operation of this Forth has been performed and documented by Carl Claunch.

Please see FORTH-68_notes.txt and 


Part of the difficulty in understanding the listings, was the use of the IBM proprietary EBCDIC (Extended Binary Coded Decimal Interchange Code) on the IBM 1130. Charles Moore created his own character coding to make the use of hexadecimal numbers easier and to facilitate alphabetical dictionary searches. Neither of these character coding schemes are compatible with ascii.


The IBM 1130 was a fairly simple 16-bit computer, with a load-store architecture, a single accumulator and three index registers X1, X2, X3, stored at locations 01, 02, 03 in the core memory.


Moore used X1 as a pointer to a 28 word workspace. X2 was used as the data stack pointer, and X3 had various minor uses.


The assembly language listing implements a text interpreter and provides the kernel from which the Forth language can be built. It implements 28 primitive functions and generates the dictionary structure to allow further words to be added.

Forth words are entered into memory as packed character strings. Two characters are packed into each 16-bit word of memory. Words are deliminated by whitespace, the blank or space character. Moore's character encoding allocated the hexadecimal digits 0-F to character codes $00 to $0F. This allowed the easy conversion of typed characters to binary literals.

The remainder of the uppercase characters are encoded from $10 (G) to $22 (Z).

New Forth words are defined with a statement beginning with a dot and ending with a comma. This was later changed to the more familiar colon and semicolon notation.
