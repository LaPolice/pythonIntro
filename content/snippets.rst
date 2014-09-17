===============
Useful snippets
===============

-----------
Write files
-----------

::

    # collected data in a list
    report_list = [
        'first line of report text',
        'here is another line of text',
        'writing one more line',
        'and one last line of report'
    ]
    
    # join the data
    formatted_report = '\n'.join(report_list)
    print report_list
    print '-' * 30
    print formatted_report
    
    # open/create a file in 'write' mode
    f = open(u"/Users/yourusername/Desktop/write_output.txt", 'w')
    
    # write the format data in the file, no need to save
    f.write(formatted_report)

Check here for more methods on the `file object <http://docs.python.org/2/library/stdtypes.html#file-objects>`_.
