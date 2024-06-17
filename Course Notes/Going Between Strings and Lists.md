# Going Between Strings and Lists: .split() and .join()
str.split() turns a string into a list of smaller strings, breaking on whitespace by default. This is super useful for taking you from one big string to a list of words.

    words = claim.split()
    words

    ['Pluto', 'is', 'a', 'planet!']


Occasionally, you'll want to split on something other than whitespace:

    datestr = '1956-01-31'
    year, month, day = datestr.split('-')


str.join() takes us in the other direction, sewing a list of strings up into one long string, using the string it was called on as a separator.

    '/'.join([month, day, year])
    '01/31/1956'

    # Yes, we can put unicode characters right in our string literals :)
    ' 👏 '.join([word.upper() for word in words])

    'PLUTO 👏 IS 👏 A 👏 PLANET!'

