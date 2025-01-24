# Leetcode CPH Project

## Outline

This VS Code extension enables users to retrieve test cases for LeetCode problems directly within their editor, run those test cases on their code, and receive feedback. It streamlines the process of gathering input and output test cases from LeetCode problem pages while offering a user-friendly interface for managing and executing them.

## Features

- **Test Cases Structured Storage**: It saves the retrievd test cases in a folder named `testCase` within the project directory.
- **Automatic Retrieval Of Test Cases**: It extracts test cases including both input and output from a given URL(Leetcode Problem).
- **Run On Test Cases**: It allows user to run the extracted test cases for their code and shows the result.

## Requirements

- VS Code (v1.60 or later)
- Node.js (v12.x or later)

## Installation

### Manually Install

1. Clone or download this repository:
    ```sh
    git clone https://github.com/harshit1joshi/Tinkering-open-project.git
    cd cph-leetcode
    ```
2. Install dependencies:
    ```sh
    npm install
    ```
3. Open the project folder in VS Code.
4. Press `F5` to launch the extension in a new Extension Development Host window.

## Usage

### Fetch Test Cases

1. Open a LeetCode problem URL in your VS Code editor.
2. From the Command Palette (`Ctrl + Shift + P`), run the `CPH: Fetch Test Cases` command.
3. Enter the LeetCode problem URL in the input prompt.
4. Wait for the extension to fetch the test cases and save them in the `testCase` folder.

### Run Test Cases

1. Once the test cases are fetched, you can run them against your code by running the `CPH: Run Test Cases` command from the Command Palette.
2. The extension will execute your code and compare its output with the expected results.

### Test Case Folder

The test cases will be saved in a `testCase` folder in your workspace directory. The folder will contain input/output files:

- **Input Files**: Each `input_X.txt` file contains the input values for the corresponding test case.
- **Output Files**: Each `output_X.txt` file contains the expected output for the corresponding test case.

## Commands

- `CPH: Fetch Test Cases`: Prompts the user for a LeetCode problem URL, fetches the test cases, and saves them in the `testCase` folder.
- `CPH: Run Test Cases`: Runs the fetched test cases against the user's code and shows the results.

## Keybindings and Menus

### Keybindings

- `Ctrl + Alt + F` (Windows/Linux) / `Cmd + Alt + F` (Mac): Fetch Test Cases.
- `Ctrl + Alt + R` (Windows/Linux) / `Cmd + Alt + R` (Mac): Run Test Cases.

These keybindings are available when the editor window is focused.

### Menus

The `CPH: Fetch Test Cases` and `CPH: Run Test Cases` commands are also available in the editor context menu when the file is a supported language (C++, Python, or JavaScript).


## Configuration

The extension supports the following settings to customize the fetch and run behavior:

```json
"cph.language.cpp.run": "g++ -o $fileNameWithoutExt $filename && .\\$fileNameWithoutExt",
"cph.language.python.run": "py $filename",
"cph.language.javascript.run": "node $filename"
```
