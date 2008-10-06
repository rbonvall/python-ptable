# ptable

## Overview

The `ptable` module provides a `Table` class that can be used to pretty-print
tabular data.  A `Table` instance takes an iterable of rows (e.g. a list of
tuples), that can be pretty-printed by calling the `print_table` method.

Options can be set by assigning some attributes:

    table.sort_key = <sorting key function>
    table.headers = <tuple of column headers>
    table.align = <iterable of column alignments>
    table.col_max_widths = <tuple of maximum column widths>
    table.col_separator = <column separator string>
    table.repeat_headers_after = <number of rows after which the headers are printed again>
    table.header_separator = <True if a line is to be drawed below the header row>

## Example

Loading data into the table:

    >>> from ptable import Table
    >>> data = [(27000, "foo", 32), (5300, "barbar", 451), (132, "!", 3)]
    >>> t = Table(data)
    >>> t.print_table()
    27000 foo    32 
    5300  barbar 451
    132   !      3  

Setting some properties:

    >>> t.col_separator = " | "
    >>> t.headers = ('Price', 'Product', 'Id')
    >>> t.align = 'rll'
    >>> t.print_table()
    Price | Product | Id 
    27000 | foo     | 32 
     5300 | barbar  | 451
      132 | !       | 3  

Writing to a file:

    >>> t.print_table(stream=open('/tmp/data', 'w'))

## Author

Roberto Bonvallet, rbonvall@gmail.com

## License

This module is released under the [WTFPL](http://sam.zoy.org/wtfpl/).

