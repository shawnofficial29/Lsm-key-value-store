# LSM-Tree Key-Value Store

A persistent key-value storage engine written in Python. This semester project focuses on database storage, crash recovery, and LSM-tree architecture.

## Project goal

The goal is to build a key-value database that supports these operations:

```text
PUT key value
GET key
DELETE key
```

New data will first be saved in a write-ahead log and placed in an in-memory memtable. When the memtable reaches its limit, its entries will be sorted and written to disk as an SSTable.

## Current status

The GitHub repository and Python development environment have been created. The initial source, test, and data directories are ready. Pytest is installed and listed as a project dependency.

The storage operations have not been implemented yet. The next task is to implement and test the memtable.

## Planned features

- PUT, GET, and DELETE operations
- In-memory memtable
- Write-ahead log
- Crash recovery
- Immutable SSTable files
- Tombstones for deleted keys
- SSTable compaction
- Bloom filters
- TCP client-server interface
- Automated tests
- Performance benchmarks
- Docker support

## Planned architecture

```text
Client request
      |
      v
Write-ahead log
      |
      v
In-memory memtable
      |
      v
Sorted SSTable files
      |
      v
Compaction
```

## Project structure

```text
Lsm-key-value-store/
├── src/
│   └── lsm_store/
│       ├── __init__.py
│       ├── database.py
│       ├── memtable.py
│       └── wal.py
├── tests/
│   ├── test_database.py
│   ├── test_memtable.py
│   └── test_wal.py
├── data/
├── requirements.txt
├── pyproject.toml
└── README.md
```

## Development setup

Clone the repository:

```powershell
git clone https://github.com/shawnofficial29/Lsm-key-value-store.git
cd Lsm-key-value-store
```

Create a virtual environment:

```powershell
py -m venv .venv
```

Activate it on Windows:

```powershell
.\.venv\Scripts\Activate.ps1
```

Install the dependencies:

```powershell
python -m pip install -r requirements.txt
```

## Running tests

Run all tests with:

```powershell
python -m pytest -v
```

Tests will be added as each storage component is implemented.

## Development roadmap

- [x] Create the GitHub repository
- [x] Configure the Python virtual environment
- [x] Create the initial project structure
- [x] Install pytest
- [x] Add the requirements file
- [ ] Implement the memtable
- [ ] Implement the write-ahead log
- [ ] Add crash recovery
- [ ] Implement SSTables
- [ ] Implement compaction
- [ ] Add Bloom filters
- [ ] Add the TCP interface
- [ ] Add performance benchmarks
- [ ] Add Docker support

## Author

Shawn Dsouza