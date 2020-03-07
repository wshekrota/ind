
**ind**

**elastic indices**

Specification: I needed metrics for index status. But I needed more articulate numbers.
_cat/indices passes back a large report. Needed was a more accurate status. This program returns
a hash where each key has a 3 element array. Each key is a grouped index name.

**red yellow green**

1. x 0 0       red                    
2. x x 0       going yellow
3. 0 x 0       stuck yellow problem with node
4. 0 x x       going green
5. 0 0 x       green ready

Key of the hash is the unique part of the index name less date.
The data element is an array of 3 integers. red/yellow/green
This gives us an articulate status of what might be wrong. The data will be appropriate to report to checkmk.

SSL will work fine. I have not implemented client verify but you may specify either insecure or secure protocol.
example:
  ind https://hostname password
