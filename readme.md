# Event-Driven Logger in Node.js

This is a Node.js application that demonstrates event-driven programming. It logs messages and system memory usage to a file (`eventlog.txt`) using custom events.

---

## Features

- **Event-Driven Logging**: Uses custom events to log messages.
- **Real-Time Memory Monitoring**: Logs system memory usage periodically.
- **Persistent Logs**: Stores all logs in a file for future analysis.

---

## Requirements

- **Node.js** (version 12 or higher)

---

## Installation

1. Clone this repository:
   ```bash
   git clone <repository-url>
   ```
2. Navigate to the project directory:
   ```bash
   cd <project-folder>
   ```
3. Install dependencies (if any):
   ```bash
   npm install
   ```

---

## Usage

1. Run the application:
   ```bash
   node index.js
   ```
2. The application will:
   - Log "Application started" and "Application event occurred" to `eventlog.txt`.
   - Periodically log the system's memory usage (every 3 seconds) to the same file.

---

## How It Works

### Core Components:

- **Logger Class**: Extends the `EventEmitter` class to emit and listen for custom events.
- **logToFile Listener**: Writes log messages to `eventlog.txt` with a timestamp.
- **Memory Usage Monitor**: Logs the current memory usage at regular intervals using the `os` module.

### Log File Example (`eventlog.txt`):

```
2024-12-26T14:30:00.000Z - Application started
2024-12-26T14:30:00.100Z - Application event occurred
2024-12-26T14:30:03.000Z - current memory usage :47.85
2024-12-26T14:30:06.000Z - current memory usage :48.23
2024-12-26T14:30:09.000Z - current memory usage :48.12
```

---

## Code Overview

### Main Components:

1. **Logger Class**:

   - Emits a `message` event.
   - Used to log messages.

2. **logToFile Listener**:

   - Appends log messages to `eventlog.txt`.
   - Includes a timestamp for each log entry.

3. **Memory Usage Monitor**:
   - Calculates memory usage as a percentage.
   - Logs the memory usage every 3 seconds.

### Modules Used:

- **`fs`**: For writing to the log file.
- **`os`**: For retrieving system memory usage.
- **`events`**: For creating and handling custom events.

---

## Potential Enhancements

- **Error Handling**: Handle file write errors more gracefully.
- **Log Rotation**: Create new log files daily or based on file size.
- **Dynamic Intervals**: Allow configuration of memory logging intervals.
- **Log Levels**: Add support for log levels like `info`, `warn`, and `error`.

---

## Author

[Mohammad bin mazi]

Feel free to contribute or suggest improvements!

this project created under the guidance of
expert node.js teacher
