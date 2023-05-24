# Simple-File-Metadata-Format
SFM (Simple File Metadata) is a human-readable YAML-based format for managing and tracking metadata, changes, and versions of data files.

## Overview

**Metadata File (`*.metadata.yml`)**: Contains metadata about a data file, such as file type, file size, created date, last modified date, expiration date, file hashes and more. The metadata file should be
 - placed in the same folder as the data file it describes
 - have the same name as the data file it describes, with the addition of a .metadata.yml extension
 
**Example structure:**`
 /folder/file1.csv
 /folder/file1.metadata.yml

Look into ./src folder and files for a full list of supported metadata.

## Metadata File Example

```yaml
# file1.metadata.yml
file_type: csv
file_size: 12345
file_version: 1.0
created_date: 2023-04-18
last_modified_date: 2023-04-18
expires_date: 2023-04-25
hash_md5_value: abcdef1234567890
code_repository_url: https://github.io/example-repo
authors:
  - author_name: John Doe
    author_email: john.doe@example.com
  - author_name: Jane Doe
    author_email: jane.doe@example.com
data_description: A sample CSV file containing example data.
data_license: CC BY 4.0
```

## How to use as a data provider
Simply create/generate a .metadata.yml file for each data file.