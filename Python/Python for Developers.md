**Annotations:**
	- Code Documentation within your code that help other programmers understand its functionality and purpose.
	- Used to specify the types of arguments and return values for functions - these are a part of the code and are interpreted by tools such as linters and type checkers.
	**Types of Annotations**:
		1. Variable/argument Annotation: Type of data that the variable or argument expects
		2. Return Annotation: Informs programmers about the type of data that is returned by the function.
		3. Docstring: Description of the function.
	**Variable Annotation**
		- Use a colon and/or | to annotate a variable with a type
		ex: 
			number: int = 15
		ex: 
			number: int | float = 15 
		**Nested Annotations**
		ex: 
			numbers: list[int | float ] = [123, 123 ,1512.124, 123]
		ex:
			var1: dict[str, int]
	**Return Annotation**
		- Use: -> syntax:
		ex: 
			def addition(first: int, second: int) -> int:
				return first + second
	**Docstring** 
		- Is a string placed at the beginning of the function or module or class, enclosed in triple quotes """...""" and can span multiple lines:
		ex:
			def add(a: int, b: int) -> int:
				"""This function receives two integer arguments and returns its sum."""
				return a + b
**Help:**
	*To get information about a function or object, you can use the **help()** function*
		ex: 
			help(add
**Function Arguments:**
	*Positional Arguments:*
		- Have a *position* inside the function code
		- Has to be the correct number of arguments when function is called
		ex: 
			def user_data(name, surname)
				print("Name:", name)
				print("Surname:", surname)
			user_data("John", "Smith")
	*Optional Arguments:*
		- You can assign a default value to the positional argument using the = operator:
		ex:
			def user_data(name="UnkownName", surname="UnkownSurname")
				print("Name:", name)
				print("Surname:", surname)
			user_data("John", "Smith")
			user_data("John")
			user_data( )
		- The default value makes the corresponding positional arguments optional, but the total number of positional arguments required to be passed remains strict.
	*Arbitrary Arguments (*args):*
		- Commonly referred to as a *Variable-length argument*, or *arbitrary argument list*.
		- In Python, the * *args* syntax is used to pass a varying number of arguments to a function. It allows you to pass any number of positional arguments to a function, and it collects them into a tuple
		ex: 
			def multiply(* *args*):
				result = 1
				for arg in args:
					print(result,"times", arg)
					result * *= arg*
				return result
	*Keyword Arguments:*
		- Can specify the position of an argument using the keyword (argument name) and the assignment (=) operator:
			 ex: 
				def user_data(name, surname)
					print("Name:", name)
					print("Surname:, surname)
				user_data(surname="Smith", name="John")			
	*Arbitrary Keyword Arguments*:
		- Allows us to pass a specific number of named arguments
		- Use the *keys()* dictionary method to get all taken keywords, and use the *items()* to get the key-value pairs
**Unpacking**
	- To pass arguments from a *list* or *tuple* to a function, you can unpack it using the asterisk before the *list* or *tuple* name. 
	ex:
		def multiply(* *args*)
			print("Args:", args)
			result = 1
			for arg in args:
				result * *=* arg
			return result
		arguments = [11, 22, 33, 44, 55]
		print("Result:", multiply(* *arguments*))
	- For keyword argument unpacking, use two asterisks
**Example of Arguments, unpacking:**
	def snake_and_sum( * *args*, ** **kwargs**):
	    snake = []
	    summary = 0
	    for arg in args:
	        if isinstance(arg, str):
	            snake.append(arg)
	        elif isinstance(arg, int):
	            summary += arg 
	    for key, value in kwargs.items():
	        snake.append(key)
	        if isinstance(value, int):
	            summary += value  
	    return "-".join(snake), summary  # packs into tuple (string, int)
	string, result = snake_and_sum(123, 12, "sss", bold=1231, first="sad"  snake="sum")
	print("Snake:", string)
	print("Summary:", result)
**Errors:**
	- What is an exception? - An event that is raised during the execution and stops the interpreter
		- Raising exceptions helps to stop the interpreter and prevent unexpected results that could damage the entire project
		- Catching exceptions is important because it allows the program to handle errors gracefully and continue executing without terminating abruptly. 
	*Examples:*
	**TypeError**
			- This exception is raised when a function takes the value with an unexpected type:
				ex:
					print("First print")
					len(15)
					print("Second print")
				**Output:**
					First print
					------------------------------------------------------------------
								   1 print("First print")
					--------> 2 len(15)
								   3 print("Second print")
					TypeError: object of type 'int' has no len()
	**ValueError**
			- This exception is raised when a function or method takes an unexpected value
			ex:
			from math import sqrt
				print("First print")
				sqrt(-5)
				print("Second print")
				**Output**
				------------------------------------------------------------------
								   1 print("First print")
					--------> 2 sqrt(-5)
								   3 print("Second print")
					ValueError: math domain error
	**ZeroDivisionError**
		- Self explanatory
	**SyntaxError**
		- This is an exception of a completely different nature. If previous exceptions were raised by the interpreter, the SyntaxError raises by the *linter*
			*Note:* The **linter** is a tool that analyzes your code before executing.
		- For this error, all code is not executed! Previous errors executed all code before the error.
	**Raising an Error**
		- use the *raise* keyword
		ex: 
			raise ValueError("Wrong value!")
	**Handling**
		- There are different keywords used to control program errors:
			1. *try*: this keyword is used for the code block where we expect the error. 
			2. *except*: this keyword is used for the code block executed if an error is raised.
			3. *else*: this keyword is used to perform certain logic if errors are not raised.
			4. *finally*: this keyword is used for the code block that always executes after all structure.
		**Try and Except**:
		- *try* code block  waits for errors, and the *except* catches it
		- If the *try* block is executed without errors, the *except* block will not be executed.
		- The *try* block raises the exactly one error because executing stops after an error
			ex: 
				lst = []
				try:
					lst.append("first") # executed
					lst.append("second") # executed
					1 / 0 # error
					lst.append("third") # not executed
				except:
					print("Error caught")
				print(lst)
		**else and finally**
			ex:
				try:
					print("try: Start")
					# 1 / 0
					print("try: End") # If 1 / 0 is uncommented, this does not appear
				except:
					print("except: Error is raised") # this appears if 1 / 0 is uncommented
				else:
					print("else: The try block is executed successfully") # will not execute if 1 /                                                                                        0 is uncommented
				finally:
					print("finally: Always executed")
**Virtual Environment**
	- Python has a wide variety of modules that can be installed using the console command `pip`, and among them, there are many different versions of Python available.
	- The *virtual environment* allows you to isolate the version of Python and the list of modules for a specific project
	- It is an Isolated Development Environment
	- **Creating a virtual environment:**
		Step 1: Create a folder for your project.
		Step 2: Open the terminal in your folder
			1. Open the project folder and copy the path to this folder in your file explorer.
			2. Open the Command prompt (press Win + R, type "cmd", and press Enter).
			3. Type *cd* followed by a space, then paste the path to the project folder that you copied earlier. *cd "your_path"*
			4. Press Enter to change the current directory to the project folder
		Step 3: Create venv (Virtual environment)
			For Windows:
			python - m venv venv_name
		Step 4: Activate scripts. Run command.
			For Windows:
			venv_name\\Scripts\\activate
			or 
			venv_name\\Scripts\\activate.bat
	**Project Requirements:**
		- There are many different modules that are suitable for various projects. They are installed using the `pip` command (for example, `pip install pandas`). And each project has its own list of such modules, which is usually stored in a file called `requirements.txt`.
			- == - Exact version Match
			- ~= - Compatible version
			- >= - Minimum version
			- <= - Maximum version
			- > - Minimum compatible version
			- < - Maximum compatible version
			- != - Non-equal version
		- **Installing requirements:**
			1. Activate the virtual environment where you want to install the requirements
			2. Run the following command:
				For Windows:
				pip install - r requirements.txt
				*Note*: requirements.txt must be placed in the Project Folder with venv
			3. To create **requirements file:**
				pip freeze > requirements.txt
	**Integrated Development Environment (IDE)**
		- IDE is a software application that provides comprehensive facilities for software development.
		- *PyCharm* is one of the best IDEs for Python development
			Step 1: Open the PyCharm
			Step 2: Open/Create project
			Step 3: Look at the interpreter Settings. (Bottom right corner)
			Step 4: Create a new Interpreter. If you click on the  `Add New Interpreter`
			button, a menu for creating a new interpreter will appear.
		- *VS Code* is another popular IDE:
			Step 1: Open a new folder in VS Code and create the main.py file for a more convenient view.
			Step 2: Open New Terminal
			Step 3: Create a new Virtual Environment via Terminal
			Step 4: Activate. 
			
		
			
		
					
			