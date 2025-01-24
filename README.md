# LeetCode Fetcher Extension

The **LeetCode Fetcher** is a Chrome extension that simplifies the process of fetching test cases and generating solution files for LeetCode problems. With this extension, you can easily extract test cases directly from a LeetCode problem page and automatically generate Python (`.py`) or C++ (`.cpp`) solution files. Additionally, you can run your solution files with the provided `test.py` script and use VS Code tasks to test them.

---

## Features

- Automatically detects the LeetCode problem URL.
- Prompts you to select a programming language (`cpp` or `py`) for the solution file.
- Fetches test cases and stores them in a `test_cases_named.json` file.
- Generates a boilerplate solution file in your chosen language.
- Allows testing of the solution using predefined test cases through the `test.py` script.

---

## Installation

### 1. Clone or Download the Repository
Start by cloning or downloading the repository to your local machine.

### 2. Install the Chrome Extension
1. Open **Chrome** and go to `chrome://extensions/`.
2. Enable **Developer Mode** by toggling the switch at the top-right corner.
3. Click **Load unpacked** and select the folder where the extension files are located.

### 3. Set Up the API Server
1. Ensure you have **Python** installed on your machine.
2. Install the required Python packages by running:
   ```bash
   pip install flask cloudscraper beautifulsoup4
   ```
3. Start the Flask server by running the following command in the terminal:
   ```bash
   python app.py
   ```
4. The server will be available at `http://127.0.0.1:5000`.

---

## Usage

### 1. Running the Extension
1. Open any **LeetCode problem page** in your Chrome browser.
2. Click on the **LeetCode Fetcher** extension icon in the Chrome toolbar.
3. Choose your desired programming language (either `cpp` or `py`) when prompted.
4. The extension will generate the test cases and solution files in the default directory.

### 2. Folder Structure
The generated files will be organized under a folder called `leetcode` (or another name if you specify it in `fetch.py`). The structure will look like this:
```
/leetcode/
    ├── two-sum/                  # Example folder for the "Two Sum" problem
    │   ├── test_cases_named.json  # JSON file containing test cases
    │   ├── solution.py           # Python solution file
    │   ├── solution.cpp          # C++ solution file
    ├── test.py                   # Script to test the solution files
    └── .vscode/
        └── tasks.json            # VS Code task configuration
```

### Testing Your Solution File

#### Prerequisites
1. Place the `test.py` script (provided in this repository) inside the `leetcode` folder.
2. Create a `.vscode` folder inside the `leetcode` folder and add the provided `tasks.json` file there.

#### Running the Test
1. Open **Visual Studio Code** (VS Code).
2. Open the solution file you want to test (e.g., `solution.py` or `solution.cpp`).
3. Press **Ctrl+Shift+P** (or **Cmd+Shift+P** on Mac) to open the Command Palette.
4. Select **Tasks: Run Task**.
5. Choose **Test Current Solution** from the task list.
6. The test results will be shown in the **VS Code terminal**.

---

### Important Notes
1. **Folder Setup**: Make sure the `leetcode` folder exists at the specified path. If you change the folder name, update it in the `fetch.py` script.
2. **tasks.json**: This file is used to configure VS Code tasks that run the `test.py` script with the selected solution file.
3. **Language Selection**: When using the extension, ensure you select the correct language (either `cpp` or `py`) when prompted.

---

With the **LeetCode Fetcher** extension, you can easily fetch test cases, generate solution files, and run tests in your preferred language, making it easier to solve LeetCode problems.
