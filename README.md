# Cursor Settings Configuration

This guide will help you configure Cursor with optimal settings and Model Context Protocol (MCP) servers for enhanced development experience.

## Step 1: Configure User Rules

### Setting Up User Rules

Navigate to **Cursor > Settings > Cursor Settings > Rules**

In the **USER RULES** section, add the following rules:

```
You write code that handles all edge cases and boundary conditions explicitly
You validate inputs at function entry points and fail fast with clear error messages
You use meaningful variable and function names that explain intent without comments
You keep functions small and focused on a single responsibility
You avoid deep nesting by using early returns and guard clauses
You use immutable data structures where possible to prevent unexpected mutations
You write defensive code that checks for null/undefined values before using them
You use proper error handling with try-catch blocks instead of ignoring exceptions
You avoid magic numbers and strings by using named constants
You refactor duplicate code into reusable functions immediately
You use consistent patterns for similar operations throughout your codebase
You test your code with real data scenarios, not just happy path examples
You use debugger and step through your code line by line when fixing bugs
You read error messages carefully and trace the full stack trace to root cause
You isolate problems by commenting out code sections to narrow down issues
You verify your assumptions by adding temporary logging to understand data flow
You check return values and handle failure cases explicitly
You use type annotations or assertions to catch type-related errors early
You avoid premature optimization and focus on correctness first
You clean up temporary debugging code before committing changes
Here are key qualities about how software engineers think about project structure when coding:
You organize code by feature/domain rather than by technical layer (controllers, models, views)
You separate business logic from framework-specific code to enable easier testing and changes
You create clear boundaries between modules with well-defined interfaces and contracts
You follow consistent folder naming conventions that other developers can predict and navigate
You group related files together and avoid spreading single features across multiple distant folders
You use dependency injection instead of hard-coding dependencies between components
You create abstraction layers for external services (databases, APIs) to enable mocking and swapping
You separate configuration from code using environment variables or config files
You organize imports logically - external libraries first, then internal modules in logical order
You create shared utility modules for common functions rather than duplicating code
You use consistent file naming patterns that indicate the file's purpose and content
You separate data models from business logic and keep them in dedicated modules
You create clear entry points for your application with minimal bootstrap code
You organize tests to mirror your source code structure for easy navigation
You use barrel exports (index files) to simplify imports from complex module structures
You avoid circular dependencies by carefully planning module relationships
You create middleware/interceptor layers for cross-cutting concerns like logging and authentication
You separate pure functions from stateful components to improve testability
You use consistent patterns for error handling and data validation across modules
You design your folder structure to scale - adding new features shouldn't require restructuring
You are using MCP Playwright to validate the given tasks (if possible to be validated in browser)
You are using MCP Process Image to validate the design (design screenshot + actual object screenshot)
You are using MCP Sequential Thinking for each task breaking it into meaningful steps.
You are using MCP Context7 for the specific technology version related tasks
You are using MCP Product Documentation for the PRD, SAS, TSD and Task generation
```

## Step 2: Configure MCP Servers

### Setting Up Standard MCP Servers

Navigate to **Cursor > Settings > Cursor Settings > Tools & Integrations** and click **New MCP Server**

Use the following MCP configuration:

```json
{
  "mcpServers": {
    "context7-mcp": {
      "command": "npx",
      "args": [
        "-y",
        "@smithery/cli@latest",
        "run",
        "@upstash/context7-mcp",
        "--key",
        "c93688da-519c-4d9d-b73a-d1ac05098cf7"
      ]
    },
    "sequential-thinking": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-sequential-thinking"]
    },
    "playwright": {
      "command": "npx",
      "args": ["-y", "@executeautomation/playwright-mcp-server"]
    },
    "Figma": {
      "url": "http://127.0.0.1:3845/sse"
    }
  }
}
```

### Setting Up Symphony Custom MCP Servers

**1. MCP Product Documentation**

Follow the setup instructions at:

```
https://github.com/symphonygroup/mcp-product-documentation
```

## Step 3: Configure Documentation Indexing

### Setting Up the Docs Feature

The **Docs** feature enables you to crawl and index custom resources and developer documentation, providing your Cursor agent with context-specific knowledge about the technologies you're working with.

**Instructions:**

1. Navigate to **Cursor > Settings > Cursor Settings > Indexing & Docs**
2. In the **Docs** section, click **+ Add Docs**
3. Enter the documentation URL for your technology (e.g., `https://react.dev/`)
4. Provide a descriptive name (e.g., "React Docs") and click **Confirm**
