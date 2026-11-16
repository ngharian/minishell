# Minishell

## Description

Minishell is a Unix-like shell project implemented in C, designed to reproduce the behavior of a basic interactive command interpreter. The project focuses on parsing user input, managing processes, handling environment variables, and supporting essential shell features such as pipes, redirections, heredocs, and built-in commands.

This project was developed as part of the 42 curriculum and emphasizes low-level system programming, process management, signal handling, and command execution logic. It provides a strong foundation in how terminals, shells, and UNIX processes interact in real operating systems.

## Features

### Core Shell Features
- **Interactive command line**: Reads commands from the terminal using `readline`
- **Command parsing**: Splits input into commands and arguments while handling quotes and special syntax
- **Pipelines**: Executes multiple commands connected with `|`
- **Redirections**: Supports input/output redirection and file handling
- **Heredoc support**: Handles `<<` input redirection for multiline command input
- **Environment management**: Reads and updates environment variables
- **Process execution**: Runs external commands using `execve` and proper child process management
- **Signal handling**: Handles interactive and process-level signals safely

### Built-in Commands
- **echo**: Prints text with optional `-n` support
- **cd**: Changes the current working directory
- **pwd**: Prints the working directory
- **export**: Adds or updates environment variables
- **unset**: Removes environment variables
- **env**: Displays the current environment
- **exit**: Exits the shell with a status code

### Parsing and Execution Capabilities
- **Quote handling**: Manages single and double quotes in command strings
- **Variable expansion**: Expands environment variables inside input
- **Path lookup**: Searches executable binaries in the `PATH`
- **Command chaining**: Executes multiple commands in sequence with correct process flow
- **Error handling**: Detects invalid syntax, missing files, permission errors, and execution failures

## Technologies Used

- **Language**: C
- **Shell Interface**: GNU Readline
- **Utility Library**: Custom Libft implementation
- **Build System**: Makefile
- **Platform**: Linux / Unix-like systems
- **System Calls**: `fork`, `execve`, `pipe`, `wait`, `dup`, `open`, `signal`

## Prerequisites

- Linux operating system
- GCC compiler
- Make
- `readline` development library
- Libft implementation included in the project

## Installation

1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd minishell
   ```

2. Build the project:
   ```bash
   make
   ```

3. Run the shell:
   ```bash
   ./minishell
   ```


### Example Commands
```bash
pwd
ls -la
echo "Hello, world!"
export TEST=42
cd /tmp
env
cat file.txt | grep hello
echo hi > output.txt
cat << EOF
hello
EOF
exit 0
```

### Shell Behavior
The shell supports standard command-line interaction similar to bash for a subset of useful features, including:
- built-ins
- pipes
- redirections
- environment variables
- error reporting and process status handling

## Key Algorithms & Concepts

- **Lexing and Parsing**: Breaking input text into tokens and command structures
- **Command Tree / Command List Management**: Organizing executable commands and redirections
- **Environment Expansion**: Replacing variables like `$HOME` and `$PATH`
- **Process Creation**: Using `fork()` and `execve()` to run external programs
- **Pipe Management**: Connecting command output and input between processes
- **Redirection Handling**: Opening files and redirecting standard streams
- **Signal Handling**: Managing `SIGINT` and interactive shell behavior
- **Memory Management**: Cleaning allocated structures and preventing leaks

## Learning Outcomes

This project demonstrates:
- Advanced C programming and memory management
- Unix process control and inter-process communication
- Shell parsing and execution model
- Signal handling in interactive programs
- Environment variable management
- Real-world knowledge of terminal and command-line interfaces
- Clean code organization and modular design in a system project
