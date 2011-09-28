python-parse-domain
===================

So, you have a bunch of URLs and want to display human-friendly domains from them.  Extracting the domain isn't as easy as splitting on dots, because of longer international TLDs.   

This module contains list of these TLDs so they can be extracted correctly, and allows you to specify the number of levels of the domain you want.

    >>> from parse_domain import parse_domain
    >>> parse_domain('http://google.com',1)
    'com'
    >>> parse_domain('http://google.com',2)
    'google.com'
    >>> parse_domain('http://guardian.co.uk',1)
    'co.uk'
    >>> parse_domain('http://guardian.co.uk',2)
    'guardian.co.uk'
    >>> parse_domain('http://www.guardian.co.uk',2)
    'guardian.co.uk'
    >>> parse_domain('http://tech.blog.guardian.co.uk',2)
    'guardian.co.uk'
    >>> parse_domain('http://tech.blog.guardian.co.uk',3)
    'blog.guardian.co.uk'
    >>> parse_domain('http://tech.blog.guardian.co.uk',4)
    'tech.blog.guardian.co.uk'
    >>> parse_domain('http://tech.blog.guardian.co.uk',5)
    'tech.blog.guardian.co.uk'

