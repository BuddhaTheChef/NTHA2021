Directions 

Step 1: make sure you have python3 installed visit: https://www.python.org/downloads/ to download your verison

Step 2: Create an empty folder on your desktop and go to this repository: -----repo here-----

Step 3: In terminal or command prompt navigate into newly created folder and run git clone ----repo clone ----

Step 4: Open the folder with the text editor of your choice you should see these files:

        -input.txt
        -input5.txt
        -README.md
        -solve.py

Step 5: navigate to solve.py 

Step 6: To connect .txt file to solve.py and view parameters add code below inside main() function 

	file = open("input5.txt", "r")
	lines = file.readlines()
	file.close()
	#look for text
	for line in lines:
		line = line.strip()
		print( line )

Step 7: To view incoming parameters run "python solve.py input.txt" 

Step 8: The first bug I decided to fix is within the "parse_input(filepath)" function, it was throwing an error because it would include the grid size along with the rectangles it was trying to parse through so it would throw "ValueError: not enough values to unpack (expected 3, got 2)" becaue the first input of the txt file was only 2 characters. I decided to start itterating after the 0th index starting at the first which returned all the rectangles with their pid, length, width: "for i in range(1,len(file_contents))"

Step 9: For the function  __out_of_bounds(self, point) I added in a if statement that checks if point is within the grid array of self.state by creating 

 if point not in self.state:
            return True
        return False

if the point is not within the bounds of self.state then it returns true. and else returns false. 

Step 10: I moved to "def solve():" function here  I used recurssion to call on remaining and decrement the number to add each piece to the used pieces array and when remaining hits 0 we break out of the function returning the array of pieces with numbers 


Step 11: for the function "def place(self, piece):" I tried to fix the bug because it started with postion[0] for width and position[1] for length. I switched it because it the text file position[1] is width and position[0] is length for each piece

Step 12: for the bug in "def rotate(self):" I beleive the function wasnt being called right and saw rotated instead of rotate in the "def __str__(self):" funtion object so I switched it there.

