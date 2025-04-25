# Getting Started with Claude GitHub Integration

## Prerequisites

Before you can use Claude with GitHub, ensure you have:

1. **Claude Pro Subscription**: Required to access MCP servers
2. **GitHub Account**: With repositories you want to access
3. **github-mcp-server**: Installed in your Claude interface

## Checking MCP Server Installation

To verify the github-mcp-server is installed:

1. Open Claude's interface
2. Look for the Model Context Protocol panel (typically found in settings or in the sidebar)
3. Check that "github-mcp-server" is listed under installed MCP servers
4. Verify the version is 0.6.2 or higher

![MCP Servers Panel Example](../images/mcp-panel-example.png)

## Your First GitHub Operation

Try a simple operation to test the integration:

```
Claude, can you check what files are in my repository [repository-name]?
```

Claude should use the github-mcp-server to access your repository and list the files.

## Common Operations

### Reading File Contents

```
Claude, please show me the contents of the file [filename] in my [repository-name] repository.
```

### Creating a New File

```
Claude, create a new file called [filename] in my [repository-name] repository with the following content:

[Your content here]
```

### Updating an Existing File

```
Claude, update the file [filename] in my [repository-name] repository. Replace its contents with:

[New content]
```

## Troubleshooting

If you encounter issues:

1. Verify the github-mcp-server is properly installed
2. Check that you have appropriate permissions for the repositories you're trying to access
3. Ensure your prompts to Claude are clear and specific
4. For persistent issues, check the [Troubleshooting](../troubleshooting.md) guide
