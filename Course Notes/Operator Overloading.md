# Operator overloading
What's the value of the below expression?

    [3, 4, 1, 2, 2, 1] + 10

    TypeError                                 Traceback (most recent call last)
    /tmp/ipykernel_19/2144087748.py in <module>
    ----> 1 [3, 4, 1, 2, 2, 1] + 10

    TypeError: can only concatenate list (not "int") to list


What a silly question. Of course it's an error.
But what about...

    rolls + 10

    array([13, 14, 13, 14, 15, 15, 12, 11, 13, 13])


We might think that Python strictly polices how pieces of its core syntax behave such as +, <, in, ==, or square brackets for indexing and slicing. But in fact, it takes a very hands-off
approach. When you define a new type, you can choose how addition works for it, or what it means for an object of that type to be equal to something else.

The designers of lists decided that adding them to numbers wasn't allowed. The designers of numpy arrays went a different way (adding the number to each element of the array). Here are a
few more examples of how numpy arrays interact unexpectedly with Python operators (or at least differently from lists).

    # At which indices are the dice less than or equal to 3?
    rolls <= 3

    array([ True, False,  True, False, False, False,  True,  True,  True,
            True])

    xlist = [[1,2,3],[2,4,6],]

    # Create a 2-dimensional array
    x = numpy.asarray(xlist)
    print("xlist = {}\nx =\n{}".format(xlist, x))

    xlist = [[1, 2, 3], [2, 4, 6]]
    x =
    [[1 2 3]
    [2 4 6]]

    # Get the last element of the second row of our numpy array
    x[1,-1]

    6

    # Get the last element of the second sublist of our nested list?
    xlist[1,-1]

    TypeError                                 Traceback (most recent call last)
    /tmp/ipykernel_19/3020169379.py in <module>
          1 # Get the last element of the second sublist of our nested list?
    ----> 2 xlist[1,-1]

    TypeError: list indices must be integers or slices, not tuple


numpy's ndarray type is specialized for working with multi-dimensional data, so it defines its own logic for indexing, allowing us to index by a tuple to specify the index at each
dimension.
