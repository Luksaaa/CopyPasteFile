# File Copy Tool

A command-line utility for copying files and directories on Windows. This tool provides a simple interface to choose between different copy methods, including native Windows commands and Python's built-in libraries.

## Description

The File Copy Tool is designed to streamline the process of copying data by providing multiple backend options. Whether you need high-performance multi-threaded copying via Robocopy or a simple Python-based implementation, this tool consolidates these methods into a single interactive script.

## Features

- Interactive command-line interface.
- Support for three copy methods: Robocopy, XCOPY, and Python shutil.
- Automatic handling of subdirectories and system files (method-dependent).
- Multi-threaded copy support (Robocopy).
- Path normalization (removes quotes from input paths automatically).

## Requirements

- Python 3.x
- Windows OS (required for Robocopy and XCOPY methods)

## Installation

1. Clone or download the repository to your local machine.
2. Ensure Python is installed and added to your system's PATH.

## Usage

1. Run the script using Python:
   ```bash
   python CopyFiles.py
   ```
2. Select the desired copy method (1, 2, or 3).
3. Enter the source path when prompted.
4. Enter the destination path when prompted.

The script will handle the execution and notify you upon completion.

## Copy Methods

### 1. Robocopy (Recommended)
Uses the robust Microsoft Robocopy utility. It is configured for:
- Recursive copying (`/E`).
- Multi-threading with 32 threads (`/MT:32`) for maximum speed.
- Unbuffered I/O (`/J`) for faster transfer of large files.
- Console logging suppression for reduced terminal overhead.
- Automatic retries on failure (3 retries, 5-second wait).

### 2. XCOPY
Uses the legacy Windows XCOPY command with standard recursive and system file flags.

### 3. Python Shutil
Uses Python's native `shutil` library. This is a platform-independent method but may be slower for large directory structures compared to native Windows tools.
