# skos-history-query-generator
Generator of SPARQL queries to be used with skos-history RDF diff tool

# Usage
Please use Jupyter Notebook and Python3 to run this script. 

Currently configurations are provided for SKOS-Core and SRC-AP (an application profile used at the European Publication's Office for representing source files inside [VocBench3](http://vocbench.uniroma2.it/) )

This script uses CSV files as configurations and generates, for each row, the relevant SPARQL queries. The columns of CSV are as follows:
* "class", # this column indicates what class is the diffed instance
* "property", # this column indicates the property of the instance  (i.e. the relation connecteing instance URI to the value)
* "object property", # this column provides possibility to perform two level diff, needed in case of reified structures;
* "modifiable", # this column indicates (1) whether a query for update operation shall be generated 
* "language dependent" # this column indicates (1) whether the modification values need to be distinguished by language


# TODO 

* if the configuration statement has an object propoerty do not generate propoerty query but only a reified query
* return only one result per class instance for the deleted instances i.e. do not multiply the result set with the prefLabels
* support modification operation for any propeorty that is guaranteed/expected to have cardinality (1,1) or (0,1) i.e. max 1 (use modifiable flag in CSV)
* distinguish modifications based on language where needed (use languange depenent flag in CSV)

# Licence
This program is licenced under European Union Public License version 1.2 (EUPL-1.2).