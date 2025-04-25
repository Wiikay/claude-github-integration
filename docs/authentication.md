# Authentication with github-mcp-server

## How Authentication Works

The github-mcp-server uses GitHub's API to authenticate and perform operations on your behalf. The authentication process is managed securely between your Claude interface and GitHub.

## Authentication Methods

Authentication typically happens through one of these methods:

1. **GitHub Access Token**: A personal access token with appropriate permissions
2. **OAuth Authentication**: Authentication via OAuth flow
3. **Session-based Authentication**: Using your active GitHub session

The specific method used depends on how the github-mcp-server was configured in your Claude interface.

## Security Considerations

- Your GitHub credentials are never exposed in Claude conversations
- All API calls are made directly from the github-mcp-server to GitHub's API
- Claude only receives the results of these operations, not your authentication details
- Communications between Claude and the github-mcp-server are encrypted

## Permission Scopes

Depending on the operations you want to perform, the github-mcp-server may need different permission scopes:

| Operation | Required Permission |
|-----------|---------------------|
| Reading public repositories | `public_repo` |
| Reading private repositories | `repo` |
| Creating/updating files | `repo` |
| Managing issues | `repo` |
| Managing pull requests | `repo` |

## Best Practices

1. **Least Privilege**: Grant only the permissions needed for your use case
2. **Regular Review**: Periodically review the permissions granted to github-mcp-server
3. **Separate Tokens**: Use different tokens for different projects if possible
4. **Token Rotation**: Regularly rotate access tokens used for authentication
5. **Audit Actions**: Keep track of operations performed via the integration

## Example Configuration

If you were to configure github-mcp-server manually, a configuration might look something like this:

```json
{
  "mcp": {
    "servers": [
      {
        "name": "github-mcp-server",
        "version": "0.6.2",
        "config": {
          "authentication": {
            "type": "github_token",
            "token_env_var": "GITHUB_TOKEN"
          },
          "permissions": {
            "repositories": "read-write",
            "issues": "read-write",
            "pull_requests": "read-write"
          }
        }
      }
    ]
  }
}
```

However, in most cases, this configuration is handled for you when the MCP server is installed in your Claude interface.

## Troubleshooting Authentication Issues

If you encounter authentication problems:

1. **Check that github-mcp-server is properly installed** in your Claude interface
2. **Verify you have appropriate permissions** for the repositories you're accessing
3. **For organization repositories**, ensure you have the necessary organization access
4. **For private repositories**, confirm your authentication includes the `repo` scope

If you continue to experience authentication issues, you may need to check with Anthropic support regarding your specific MCP server configuration.
