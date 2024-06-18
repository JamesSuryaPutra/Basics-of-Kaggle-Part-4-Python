# Building strings with .format()
Python lets us concatenate strings with the + operator.

    planet + ', we miss you.'

    'Pluto, we miss you.'


If we want to throw in any non-string objects, we have to be careful to call str() on them first

    position = 9
    planet + ", you'll always be the " + position + "th planet to me."

    TypeError                                 Traceback (most recent call last)
    /tmp/ipykernel_19/1802981568.py in <module>
          1 position = 9
    ----> 2 planet + ", you'll always be the " + position + "th planet to me."

    TypeError: can only concatenate str (not "int") to str


    planet + ", you'll always be the " + str(position) + "th planet to me."

    "Pluto, you'll always be the 9th planet to me."


This is getting hard to read and annoying to type. str.format() to the rescue.

    "{}, you'll always be the {}th planet to me.".format(planet, position)

    "Pluto, you'll always be the 9th planet to me."


So much cleaner! We call .format() on a "format string", where the Python values we want to insert are represented with {} placeholders. Notice how we didn't even have to call str() to
convert position from an int. format() takes care of that for us. If that was all that format() did, it would still be incredibly useful. But as it turns out, it can do a lot more.
Here's just a taste:

    pluto_mass = 1.303 * 10**22
    earth_mass = 5.9722 * 10**24
    population = 52910390
    
    # 2 decimal points, 3 decimal points, format as percent separated with commas
    "{} weighs about {:.2} kilograms ({:.3%} of Earth's mass). It is home to {:,} Plutonians.".format(
        planet, pluto_mass, pluto_mass / earth_mass, population,
    )

    "Pluto weighs about 1.3e+22 kilograms (0.218% of Earth's mass). It is home to 52,910,390 Plutonians."


    # Referring to format() arguments by index, starting from 0
    s = """Pluto's a {0}.
    No, it's a {1}.
    {0}!
    {1}!""".format('planet', 'dwarf planet')
    print(s)

    Pluto's a planet.
    No, it's a dwarf planet.
    planet!
    dwarf planet!

