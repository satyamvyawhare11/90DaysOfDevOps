# Day 20 – Log Analyzer & Report Generator

## Script Created

log_analyzer.sh

### What It Does

- Accepts a log file as input
- Validates file existence
- Counts ERROR and Failed entries
- Prints CRITICAL events with line numbers
- Finds top 5 most common ERROR messages
- Generates report: log_report_<date>.txt
- Moves processed log to archive/

Example:
./log_analyzer.sh sample_log.log

---

## Tools Used

- grep
- awk
- sort
- uniq
- wc
- date
- mv

---

## Sample Report Content

- Date of analysis
- Log file name
- Total lines
- Total error count
- Top 5 errors
- Critical events

---

## What I Learned

- Parsing logs efficiently
- Using pipelines for data processing
- Automating reporting
- Writing production-style scripts
- Thinking like a system administrator
