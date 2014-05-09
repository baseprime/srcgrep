srcgrep
==========

Grep through entire source tree based on an expression or string. Will output line file and line number of matched expression.

## Example

Searching the source code of all files in the path provided, including file and line number.

    $ srcgrep -e '\$?paths?' -i -p /var/www/apps/myapp
      /var/www/apps/myapp:19:     my @source_paths  = (
      /var/www/apps/myapp:50:     my ($path, $ignore, @regexp, $test, $outfile, @patterns, @excludes);

    
## Usage:

    Usage:  srcgrep [OPTIONS] -e PATTERN [-e PATTERN, -e ...]
    
    The output will be in FILENAME:LINE#:LINE format convenient for gvim.
    
    Options:
    
    -h, --help     This usage statement.
    
    -i, --ignore   Ignore case when searching.
    
    -E, --exclude   Exclude filename pattern.
    
    -o, --outfile  Produce an outfile of results in /tmp.  The file
        will be named srcgrep-YYYYmmddHHMMSS.
    
    -t, --test     Do not run the search, but print the command instead.
    
    -p, --path     Path to search.  If left empty, the script will try to
        find the source directory.
    
    -e, --regexp   Search pattern using regular expressions. Additional
        patterns will result in OR searches
    
    
    EXAMPLES:
    
    To find source files matching either 'File' or 'Foo bar':
    srcgrep -e File -e 'Foo bar'
    
    To find files in /tmp with lines starting with Test or test:
    srcgrep -i -p /tmp -e '^test'


## License
##### [MIT License](http://opensource.org/licenses/MIT)
