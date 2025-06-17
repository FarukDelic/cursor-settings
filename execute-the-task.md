# JIRA Task Execution Workflow

This guide provides a comprehensive approach to executing development tasks from JIRA using AI-powered tools and automated validation processes.

## Prerequisites

Before starting, ensure you have:

- Cursor IDE with MCP servers configured
- JIRA access with appropriate permissions
- MCP Playwright server for browser automation
- MCP Process Image for visual validation (frontend tasks)
- MCP Sequential Thinking for task breakdown

## Step 1: Configure MCP JIRA Integration

### Setting Up JIRA Connection

Configure the MCP JIRA integration to enable seamless task management. There are multiple connection methods available:

**Recommended Method: Zapier Integration**

- Follow the detailed setup guide: [JIRA MCP Setup Tutorial](https://www.youtube.com/watch?v=tFFsX97HzEk)
- Ensure your JIRA instance has proper API access configured
- Test the connection by fetching a sample ticket

**Alternative Methods:**

- Direct API integration using JIRA tokens
- OAuth-based authentication for enterprise environments

## Step 2: Execute Backend Development Tasks

### Backend Task Execution Template

Use this structured prompt for backend development tasks:

```
<task>
You are tasked to execute the Jira task in the current codebase. Make sure to follow the JIRA description for the technical instructions. Use sequential thinking MCP server to break the task into smaller steps. Write the code and validate the code with MCP Playwright (if possible).
</task>

<steps>
1. Get the JIRA ticket informations [paste a link of the ticket]
2. Execute the code
3. Validate the code using MCP Playwright (if possible)
4. Respond with Task Complete and ask human to review the code.
5. Make the Jira ticket status complete.
</steps>
```

### Backend Task Best Practices

- **Code Quality**: Follow established coding standards and patterns
- **Testing**: Include unit tests and integration tests where applicable
- **Documentation**: Update relevant documentation and code comments
- **Error Handling**: Implement proper error handling and logging
- **Performance**: Consider performance implications and optimize if needed

## Step 3: Execute Frontend Development Tasks

### Frontend Task Execution Template

Use this comprehensive prompt for frontend component development:

```
<inputs>
- A screenshot of a Figma component design (Image A) is provided. / [or use the MCP Figma to get the selection]
- Your task is to develop a matching [PROVIDE A FRAMEWORK NAME AND VERSION] component.
- After implementation, use MCP Playwright to render the component in a browser and take a screenshot (Image B). Then use MCP image comparison to validate visual parity between Image A and B.
- Fix any difference between Image A and Image B.
</inputs>

<objective>
1. Recreate the component shown in the Figma screenshot using [FRAMEWORK] + [STYLING SYSTEM].
2. Ensure **pixel-perfect visual match** to the Figma design by comparing the two images (Image A and MCP-generated Image B).
3. Leverage design tokens (fonts, spacing, colors) which are already imported from Figma as CSS/SCSS variables or utility classes.
</objective>

<implementation_requirements>
- Framework: [PROVIDE A FRAMEWORK NAME AND VERSION]
- Styling: [PROVIDE ALL THE STYLING GUIDELINE AND CONFIGURATIONS (tailwind.config or other configuration files)]
- Design tokens: [Use pre-defined variables (e.g. `text-primary`, `bg-surface`, `font-body`, etc.)]

<component_api>
Your component **must support the following attributes** as inputs or bindings:

- `@Input() variant`: e.g. `'primary' | 'secondary' | 'primary-stroke'`
- `@Input() disabled`: boolean
- `@Input() leftIcon`: boolean (optional)
- `@Input() rightIcon`: boolean (optional)
- `@Input() link`: string (optional)
- Accessibility: Use semantic HTML and ARIA roles where applicable.
</component_api>

<output_files>
- `[component-name].component.ts`
- `[component-name].component.html`
- Tailwind utility classes used inline or extracted into `[component-name].component.tailwind.css` if needed.
</output_files>

<post_generation_steps>
1. Use MCP Playwright to launch and screenshot the rendered component.
2. Run MCP PROCESS IMAGE for image comparison between:
   - 📥 Figma Screenshot (Image A)
   - 📤 Rendered Output (Image B)
3. Fix any **visual diffs**, then refine the implementation to minimize differences and repeat validation.
</post_generation_steps>
```
