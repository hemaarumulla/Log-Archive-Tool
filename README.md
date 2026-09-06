# Log Archive Tool

A simple command-line tool that archives and compresses log files into a `.tar.gz` file with a timestamp.

This project was built as part of a Linux/Bash scripting project.

## Features

* Accepts a log directory as a command-line argument
* Validates whether the provided directory exists
* Compresses log files into a `.tar.gz` archive
* Creates a timestamp-based archive filename
* Stores archives in a separate directory
* Logs the archive creation date and time
* Provides basic error handling

## Requirements

* Linux or Unix-based environment
* `sh` or a compatible shell
* `tar`
* `gzip`

## Project Structure

```text
log-archive-tool/
├── log-archive
├── README.md
└── test_logs/
    ├── app.log
    ├── database.log
    └── user.log
```

## Usage

Make the script executable:

```bash
chmod +x log-archive
```

Run the tool:

```bash
./log-archive <log-directory>
```

Example:

```bash
./log-archive test_logs
```

## Archive Output

The tool creates a compressed archive with the following format:

```text
logs_archive_YYYYMMDD_HHMMSS.tar.gz
```

Example:

```text
logs_archive_20260906_214500.tar.gz
```

The archive is stored in:

```text
$HOME/log_archives/
```

## Archive Log

Each successful archive is recorded in:

```text
$HOME/log_archives/archive.log
```

Example:

```text
2026-09-06 21:45:00 - Archive created: /home/user/log_archives/logs_archive_20260906_214500.tar.gz
```

## How It Works

1. The user provides a log directory.
2. The script validates that the directory exists.
3. An archive directory is created if it does not already exist.
4. The current date and time are generated.
5. A timestamp-based archive filename is created.
6. The provided log directory is compressed using `tar` and `gzip`.
7. The archive is stored in the archive directory.
8. The archive creation date and time are recorded in `archive.log`.

## Example Commands

Create test log files:

```bash
mkdir -p test_logs

echo "Application started" > test_logs/app.log
echo "Database connected" > test_logs/database.log
echo "User logged in" > test_logs/user.log
```

Run the tool:

```bash
./log-archive test_logs
```

Check the created archives:

```bash
ls $HOME/log_archives
```

View the archive log:

```bash
cat $HOME/log_archives/archive.log
```

View the contents of an archive:

```bash
tar -tzf $HOME/log_archives/logs_archive_YYYYMMDD_HHMMSS.tar.gz
```

## Technologies Used

* Linux
* Shell Scripting
* `tar`
* `gzip`

## Concepts Practiced

* Shell scripting
* Command-line arguments
* Shell variables
* Conditional statements
* File and directory validation
* File permissions
* Date and time handling
* File compression
* Archive creation
* Exit status handling
  
## Project URL

https://roadmap.sh/projects/log-archive-tool
