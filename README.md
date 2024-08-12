# Module12-Challenge-NoSQL-Databases

Data Analytics Boot Camp - Module 12 - NoSQL Databases \
NoSQL Challenge

---

# Results

The *NoSQL* subfolder contains the following files:

- **NoSQL_setup.ipynb**
- **NoSQL_analysis.ipynb**

# Implementation notes

Part 1: Database and Jupyter Notebook Set Up

- Used the *mongoimport* utility to import the data provided in *establishments.json*
- The command-line text used to perform the import is included at the top of *NoSQL_setup.ipynb*

Part 2: Update the Database

- Added the restaurant "Penang Flavours" to the database, by inserting a new document using using the supplied details.
- Queried the BusinessTypeID corresponding to BusinessType "Restaurant/Cafe/Canteen", and updated the new restaurant record with that ID value.
- Confirmed the new Restaurant entry was added to the database, and its BusinessTypeID value was updated accordingly, by utilising the ObjectId saved from the insert step.
- Removed documents with 'LocalAuthorityName' of Dover.
- Converted Latitude/Longitude values and Rating values to appropriate numeric data type.

Part 3: Exploratory Analysis

- Queried for various field values using PyMongo comparison operators (documentation reference below).
- Pattern matching in strings via $regex evaluation operator (article and documentation references below), to find the full name of the London local authority (City of London Corporation).
- PyMongo standard search implementation pattern using 'find':
    - *collection*.find(query).sort(sort).limit(limit)
- PyMongo aggregation pipeline implementation pattern:
    - pipeline = [match_query, group_query, sort_query]
    - *collection*.aggregate(pipeline)

# References

The following references were used in the development of the solution for this Challenge.

## PyMongo - inserted_id
- How to get the object_id in PyMongo after an insert https://stackoverflow.com/questions/8783753/how-to-get-the-object-id-in-pymongo-after-an-insert

## PyMongo - querying by data type
- https://www.mongodb.com/docs/manual/reference/operator/query/type/

## PyMongo - query comparison operators
- https://www.mongodb.com/docs/manual/reference/operator/query-comparison/

## PyMongo - Regular Expression pattern matching
- https://stackoverflow.com/questions/3483318/performing-regex-queries-with-pymongo
- https://www.mongodb.com/docs/manual/reference/operator/query/regex/

## PyMongo - working with / searching by MongoDB ObjectId
- https://pymongo.readthedocs.io/en/stable/api/bson/objectid.html
- https://www.geeksforgeeks.org/search-by-objectid-in-mongodb-with-pymongo-python/
