# Using Plain Text Files (`.txt`)

## Basic Premise

A diagnostic computer has collected rows of numerical data. Each line of the input file represents one set of readings.

Create a Python program that reads the provided text file one line at a time, processes the numbers on each line, and produces a diagnostic checksum.

For each line:

1. Remove unnecessary whitespace.
2. Separate the numbers.
3. Convert the values into integers.
4. Find the largest and smallest value.
5. Subtract the smallest value from the largest value.
6. Add that difference to a running checksum.
7. Write the difference to `checksum_results.txt`.

After every line has been processed, write the final checksum at the bottom of the results file.

### Practice Input

Use `checksum_practice_input.txt` while developing your program:

```text
12 7 19 4
8 8 3 14
21 13 17 9
6 2 10 5
```

For the first line:

```text
12 7 19 4
```

The largest value is `19` and the smallest is `4`.

```text
19 - 4 = 15
```

The four line differences are:

```text

12  7 19  4 | Checksum = 15
 8  8  3 14 | Checksum = 11
21 13 17  9 | Checksum = 12
 6  2 10  5 | Checksum = 8
```

The final checksum is:

```text
15 + 11 + 12 + 8 = 46
```

Therefore, `checksum_results.txt` should contain:

```text
15
11
12
8
Checksum: 46
```

Once your program works with the practice file, change it to process the provided `checksum_input.txt` file.

## Basic File Structure

Your starter folder will contain:

```text
basic/
├── main.py
├── checksum_practice_input.txt
└── checksum_input.txt
```

After running the finished program, it should also contain `checksum_results.txt`.

## Basic Requirements

* [ ] Open the provided input file in read mode and process the file one line at a time.
* [ ] Remove unnecessary whitespace, separate the numbers on each line, and convert the values into integers.
* [ ] Find the largest and smallest value on each line and calculate their difference.
* [ ] Maintain a running checksum by adding together all of the calculated differences.
* [ ] Create or overwrite `checksum_results.txt` and write each line's difference on its own line.
* [ ] Write the final checksum at the bottom of `checksum_results.txt` using the format `Checksum: number`.
* [ ] Verify your algorithm using `checksum_practice_input.txt`, then use the same algorithm to process the full `checksum_input.txt` file.

> Fully completing the Basic Requirements earns **16/20 marks, or 80%**.

## Basic Assessment — 16 Marks

| Assessment Item | Criteria | Marks |
|---|---|---:|
| Reading the File | Opens the provided text file and processes its contents line by line. | 2 |
| Processing Each Line | Correctly cleans, separates, and converts the values on each line into integers. | 3 |
| Calculating Differences | Correctly finds the largest and smallest values and calculates the difference for every line. | 4 |
| Calculating the Checksum | Correctly maintains a running total of all calculated differences. | 3 |
| Writing Results | Creates `checksum_results.txt` and writes every calculated difference on its own line. | 2 |
| Final Checksum | Writes the correctly calculated final checksum at the bottom of the results file. | 2 |
|  | **Total** | **16** |

## Advanced Premise

Extend your Basic program so that it can process a text file selected by the user rather than always using a predetermined filename.

The program should ask the user which file they want to process, safely open that file, validate its contents, and create a results file based on the selected filename.

You should be able to begin by copying your completed Basic `main.py` into the Advanced folder and modifying it.

For example, if the user enters

```text
sensor_data.txt
```

the program should read `sensor_data.txt` and create `sensor_data_results.txt`.


The checksum algorithm itself should remain the same.

## Advanced File Structure

Your starter folder will contain:

```text
advanced/
├── main.py
├── checksum_practice_input.txt
├── checksum_input.txt
└── sensor_data.txt
```

## Advanced Requirements

* [ ] Use `input()` to ask the user for the name of the `.txt` file they want to process.
* [ ] Use the same checksum algorithm from the Basic activity to process the selected file.
* [ ] Automatically create an output filename based on the input filename, such as `sensor_data_results.txt`.
* [ ] Validate each line before processing it so that non-numeric data is not treated as a valid row of readings.
* [ ] Use error handling so problems such as a missing file or invalid numeric data do not cause the program to crash.
* [ ] When invalid input or a file error occurs, clearly explain the problem and allow the user to correct it.

## Advanced Assessment — 4 Marks

| Assessment Item | Criteria | Marks |
|---|---|---:|
| User-Selected File | Accepts a filename from the user and correctly processes the selected text file. | 1 |
| Dynamic Output File | Creates an appropriately named results file based on the selected input filename. | 1 |
| Input Validation | Detects invalid rows instead of attempting to process non-numeric data. | 1 |
| Error Handling | Handles missing files and invalid data without crashing and allows the user to correct the problem. | 1 |
|  | **Total** | **4** |