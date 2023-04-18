# Simple-File-Metadata-Format
SFM (Simple File Metadata) is a human-readable YAML-based format for managing and tracking metadata, changes, and versions of data files.

## Overview

SFM consists of two main components:

1. **Metadata File (`*.metadata.yml`)**: Contains detailed metadata about a data file, such as file name, file type, file size, created date, last modified date, expiration date, file hashes, code repository URL, authors, data description, and data license.

2. **Latest File (`*.latest.yml`)**: A pointer to the latest version of a data file and its metadata, along with the next expiration date for when the latest file should be read again.

Look into ./src folder and files for a full list of supported metadata.

## Metadata File Example

```yaml
# file1.metadata.yml
file_name: file1.csv
file_type: csv
file_size: 12345
file_version: 1.0
file_path: /folder/file1.csv
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

## Latest file example

```yaml
# file1.latest.yml
latest_file_path: /folder/file1.csv
latest_metadata_path: /folder/file1.metadata.yml
expires_date: 2023-04-25
```

## How to use

To use SFM, create a .metadata.yml file for each data file in your repository and a .latest.yml file to point to the latest version of the data file and its metadata. Update the metadata files as needed to reflect changes in the data files.

When consuming data from a repository using SFM, read the .latest.yml file to determine the most recent version of a data file and its metadata. Use the metadata to verify file integrity, understand the file's content, and track changes over time.