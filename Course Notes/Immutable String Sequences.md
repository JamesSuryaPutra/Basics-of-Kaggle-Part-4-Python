# Immutable string sequences
But a major way in which they differ from lists is that they are immutable. We can't modify them.

    planet[0] = 'B'
    # planet.append doesn't work either

    TypeError                                 Traceback (most recent call last)
    /tmp/ipykernel_19/2683731249.py in <module>
    ----> 1 planet[0] = 'B'
          2 # planet.append doesn't work either

    TypeError: 'str' object does not support item assignment

