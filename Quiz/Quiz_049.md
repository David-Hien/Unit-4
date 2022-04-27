## Code
``` python
class quiz049:
    """ This class represents Quiz 49"""
    def __init__(self, binary):
        self.binary = str(binary)

    # This method converts binary into unary
    # It uses the window sliding method that traces the list with two pointers: left and right
    def convert(self):
        # Guard clause exit the program if there is no input
        if not self.binary:
            return "Invalid input"

        # Create the left pointer
        l = 0

        # Create variable for result
        result = "00 0" if self.binary[0] == "0" else "0 0"

        # Create the right pointer that goes through all elements in the binary
        for r in range(1, len(self.binary)):
            # Guard clause exit the program if non binary input given
            if self.binary[r] != "0" and self.binary[r] != "1":
                return "Invalid input"

            # Checks if the value at the right pointer is the same as the value at the left pointer
            if self.binary[r] == self.binary[l]:
                # Adds "0" if the values are the same
                result += "0"
            else:
                # Adds "_00_" if value at right pointer is "0" and "_0_" if value is "1"
                # Also adds a "0" since count is 1 
                result += " 00 0" if self.binary[r] == "0" else " 0 0"
                
                # Moves the left pointer to the right pointer, reseting the window
                l = r

        return result


# Run tests
test1 = quiz049(1000011)
test2 = quiz049(1111011)
test3 = quiz049(111)
test4 = quiz049(100)

print(test1.convert())
print(test2.convert())
print(test3.convert())
print(test4.convert())

```

## Run
```
/Users/hientrinh/Quiz/venv/bin/python /Users/hientrinh/Quiz/Quiz_049.py
0 0 00 0000 0 00
0 0000 00 0 0 00
0 000
0 0 00 00

Process finished with exit code 0
```
