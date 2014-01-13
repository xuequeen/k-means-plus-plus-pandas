K-means++ in Pandas
===================

An implementation of the [k-means++ clustering algorithm](http://en.wikipedia.org/wiki/K-means%2B%2B) using [Pandas](http://pandas.pydata.org/).

Prerequisites
-------------

* Python 2.7 or lower; this is not Python 3 compatible (yet).
* [Pandas](http://pandas.pydata.org/) (obviously).
* [NumPy](http://numpy.org)

Usage
-----

Here are the constructor arguments:

* `data_frame`: A Pandas data frame representing the data that you wish to cluster. Rows represent observations, and columns represent variables.

* `k`: The number of clusters that you want.

* `columns=None`: A list of column names upon which you wish to cluster your data. If this argument isn't provided, then all of the columns are selected. **Note:** Columns upon which you want to cluster must be numeric and have no `numpy.nan` values.

* `max_iterations=None`: The maximum number of times that you wish to iterate k-means. If no value is provided, then the iterations continue until stability is reached (ie the cluster assignments don't change between one iteration and the next).

* `appended_column_name=None`: If this value is set with a string, then a column will be appended to your data with the given name that contains the cluster assignments (which are integers from 0 to `k`).

Once you've constructed a `KMeansPlusPlus` object, then just call the `cluster` method, and everything else should happen automagically. Take a look at the `examples` folder.

TODO:
----

* Add on features that take iterations of k-means++ clusters and compares them via, eg, concordance matrices, Jaccard indices, etc.

* Given a data frame, implement the so-called [Elbow Method](http://en.wikipedia.org/wiki/Determining_the_number_of_clusters_in_a_data_set#The_Elbow_Method) to take a stab at an optimal value for `k`.

* Make this into a proper Python module that can be installed via pip.