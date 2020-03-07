
**ind**

**elastic indices**

Specification: I needed metrics for index status. But I needed more articulate numbers.
_cat/indices passes back a large report. Needed was a more accurate status. This program returns
a hash where each key has a 3 element array. Each key is a grouped index name.
```
_cat/indices (for a one name collection might look like)
green open log-yourname-2020.03.01 SUUvU6M1Rj-yEhnDj6cJrw 5 1  483505 0 315.8mb 157.9mb
green open log-yourname-2020.02.27 XSSiXFEkTqyAO-ghXqcFqA 5 1 1343163 0 859.1mb 429.5mb
green open log-yourname-2020.03.02 wmPv_XifS0m-c9X96DO2jQ 5 1      25 0 102.5kb  51.2kb
green open log-yourname-2020.03.08 uDCpU01kTOK_iwMDY5Oapw 5 1  225504 0 141.7mb  70.8mb
```

**red yellow green**
```
1. x 0 0       red                    
2. x x 0       going yellow
3. 0 x 0       stuck yellow problem with node
4. 0 x x       going green
5. 0 0 x       green ready
```
Key of the hash is the unique part of the index name less date.
The data element is an array of 3 integers. red/yellow/green
This gives us an articulate status of what might be wrong. The data will be appropriate to report to checkmk.

```
output of ind for this if alll green
map[index-name-prefix:[0,0,000068758787587]
```

SSL will work fine. I have not implemented client verify but you may specify either insecure or secure protocol.
example:
  ind https://hostname password
