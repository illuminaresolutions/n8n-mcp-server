# n8n MCP Server
[![smithery badge](https://smithery.ai/badge/@illuminaresolutions/n8n-mcp-server)](https://smithery.ai/server/@illuminaresolutions/n8n-mcp-server)

An MCP server that provides access to n8n workflows, executions, credentials, and more through the Model Context Protocol. This allows Large Language Models (LLMs) to interact with n8n instances in a secure and standardized way.

## Features

- Connect to any n8n instance through its REST API
- List all workflows in your n8n instance
- View workflow details including nodes, connections, and settings
- Execute workflows and monitor their status
- Manage users, credentials, tags, and projects
- Secure access through n8n API key authentication

## Installation

### Installing via Smithery

To install n8n MCP Server for Claude Desktop automatically via [Smithery](https://smithery.ai/server/@illuminaresolutions/n8n-mcp-server):

```bash
npx -y @smithery/cli install @illuminaresolutions/n8n-mcp-server --client claude
```

### Prerequisites

- Node.js 16 or higher
- An n8n instance with API access
- n8n API key with appropriate permissions

### Using npm

```bash
npm install n8n-mcp-server
```

### Using the Source Code

```bash
# Clone the repository
git clone https://github.com/illuminaresolutions/n8n-mcp-server.git

# Navigate to the project directory
cd n8n-mcp-server

# Install dependencies
npm install

# Build the project
npm run build
```

## Configuration

Create a `.env` file in your project root with the following variables:

```env
N8N_HOST=https://your-n8n-instance.com
N8N_API_KEY=your-api-key-here
```

## Usage

### With Claude Desktop

1. Install [Claude Desktop](https://claude.ai/download)

2. Open your Claude Desktop configuration at:
   - macOS: `~/Library/Application Support/Claude/claude_desktop_config.json`
   - Windows: `%APPDATA%\Claude\claude_desktop_config.json`

3. Add the n8n MCP server configuration:

```json
{
  "mcpServers": {
    "n8n": {
      "command": "npx",
      "args": ["-y", "n8n-mcp-server"],
      "env": {
        "N8N_HOST": "https://your-n8n-instance.com",
        "N8N_API_KEY": "your-api-key-here"
      }
    }
  }
}
```

4. Restart Claude Desktop

### With Cline

1. Install [Cline](https://github.com/cline/cline)

2. Configure the n8n MCP server in Cline:

```bash
cline config add-server n8n npx -y n8n-mcp-server
```

3. Set the required environment variables:

```bash
cline config set-env n8n N8N_HOST https://your-n8n-instance.com
cline config set-env n8n N8N_API_KEY your-api-key-here
```

## Current Features

- List all workflows in your n8n instance
- View detailed workflow information
- Check workflow status
- Manage workflow execution

## Roadmap

The following features are planned for future releases:

### Workflow Management
- Retrieve a workflow by its ID
- Update an existing workflow
- Delete a workflow by its ID
- Activate a workflow by its ID
- Deactivate a workflow by its ID

### Execution Management
- Retrieve all executions
- Retrieve an execution by its ID
- Delete an execution by its ID

### User Management
- Retrieve all users
- Create multiple users
- Get user by ID/Email
- Delete a user

### Credential Management
- Create a credential
- Delete credential by ID
- Show credential data schema

### Tag Management
- Create a tag
- Retrieve all tags
- Retrieve a tag
- Delete a tag
- Update a tag

### Project Management
- Create a project
- Retrieve projects
- Delete a project
- Update a project

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Security

Remember to keep your n8n API key secure and never commit it to version control. Always use environment variables or secure configuration management for sensitive credentials.

## Support

If you encounter any issues or have questions, please file an issue on the GitHub repository.
