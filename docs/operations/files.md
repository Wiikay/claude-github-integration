# File Operations

## Available File Operations

Claude can perform the following file operations in GitHub repositories:

### Reading Files

```
Claude, show me the contents of file [filename] in my repository [repository-name].
```

This operation allows you to view the contents of any file in your GitHub repositories. Claude can display the file contents directly in your conversation.

### Creating Files

```
Claude, create a new file called [filename] in my repository [repository-name] with the following content:
[Your content here]
```

This operation creates a new file in your repository with the specified content. You can create any type of file, including:
- Code files (.js, .py, .java, etc.)
- Markdown documentation (.md)
- Configuration files (.json, .yaml, etc.)
- Text files (.txt)

### Updating Files

```
Claude, update the file [filename] in my repository [repository-name]. Change its content to:
[New content]
```

This operation allows you to modify existing files in your repository. When updating a file, Claude automatically retrieves the current content and makes the specified changes.

### Deleting Files

```
Claude, delete the file [filename] from my repository [repository-name].
```

This operation removes a file from your repository.

## Multiple File Operations

Claude can also perform operations on multiple files at once:

```
Claude, create the following files in my [repository-name] repository:
- README.md with content: [content]
- index.html with content: [content]
- styles.css with content: [content]
```

## Working with File Content

### Code Files

For code files, Claude can help with formatting, commenting, and ensuring correct syntax:

```
Claude, create a Python file named app.py in my [repository-name] repository with a Flask application skeleton and appropriate comments.
```

### Documentation Files

Claude excels at creating and updating documentation files:

```
Claude, update the README.md in my [repository-name] repository to include installation instructions, usage examples, and a license section.
```

## File Content Best Practices

1. **Specify the file extension** (.md, .py, .js, etc.) to ensure proper formatting
2. **For code files**, ask Claude to include comments for clarity
3. **For documentation**, request specific sections like Overview, Installation, Usage
4. **When updating files**, consider asking Claude to show the current content first

## Functions Used

Claude uses the following MCP functions for file operations:

- `get_file_contents`: For retrieving file content
- `create_or_update_file`: For creating new files or updating existing ones
- `push_files`: For creating or updating multiple files at once

## Example Conversation

**User**: Claude, can you create a new JavaScript file called utils.js in my project-x repository with utility functions for string manipulation?

**Claude**: I'd be happy to create that JavaScript file for you. What specific string manipulation utilities would you like me to include?

**User**: Please include functions for capitalizing first letters, reversing strings, and counting occurrences of a substring.

**Claude**: I'll create the utils.js file with those string manipulation functions. Let me prepare that for you.

[Claude uses MCP to create the file]

**Claude**: I've created the utils.js file in your project-x repository with the following string manipulation utility functions:
- `capitalizeFirstLetter(str)`: Capitalizes the first letter of a string
- `reverseString(str)`: Reverses a string
- `countOccurrences(str, substr)`: Counts occurrences of a substring in a string

Each function includes JSDoc comments explaining usage and parameters. Would you like me to show you the full content of the file?
