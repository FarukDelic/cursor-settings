# AI-Driven Product Documentation Workflow

This guide walks you through creating comprehensive product documentation using AI-powered tools and structured thinking processes.

## Terminology

- **PRD** - Product Requirements Document
- **SAS** - Solution Architecture Specification
- **TSD** - Technical Specification Document

## Step 1: Create Product Requirements Document (PRD)

### Setting Up Your Documentation Environment

1. Open Cursor and create a `documentation` folder in your project
2. Open the Chat interface and provide your project requirements using the structured prompt below

**Prompt Template:**

```
<requirements>
[THIS IS A PLACEHOLDER - WRITE YOUR REQUIREMENTS HERE]
</requirements>

<technical_instructions>
[THIS IS A PLACEHOLDER - WRITE YOUR TECHNICAL INSTRUCTIONS HERE]
</technical_instructions>

<instructions>
Use MCP Product Documentation to generate a comprehensive PRD (Product Requirements Document) based on the requirements and technical instructions provided above. Make sure to use the MCP sequential thinking first.

Follow the structure form the context provided from the MCP Product Documentation
</instructions>
```

**Tips for Writing Requirements:**

- Be specific about user needs and business objectives
- Include functional and non-functional requirements
- Specify target audience and use cases
- Mention any constraints or limitations

## Step 2: Review and Refine PRD

### Quality Assurance Process

Once your initial PRD is generated, conduct a thorough review to ensure accuracy and completeness.

**Prompt Template:**

```
<ATTACH THE PRD DOCUMENT>

<instructions>
Use MCP Product Documentation to review PRD based on the requirements and technical instructions provided above. Make sure that you create a questions.md file in documentation folder if you have any questions for me. Make sure to use the MCP sequential thinking first.

</instructions>
```

**Expected Outcome:**

- A refined PRD document
- A `questions.md` file containing clarification requests
- Identification of any gaps or ambiguities

## Step 3: Address Clarification Questions

### Minimizing AI Assumptions

Review the generated `questions.md` file and provide detailed answers to eliminate assumptions and reduce potential inaccuracies.

**Best Practices:**

- Answer all questions thoroughly
- Provide examples where applicable
- Clarify any ambiguous requirements
- Update the PRD based on your responses

## Step 4: Generate Solution Architecture Specification (SAS)

# NEW GUIDE IN solution-architecture-md file

## Step 5: Generate Development Tasks

### Breaking Down Implementation

Transform your documentation into actionable development tasks.

**Prompt Template:**

```
<ATTACH THE REVIEWED PRD DOCUMENT>
<ATTACH THE REVIEWED SAS DOCUMENT>

<instructions>
Use MCP Product Documentation to generate tasks based on the PRD and SAS document. Make sure to use the MCP sequential thinking first.
</instructions>
```

## Step 6: Create Detailed Technical Descriptions for JIRA Tasks

### Enhancing Tasks with Technical Context

Transform your generated tasks into comprehensive technical specifications by leveraging JIRA integration and context-specific documentation.

**Prompt Template:**

```
<instructions>
1. Use MCP JIRA to retrieve the specific task details from JIRA ticket: [JIRA_TICKET_ID]
2. Use MCP Context7 to gather technical documentation for: [TECHNOLOGY_STACK - e.g., React, Node.js, PostgreSQL]
3. Create a detailed technical description for executing this JIRA task that includes:
   - Step-by-step implementation approach
   - Code examples and snippets
   - Testing strategies
   - Acceptance criteria
   - Potential challenges and solutions
4. Attach the **PRD** and **SAS** document

Make sure to use MCP Sequential Thinking to break down the technical implementation process.
</instructions>
```
