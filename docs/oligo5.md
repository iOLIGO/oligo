
## OLIGO5

Python object composed of oligo. The oligo database file based on the h5 file structure can contain one or more oligo files(tests/test_data/sample.oligo5).

```python

from ioligo import OLIGO5

oligo5_test = OLIGO5("test")
oligo5_file = "tests/test_data/oligo/test.oligo5"
oligo5_test.read(oligo5_file)

oligo5_test.name
# 'test'
oligo5_test.oligos
# {'G-sample': [<oligo.oligo.OLIGO object at 0x7fcb26336a30>]}
type(oligo5_test.oligos["G-sample"])
# <class 'list'>
oligo5_test.oligos["G-sample"][0].name
# 'sample'
olgio5_test.help()
# "more info: https://github.com/iOLIGO/oligo/blob/main/docs/oligo5.md"
oligo5_test.info()
# 'test_info.tsv'
```

### info formate

|groups|oligos|number|
|:----:|:----:|:----:|
|group1|oligo1,oligo2,...oligon|number1,number2,...,numbern|
|group2|oligo1,oligo2,...oligon|number1,number2,...,numbern|
| ... | ... | ... |
|groupn|oligo1,oligo2,...oligon|number1,number2,...,numbern|



## More usage

- Read multiple oligo files at the same time to form an oligo5 file.

```python
oligo1 = "./test.oligo"
oligo2 = "./test/test2.oligo"
oligo3 = "./test/test3.oligo"
from ioligo import OLIGO5
oligo5_test = OLIGO5("test")
oligo5_test.read_foligo(oligo1, oligo2, oligo3)
```

- Read all oligo files in the directory at the same time to form an oligo5 file.

```python
oligos_dir = "./test"
from ioligo import OLIGO5
oligo5_test = OLIGO5("test")
oligo5_test.read_doligo(oligos_dir)
```

- Perform statistics on data sets in oligo5

```python
oligo5_test.info("test_data/oligo/doligo5")
```

- Output as oligo5 file

```python

oligo5.to_oligo5("test_data/oligo/doligo")

```

- Output as oligo dir

```python
oligo5.to_oligo("test_data/oligo/O5toO")
```