**For Loops:**
	Looping through strings:
		ex:
			text = 'Nothing'
			for i in text:
				print(i,!)
		Output:
			N !
			o !
			t !
			h !
			i !
			n !
			g !
	Range function:
		range(min,max+1,step)
		ex:
			To range numbers from 0 to 10 with step of one:
			range(0,11,1)
			Using in a for loop (decreasing #s from -1 to -5):
				for i in range(-1,-6,-1)
					print(i)
			Output:
				-1 
				-2 
				-3
				-4
				-5
	Break/Continue/pass statements:
		- Break is used to terminate the loop
		- continue is used to skip a block of code in the loop for the current             iteration only
		- The pass statement is a null statement. Nothing happens when the                 statement is executed
			- Typically used as a placeholder for future code, as you will not get an          error
	Enumerate Function:
		- With the enumerate function, we can access both the value and its index         numbers
		ex:
			numbers = [2,3,8,5,6,7,8,11,8]
			for i, v in enumerate(numbers):
				print('Numbers[', i, '] =', v)
	Matrix Loops:
		ex: 
			for i in range(len(matrix)) - this loops through rows
				for j in range(len(matrix[i])) - this loops through columns
**While Loops:**
	- The while statement checks the condition. The condition must return a boolean value: either True or False.
	- For working with lists, use len(list):
		ex: 
			numbers = [1, 2, 4, 5, 7]
			i = 0
			while i < len(numbers)
				print(numbers[i])
				i += 1
		*Note*: Often need to use len(numbers) - 1
**Nested Loops:**
	len(matrix) - is the number of *rows*
	len(matrix[i]) - is the number of *columns*
	