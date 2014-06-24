Canary-Python
=============

Canary-Python is a library that you can drop into your existing Python application's directory which will permit one to 
integrate the Canary API in a Pythonic-way.

Requirements
------------

* Python 2.6+
* [Requests](http://docs.python-requests.org/en/latest/)
* An API key from Canary itself.

This should work just fine under any OS that runs Python.

Using
-----

Getting started is pretty straightforward. It's just matter of importing it and then setting your API key.

    >>> from canary import framework
    >>> c = framework.canary(api_key='5e884898da28047151d0e56f8dc6292773603d0d6aabbdd62a11ef721d1542d8')

Using the above example, any function executed thereafter will populate the received data in the *c.data* variable. 
Bear in mind that any actions made using the framework will overwrite the data. This will be changed in the future.

Output data will match what is provided in the [documentation](https://canary.pw/help/api/).

### Search

To perform a search, you can perform the following:

    >>> c.search('hacked')

Queries can be done just like the web interface including the bang operators. More information can be found 
[here](https://canary.pw/help/#using).

Search results will be just like the documentation linked to has shown.

### Viewing

To view a document, you'll need a valid *reference* ID from either the website via the 'item' argument or from a 
search result done within the search function.

It can be done as follows:

    >>> c.view('7e1619922171a48696e2cf2ebe314bee')

Data will appear as what is stated in the documentation.

### Storing

Users who are community members can upload data to the Canary database using the store function. This feature is not 
documented as it is not a feature typical to the average user.

The following information is required in order to upload into the database:

* Document's title
* Document's data (body)
* Source of the document (predefined by the community)
* Source URL of the document

It can then be pushed to the database using the following:

    >>> c.store(title='My title', text='My text', source='mysource', source_url='https://mysource/1.txt')

It will return an output that lets you know if it is successful or not.

Changelog
---------

### Version 0.1 (June 23, 2014)

* First version