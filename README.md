# mysql-recovery-tool
Read-only MySQL InnoDB recovery tool with fragment carving. Recover dropped tables, truncated tables, deleted rows and undo accidental UPDATEs from MySQL 5.0–9.0.
# MySQL Recovery Tool

A read-only MySQL InnoDB recovery utility with built-in fragment carving.

## Overview

MySQL Recovery Tool performs offline analysis on MySQL InnoDB database files, disk partitions and disk image files. It parses InnoDB data page structures directly, reconstructs scattered fragments, and salvages table data without writing any changes to your source evidence.

All scanning operations run in **read-only mode** — your original database files, disk partitions and disk images remain untouched.

## Supported Versions

- MySQL 5.0
- MySQL 5.5
- MySQL 5.6
- MySQL 5.7
- MySQL 8.0
- MySQL 9.0

**Storage engine:** InnoDB

## Core Capabilities

- Recover data from corrupted InnoDB database files
- **Fragment carving**: extract and reassemble scattered InnoDB data pages from disk partitions or disk images
- Recover dropped tables (`DROP TABLE`)
- Restore data from truncated tables (`TRUNCATE TABLE`)
- Recover deleted rows (`DELETE` / `DELETE FROM`)
- Undo accidental `UPDATE` operations — restore original field values
- Preview recoverable table data before export
- **100% read-only scan**: source files will never be modified

## Use Cases

- InnoDB database file corruption
- Dropped database or dropped table without backup
- Truncated table recovery
- Accidental DELETE of records
- Accidental UPDATE overwrote wrong rows
- Data rescue from disk image copies when the original MySQL instance is unavailable

## How It Works

1. The tool scans InnoDB data files, disk partitions or disk images in read-only mode.
2. It locates and parses InnoDB data pages directly from raw disk or image structures.
3. Scattered fragments are reassembled into table records.
4. Recoverable tables and rows are displayed in a preview view.
5. Verified data can be exported after preview.

## Important Notice

This is an offline forensic analysis tool.

We do **not** write or modify the original database files, disk partitions or disk images during scanning. Always work on copies or disk images for evidence safety.

## Download

Get the latest Windows binary release on GitHub Releases.

> Pre-built Windows x64 zip package, contains the read-only MySQL InnoDB recovery client.

## Antivirus Note

> ⚠️ The Windows binary is protected with VMProtect for anti-tampering. Some antivirus software may incorrectly flag it as malware (false positive). This tool works in fully read-only mode and will not modify your database source files.

## Contact

For technical feedback, bug reports or feature requests, please open a GitHub issue.
