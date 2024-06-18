# Backlash character usage in strings
The table below summarizes some important uses of the backslash character.

    What you type...	What you get	example	print(example)
    \'	'	'What\'s up?'	What's up?
    \"	"	"That's \"cool\""	That's "cool"
    \\	\	"Look, a mountain: /\\"	Look, a mountain: /\
    \n	
    "1\n2 3"	1
    2 3


The last sequence, \n, represents the newline character. It causes Python to start a new line.

    hello = "hello\nworld"
    print(hello)

    hello
    world


In addition, Python's triple quote syntax for strings lets us include newlines literally (i.e. by just hitting 'Enter' on our keyboard, rather than using the special '\n' sequence). We've already seen this in the docstrings we use to document our functions, but we can use them anywhere we want to define a string.

    triplequoted_hello = """hello
    world"""
    print(triplequoted_hello)
    triplequoted_hello == hello

    hello
    world

    True


The print() function automatically adds a newline character unless we specify a value for the keyword argument end other than the default value of '\n':

    print("hello")
    print("world")
    print("hello", end='')
    print("pluto", end='')

    hello
    world
    hellopluto

