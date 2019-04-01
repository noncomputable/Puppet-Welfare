# Information Adversity

Quick and easy web tool for calculating information adversity, for the experimental framework developed in _Plato's Puppeteer: Interface Design and User Welfare_.

Given data from a choice experiment like described in _Plato's Puppeteer_, 
it'll calculate the individual and aggregate information adversity and dump it to a CSV file.

Data should be provided as three CSV files.

1. Product data. The columns are distinct substitute sets and rows are the ranks of distinct products. The row number is taken to be the ID of the product in its set:

| Charger | Fire Hose | Pen |
|:-------:|:---------:|:---:|
|    1    |     2     |  2  |
|    2    |     3     |  5  |
|    3    |     7     |  1  |
|    4    |           |  9  |
|    5    |           |     |

2. Choice data. The columns are distinct substitute sets and rows are comma-separated IDs of the products each user nominates. The row number is taken to be the ID of the user whose choice data it is:

| Charger | Fire Hose | Pen |
|:-------:|:---------:|:---:|
|   3,2   |     1     |  4  |
|  2,7,3  |     2     | 4,3 |
|    5    |    1,2    |  4  |

3. Subject data. The rows are the IDs of the interface assigned to the users. The row number is taken to be the ID of the user assigned that interface:

| Interface ID |
|:------------:|
|       1      |
|       3      |
|       2      |

In the CSV file generated by the script, the columns are distinct interfaces and the rows are the information adversities of users for the respective interfaces. The row number is taken to be the ID of the user whose information adversity it is. The last row is the aggregate information adversity for each interface.
