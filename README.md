# ind
elastic indices
##
Specification: I needed metrics for index status. But I needed more articulate numbers.
_cat/indices passes back a large report. Needed was a more accurate status. This program returns
a hash where each key has a 3 element array. Each key is a grouped index name.
###
red yellow green
x 0 0 
x x 0 going yellow
0 x 0 stuck yellow (problem with node)
0 x x going green
0 0 x all green ready
##
key of the hash is the index name containing the unique part of the index name less date.
The data element is an array of 3 integers. red/yellow/green
This gives us an ariculate status of what might be wrong. The data will be appropriate to report to checkmk.
##
SSL will work fine. I havenot implemented client verify but you may specify either insecure or secure protocol.
example:
  ind https://hostname password
