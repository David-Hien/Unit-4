## Code
``` python
class quiz050:
    """ This class represents Quiz 50"""
    def __init__(self, message):
        self.message = message

        # This is the list given as a reference for the ASCII characters
        self.alphabet = [
            "### ##   ## ##  ### ###  ## # # ###  ## # # #   # # ###  #  ##   #  ##   ## ### # # # # # # # # # # ### ### ",
            "# # # # #   # # #   #   #   # #  #    # # # #   ### # # # # # # # # # # #    #  # # # # # # # # # #   #   # ",
            "### ##  #   # # ##  ##  # # ###  #    # ##  #   ### # # # # ##  # # ##   #   #  # # # # ###  #   #   #   ## ",
            "# # # # #   # # #   #   # # # #  #  # # # # #   # # # # # # #    ## # #   #  #  # # # # ### # #  #  #       ",
            "# # ##   ## ##  ### #    ## # # ###  #  # # ### # # # #  #  #     # # # ##   #  ###  #  # # # #  #  ###  #  "
        ]

    # This method prints out the characters in ASCII Art form
    def convert(self):
        # Assign a string to refer to as the alphabet
        map = "abcdefghijklmnopqrstuvwxyz"

        # Loops throught 5 lines
        for i in range(5):
            # Loops through all the letters
            for letter in self.message:
                # Lowercase to refer it to the map
                letter = letter.lower()

                # If the character is not in the alphabet, print "?"
                if letter not in map:
                    print(self.alphabet[i][-4:], end='')

                # Else print the character in the alphabet
                else:
                    # Two pointer (left and right) to slice the string into substring in between the pointers
                    l = map.index(letter) * 4
                    r = l + 4
                    print(self.alphabet[i][l:r], end='')

            # Skip line
            print()
        print()


# Run test cases
test1 = quiz050(message="E")
test2 = quiz050(message="ManhAtTan")
test3 = quiz050(message="gOLDen")
test4 = quiz050(message="Watch4pol")

test1.convert()
test2.convert()
test3.convert()
test4.convert()

```

## Run
```
/Users/hientrinh/Quiz/venv/bin/python /Users/hientrinh/Quiz/Quiz_050.py
### 
#   
##  
#   
### 

# # ### ### # # ### ### ### ### ### 
### # # # # # # # #  #   #  # # # # 
### ### # # ### ###  #   #  ### # # 
# # # # # # # # # #  #   #  # # # # 
# # # # # # # # # #  #   #  # # # # 

 ##  #  #   ##  ### ### 
#   # # #   # # #   # # 
# # # # #   # # ##  # # 
# # # # #   # # #   # # 
 ##  #  ### ##  ### # # 

# # ### ###  ## # # ### ##   #  #   
# # # #  #  #   # #   # # # # # #   
### ###  #  #   ###  ## ##  # # #   
### # #  #  #   # #     #   # # #   
# # # #  #   ## # #  #  #    #  ### 


Process finished with exit code 0
```
