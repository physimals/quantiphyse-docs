Using the Quantiphyse console
=============================

The console is an advanced tool which allows you to interact directly with the data structures within 
the program. You might use this to perform processing steps which don't have a predefined widget, using
the full power of the Numpy and Scipy libraries.

Objects provided
----------------

The main predefined variables are:

  - `ivm` - The volume management object. It provides the `add_overlay` and `add_roi` methods you need
    to get data into the viewer

  - Each existing data item is a named variable - for example if you have an overlay named `T10` there will
    be a variable `T10` which contains the data.

The following namespaces are predefined:

 - `np` - The Numpy module

Working with data
-----------------

Data objects are subclasses of Numpy arrays and can support any operations on them. To add new data into 
the viewer you use the `add_overlay()` or `add_roi()` methods.

Examples
--------

Add Gaussian noise to some data
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

::
    noisy_data = my_data + np.random.normal(0, 100) # Assumes we have loaded some data called my_data
    ivm.add_overlay('noisy_data', noisy_data)



