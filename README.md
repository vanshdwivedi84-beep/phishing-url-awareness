# EWB Phishing URL Awareness Checker

**Author:** Vansh Dwivedi  
**Project type:** Beginner cybersecurity mini project  
**Language:** Python 3.10+

## Overview

Phishing is a social-engineering trick in which someone uses a fake link or message to persuade a person to reveal sensitive information. This command-line project checks URL text for six selected warning signs and prints findings that encourage the user to review a link carefully.

The program analyses text only. It never opens, visits, scans, or sends a URL anywhere.

## Features

- Detects an `@` symbol in the URL.
- Flags URLs longer than 100 characters.
- Flags an IPv4-style IP address used as the hostname.
- Flags hostnames containing five or more dot-separated segments.
- Flags a punycode marker (`xn--`) in the hostname.
- Flags the HTTP scheme.
- Handles blank and malformed input without crashing.
- Repeats checks until the user enters `q`, `quit`, or `exit`.
- Displays a review reminder when warning signs are detected.

## Requirements

- Python 3.10 or later.
- No third-party packages are needed. The project uses Python standard-library modules (`re` and `urllib.parse`).

## Project structure

```text
phishing-url-awareness/
├── phishing_checker.py
├── README.md
├── requirements.txt
├── tests/
│   └── test_samples.md
└── screenshots/
    ├── sample_run.png       # Add your real screenshot
    └── test_results.png     # Add your real screenshot
```

## How to run

1. Open a terminal in this project folder.
2. Check that Python is installed:

   ```bash
   python --version
   ```

   On Windows, if needed, use `py --version`. On macOS/Linux, use `python3 --version`.

3. Run the program:

   ```bash
   python phishing_checker.py
   ```

   On macOS/Linux, use `python3 phishing_checker.py`.

4. Enter one of the sample strings listed in `tests/test_samples.md`. Enter `q` to quit.

## Example

Input:

```text
http://192.0.2.10/account
```

Expected findings:

```text
- Uses an IP address instead of a familiar domain.
- Uses HTTP. HTTPS alone does not prove trust.

REVIEW CAREFULLY: 2 warning sign(s) found.
```

## Testing

Five sample cases from the project workbook are documented in [`tests/test_samples.md`](tests/test_samples.md). Run them locally and verify the actual output. Do not claim a test passed unless you have run it and confirmed the result.

## Screenshots

After running the program on your own computer, save these two genuine screenshots in the `screenshots/` folder:

- `sample_run.png`: terminal showing the command, one sample input, and its output.
- `test_results.png`: your completed `tests/test_samples.md` open in VS Code, or terminal evidence of all five runs.

The screenshot files are intentionally not fabricated. Capture them on your own computer so they are authentic evidence of your work.

## Improvements

1. **Repeat-check loop:** the program can inspect multiple sample URLs in one session and exits when the user enters `q`, `quit`, or `exit`. This avoids restarting the script for every test.
2. **Malformed-input handling:** URL parsing is wrapped in `try/except ValueError`, so malformed text such as `http://[bad` produces a clear message instead of terminating the program.
3. **Review summary:** when actual warning signs are detected, the program prints a `REVIEW CAREFULLY` summary and the number of findings.

## Limitations

This is a small educational awareness checker, not a complete phishing detector. It checks only six visible clues. It does not use threat-intelligence feeds, reputation services, DNS, machine learning, or malware scanning. A URL with no listed warning signs may still be dangerous, and a URL with warning signs may be legitimate. HTTPS alone does not prove that a website is trustworthy.

## Safety and ethical use

- Use only the reserved sample strings provided in the workbook for this assignment.
- Do not open suspicious links to test them.
- Do not collect passwords, OTPs, payment details, or other credentials.
- Do not scan or probe websites or networks without written permission.
- Never upload passwords, API keys, access tokens, or private information to GitHub.

## Author

Vansh Dwivedi  
Cybersecurity Internship Mini Project
