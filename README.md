# SheetJS Practice Canvas

A web-based canvas to learn and practice [SheetJS](https://sheetjs.com/) for manipulating Excel files in JavaScript.

![SheetJS Practice Canvas](https://github.com/user-attachments/assets/788decfa-ff1c-4ce6-a187-cc539f6cf4ab)

## Features

- **Code Editor**: A full-featured code editor (powered by CodeMirror) on the left side with syntax highlighting, line numbers, and auto-closing brackets
- **XLSX File Viewer**: Upload and view Excel files (.xlsx, .xls, .csv) on the top right with sheet tab navigation
- **Output Area**: View console output and execution results on the bottom right
- **Execution Controls**:
  - **Reset**: Reset the code to the default template
  - **Execute**: Run your JavaScript code (also supports `Ctrl+Enter` keyboard shortcut)
  - **Pause Execute**: Pause/Resume code execution

## Getting Started

1. Open `index.html` in your web browser
2. Upload an XLSX file by clicking or dragging a file into the XLSX File Viewer area
3. Write your SheetJS code in the Code Editor
4. Press `Ctrl+Enter` or click the Execute button to run your code
5. View the output in the Output area

## Usage

The canvas provides access to:
- `workbook` - The loaded XLSX workbook object (available after uploading a file)
- `XLSX` - The SheetJS library for manipulating Excel files
- `console` - Custom console for logging output

### Example Code

```javascript
// List all sheet names from the loaded workbook
if (workbook) {
    console.log('Sheet names:', workbook.SheetNames);
    
    // Get the first sheet
    const worksheet = workbook.Sheets[workbook.SheetNames[0]];
    
    // Convert to JSON
    const data = XLSX.utils.sheet_to_json(worksheet);
    console.log('Data:', data);
}

// Create a new workbook programmatically
const wb = XLSX.utils.book_new();
const ws = XLSX.utils.aoa_to_sheet([
    ['Name', 'Age', 'City'],
    ['Alice', 30, 'New York'],
    ['Bob', 25, 'San Francisco']
]);
XLSX.utils.book_append_sheet(wb, ws, 'Sample');
```

## Technologies Used

- [SheetJS](https://sheetjs.com/) - Excel file manipulation library
- [CodeMirror](https://codemirror.net/) - In-browser code editor
- HTML5/CSS3/JavaScript

## License

MIT License
