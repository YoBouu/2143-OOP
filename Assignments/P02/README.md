# Program 2 — Command-Line Args Parser

## Overview
Program 2 focuses on building a robust configuration layer for `imgtool`. Instead of hard-coding values, this component reads raw command-line tokens, validates them (including file extensions and value ranges), and packages the results into an `Args` object. This parser will be integrated with image processing logic in future assignments.

## Project Structure
- `07-P02/`
    - `src/main.cpp`: Driver file (calls parse and print).
    - `src/Args.h`: Class declaration with data members.
    - `src/Args.cpp`: Implementation of parsing and validation logic.
    - `docs/`: Design discussions regarding the factory pattern.

## Build Instructions
To compile the project from the root directory, use the following command:

```bash
g++ -std=c++17 -O2 -Wall -Wextra -pedantic src/main.cpp src/Args.cpp -o imgtool\
