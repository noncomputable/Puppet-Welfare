# Information Adversity

Quick and easy web tool for calculating information adversity, for the experimental framework developed in 
[_Plato's Puppeteer: Measuring How Design Affects Decisionmaking_](http://noncomputable.github.io/plato.html).

You can use it live [here](http://noncomputable.github.io/Information-Adversity/).

Given data from a choice experiment, 
it'll calculate the individual and aggregate information adversity and dump it to a CSV file.

Data should be provided as three CSV files. The tables below are just toy examples, not how actual data should look.

1. Product data. The columns are distinct substitute sets and rows are the qualities of distinct products in those sets. The row number is taken to be the ID of the product in its set:

| Charger | Fire Hose | Pen |
|:-------:|:---------:|:---:|
|    1    |     2     |  1  |
|    2    |     1     |  4  |
|    3    |     3     |  2  |
|    4    |           |  3  |
|    5    |           |     |

2. Choice data. The columns are distinct substitute sets and rows are semicolon-separated IDs of the products each user nominates in the given set. The row number is taken to be the ID of the user whose choice data it is:

| Charger | Fire Hose | Pen |
|:-------:|:---------:|:---:|
|   3;2   |     1     |  4  |
|  2;7;3  |     2     | 4;3 |
|    5    |    1;2    |  4  |

3. Interface data. The columns are distinct interfaces. Each has one row: a semicolon-separated list of the IDs of users assigned to it.

| Feature A | Feature B |
|:---------:|:---------:|
|     2     |    0;1    |

In the CSV file generated by the script, each column is a distinct interface and the rows are the information adversities of users assigned the given interfaces. The row number is taken to be the ID of the user whose information adversity it is. The last row in each column is the aggregate information adversity of the given interface.

|      Feature A     |      Feature B      |
|:------------------:|:-------------------:|
|                    |        0.125        |
|                    | 0.40277777777777773 |
| 0.3333333333333333 | 0.26388888888888884 |
| 0.3333333333333333 |                     |
