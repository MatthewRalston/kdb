# README - KDB
> A Python CLI and module for k-mer profiles, similarities, and graph databases

NOTE: This project is pre-alpha, all of the badge links are broken and are just placeholders at the moment. Development is ongoing. But feel free to clone the repository and play with the code for yourself!

## Development Status

[![PyPI version](https://img.shields.io/pypi/v/kdb.svg)][pip]
[![Python versions](https://img.shields.io/pypi/pyversions/kdb.svg)][Pythons]
[![Travis build status](https://travis-ci.com/MatthewRalston/kdb.svg?branch=master)][TravisCI]
[![Coveralls code coverage](https://img.shields.io/coveralls/MatthewRalston/kdb/master.svg)][Coveralls]
[![ReadTheDocs status](https://readthedocs.org/projects/kdb/badge/?version=stable&style=flat)][RTD]


[pip]: https://pypi.org/project/kdb/
[Pythons]: https://pypi.org/project/kdb/
[TravisCI]: https://travis-ci.com/MatthewRalston/kdb
[Coveralls]: https://coveralls.io/r/MatthewRalston/kdb?branch=master
[RTD]: https://kdb.readthedocs.io/en/stable/

## Summary 

KDB is a Python library designed for bioinformatics applications. It addresses the ['k-mer' problem](https://en.wikipedia.org/wiki/K-mer) (substrings of length k) in a simple and performant manner. It generates a [De Brujin graph](https://en.wikipedia.org/wiki/De_Bruijn_graph) from the k-mer spectrum of fasta or fastq sequencing data and stores the graph and spectrum to the `.kdb` format spec, a bgzf file similar to BAM. 

The principle goal of the library is k-mer statistics and rapid access to specific k-mers and associated abundances with a Python CLI and API. Other goals include access to the k-mer count distribution, k-mer transition probabilities, and more by leveraging the bgzf specification. Another low-hanging fruit could be approximating demultiplexing coefficients for artificial metagenomes.


## Installation

OS X and Linux release:

```sh
pip install kdb
```

Development installation:

```sh
git clone https://github.com/MatthewRalston/kdb.git
pip install requirements.txt#requirements-dev.txt
PYTHONPATH=$PYTHONPATH:$(pwd)
```

## Usage Example

CLI Usage

```bash
kdb --help
kdb summary --help
# Build a [composite] profile to a new or existing .kdb file
kdb profile example1.fq.gz example2.fq.gz profile.kdb
# Calculate similarity between two (or more) profiles
kdb similarity profile1.kdb profile2.kdb (...)
```

API usage

```python
from kdb import fileutil, kmer_util, profile

# Read a kdb file
kdb_rdr = fileutil.KDBReader(open("example.kdb", 'rb'))
kdb_rdr.read_profile()

# Print a profile (a lightweight wrapper around array.array)
for c in kdb_rdr.profile:
  print(c)

# Create a KDB object
kdb = fileutil.KDB(kdbrdr.profile, kdbrdr.header)

# ... do something with the KDB object

# Create a KDB index

idx = index.IndexBuilder(kdb, kdb_rdr)
index_tuple = idx._index_lines()

# Save a kdb file
kdb_wrtr = fileutil.KDBWriter(open("example.kdb", 'wb'), kdb_rdr.get_header)
kdb_wrtr.write_profile(composite_profile, k)
```

## Documentation

Check out the [Readthedocs documentation](https://kdb.readthedocs.io/en/stable/), with examples and descriptions of the module usage.

## Development

```bash
pipenv run mamba test/*_spec.py
```

## License

Created by Matthew Ralston - [Scientist, Programmer, Musician](http://matthewralston.us) - [Email](mailto:mrals89@gmail.com)

Distributed under the GPL v3.0 license. See `LICENSE.txt` for the copy distributed with this project. Open source software is not for everyone, but for those of us starting out and trying to put the ecosystem ahead of ego, we march into the information age with this ethos.

## Contributing

1. Fork it (<https://github.com/MatthewRalston/kdb/fork>)
2. Create your feature branch (`git checkout -b feature/fooBar`)
3. Commit your changes (`git commit -am 'Add some fooBar'`)
4. Push to the branch (`git push origin feature/fooBar`)
5. Create a new Pull Request
