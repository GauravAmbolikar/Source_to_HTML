# Source_to_HTML

## 📌 Project Description

Source2HTML is a C-based source code parser that converts a C source file into an HTML file.

The generated HTML file can be opened in a web browser to display the source code with different colors for different types of tokens such as:

- Reserved keywords
- Preprocessor directives
- Header files
- Numeric constants
- Strings
- ASCII characters
- Single-line comments
- Multi-line comments

The project uses a state-event based parser architecture to identify and process different parts of the source code.

---

## 🎯 Objective

The main objective of this project is to:

1. Read a C source file character by character.
2. Identify different types of tokens.
3. Generate parser events for identified tokens.
4. Convert the parser events into HTML.
5. Apply CSS styles to different types of tokens.
6. Generate an HTML file that can be viewed in a web browser.

---

## 🏗️ Project Architecture

The project is divided into three main parts:

### 1. Parser

The parser reads the source file character by character and identifies different tokens.

It uses a State Machine consisting of different states such as:

- Idle
- Preprocessor Directive
- Header File
- Reserved Keyword
- Numeric Constant
- String
- ASCII Character
- Single-Line Comment
- Multi-Line Comment

When a token is completely identified, the parser generates an event.

### 2. Event System

The parser generates events such as:

- PEVENT_PREPROCESSOR_DIRECTIVE
- PEVENT_RESERVE_KEYWORD
- PEVENT_NUMERIC_CONSTANT
- PEVENT_STRING
- PEVENT_HEADER_FILE
- PEVENT_SINGLE_LINE_COMMENT
- PEVENT_MULTI_LINE_COMMENT
- PEVENT_ASCII_CHAR
- PEVENT_REGULAR_EXPRESSION
- PEVENT_EOF

These events are passed to the HTML conversion module.

### 3. HTML Converter

The HTML converter receives the parser events and generates the corresponding HTML output.

CSS classes are used to apply different colors to different types of source code elements.

---

## 🎨 Color Scheme

| Source Code Element | Color |
|----------------------|-------|
| Comments | Blue |
| Data Keywords | Green |
| Non-Data Keywords | Goldenrod |
| Preprocessor Directives | Purple |
| Header Files | Red |
| Strings | Magenta |
| Numeric Constants | Brown |
| ASCII Characters | Firebrick |

---

## 📂 Project Files

| File | Description |
|------|-------------|
| s2html_main.c | Main program and file handling |
| s2html_event.c | Parser state machine and event generation |
| s2html_event.h | Parser states, events, structures and function declarations |
| s2html_conv.c | Converts parser events into HTML |
| s2html_conv.h | HTML conversion declarations |
| styles.css | CSS styles used for syntax highlighting |
| test.c | Test source file |
| README.md | Project documentation |

---

## ⚙️ How the Project Works

The overall flow of the project is:

C Source File
      |
      ↓
Character Reading
      |
      ↓
Parser / State Machine
      |
      ↓
Parser Events
      |
      ↓
HTML Converter
      |
      ↓
HTML File
      |
      ↓
Web Browser

---

## 🔄 Parser Working

Initially, the parser is in the Idle State.

It reads the source file character by character.

Depending on the character encountered, it changes to an appropriate state.

For example:

    #       → Preprocessor State
    "       → String State
    '       → ASCII Character State
    /       → Comment Detection
    0-9     → Numeric Constant State
    a-z     → Reserved Keyword State

The parser continues collecting characters until the current token is complete.

After identifying the token, it generates an event and returns to the Idle state.

---

## 🛠️ Compilation

Compile the project using GCC:

    gcc s2html_main.c -o a.out

---

## ▶️ Running the Project

Run the executable by providing the C source file:

    ./a.out test.c

The program generates an HTML output file.

Example:

    test.c.html

Open the generated HTML file in a web browser to view the highlighted source code.

---

## 🧪 Example

### Input

    #include <stdio.h>

    int main()
    {
        int a = 10;

        // Print value
        printf("Value = %d", a);

        return 0;
    }

### Output

The generated HTML file displays the source code with different colors for:

- #include → Preprocessor directive
- stdio.h → Header file
- int → Reserved keyword
- 10 → Numeric constant
- "Value = %d" → String
- // Print value → Comment
- return → Reserved keyword

---

## 💻 Technologies Used

- C Programming
- File Handling
- State Machine
- Event-Based Parsing
- HTML
- CSS
- GCC
- Linux / WSL

---

## 📚 Concepts Used

This project provides practical implementation of:

- Structures
- Enumerations
- File Handling
- Character-by-character file parsing
- String handling
- Pointers
- Functions
- State machines
- Event-driven processing
- HTML generation
- CSS styling

---

## 🚀 Future Enhancements

Possible future improvements include:

- Support for more programming languages
- Improved handling of complex C syntax
- Better handling of escape sequences
- Line numbering support
- Improved HTML formatting
- Additional syntax highlighting
- Improved error handling

---

## 👨‍💻 Author

Gaurav Ambolikar

Electronics and Telecommunication Engineering