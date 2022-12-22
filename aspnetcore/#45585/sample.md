1. replace directory separator with `.`
1. character `.` based Splitting folder names for validation
   1. folders first character validation
      1. verify that the format of the first character of the folder matches the rule, if not, add the prefix character `_`
         - correct rules
           - letter
           - [unicode designation "Pc" (punctuation, connector)](https://www.compart.com/en/unicode/category/Pc)
      1. verify that the format of the first character of the folder matches the rules, if not, delete the character
         - correct rules
           - letter
           - decimal digit
           - [unicode designation "Pc" (punctuation, connector)](https://www.compart.com/en/unicode/category/Pc)
           - [unicode designation "Mn" (mark, nonspacing)](https://www.compart.com/en/unicode/category/Mn)
           - [unicode designation "Mc" (mark, spacing combining)](https://www.compart.com/en/unicode/category/Mc)
           - [Unicode designation "Me" (mark, enclosing)](https://www.compart.com/en/unicode/category/Me)
   1. verify that the folders character format matches the rule, if not, replace the character with `_`
      - correct rules
        - letter
        - decimal digit
        - [unicode designation "Pc" (punctuation, connector)](https://www.compart.com/en/unicode/category/Pc)
        - [unicode designation "Mn" (mark, nonspacing)](https://www.compart.com/en/unicode/category/Mn)
        - [unicode designation "Mc" (mark, spacing combining)](https://www.compart.com/en/unicode/category/Mc)
        - [Unicode designation "Me" (mark, enclosing)](https://www.compart.com/en/unicode/category/Me)
1. folder name cannot be a single underscore - add another underscore to it

- sample

| subpath                         | subpath identifier              | description                                                                                          |
| :------------------------------ | :------------------------------ | :--------------------------------------------------------------------------------------------------- |
| wwwroot/`.1997`/nice-day.js     | wwwroot.`._1997`.nice-day.js    | character `.` based Splitting folder,folders first character mismatch rule, add prefix character `_` |
| wwwroot/`.nice-day`/nice-day.js | wwwroot.`.nice_day`.nice-day.js | character `.` based Splitting folder,folders character mismatch rule, replace character with `_`     |
| wwwroot/`-`/nice-day.js         | wwwroot.`__`.nice-day.js        | folder name cannot be a single underscore - add another underscore to it                             |
