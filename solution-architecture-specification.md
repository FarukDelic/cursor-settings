# Solution Architecture Specification Workflow

This comprehensive guide walks you through creating a detailed Solution Architecture Specification (SAS) from client requirements using AI-powered tools and structured processes.

## Step 1: Extract Technical Requirements from Client Materials

### Objective

Transform raw client communications (transcripts, emails, documents) into structured technical requirements that serve as the foundation for your architecture specification.

### Setup Process

1. **Create Project Structure**

   ```
   project-root/
   ├── transcripts/           # Raw client materials
   ├── documentation/         # Generated documentation
   └── requirements/          # Processed requirements
   ```

2. **Organize Client Materials**
   - Create a `/transcripts` folder in your project root
   - Place all client transcripts, meeting notes, and requirement documents in this folder
   - Ensure files are in readable formats (`.txt`, `.md`, `.docx`, `.pdf`)

### Enhanced Prompt Template

```
<task>
You are provided with client materials in the @transcripts folder. Your objective is to create a comprehensive technical_requirements.md file that extracts, organizes, and structures all technical requirements from these materials.
</task>

<context>
The client materials may include:
- Meeting transcripts and recordings
- Email communications
- Requirement documents
- Feature requests
- Technical constraints
- Business objectives
</context>

<instructions>
1. Analyze all provided materials thoroughly
2. Extract functional and non-functional requirements
3. Identify technical constraints and preferences
4. Determine integration requirements and dependencies
5. Note performance, security, and scalability requirements
6. Organize requirements by priority and complexity
7. Create a structured technical_requirements.md file with the following sections:
   - Executive Summary
   - Functional Requirements
   - Non-Functional Requirements
   - Technical Constraints
   - Integration Requirements
   - Performance Criteria
   - Security Requirements
   - Assumptions and Dependencies
   - Success Criteria

Make sure to:
- Use clear, unambiguous language
- Include specific metrics where mentioned
- Highlight any conflicting or unclear requirements
- Add questions for clarification if needed
</instructions>

<output_format>
Create a well-structured technical_requirements.md file in the /requirements folder with proper markdown formatting, clear headings, and actionable requirement statements.
</output_format>
```

### Expected Deliverables

- **technical_requirements.md**: Structured technical requirements document
- **questions.md**: List of clarification questions (if any ambiguities exist)
- **assumptions.md**: Documented assumptions made during requirement extraction

## Step 2: Generate Detailed Architecture Documentation

### Objective

Create comprehensive architecture documentation that serves as the detailed foundation for the final SAS document.

### Prerequisites

- Completed `technical_requirements.md` file from Step 1
- MCP Product Documentation server configured
- Access to `get_prompt_prepare_sas` tool

### Prompt Template

```
<task>
You are tasked to prepare comprehensive architectural artifacts based on @technical_requirements.md that will serve as foundational inputs for creating a detailed Solution Architecture Specification (SAS).
</task>

<instructions>
1. Use MCP Product Documentation to get the detailed instructions
2. Call the **get_prompt_prepare_sas** tool to retrieve the complete prompt template
3. Follow the exact instructions provided by the MCP tool
4. Use MCP Sequential Thinking to break down complex architectural decisions
5. Ensure all deliverables match the specifications returned by the MCP tool
</instructions>

<mcp_tool_usage>
The MCP Product Documentation tool will provide you with:
- Complete task definition and context
- Exact deliverable specifications (5 specific files)
- Technical standards and diagram requirements
- Quality criteria and success metrics
- Detailed artifact specifications for each file

Follow the MCP-returned instructions exactly as provided.
</mcp_tool_usage>
```

### Expected Deliverables

The MCP Product Documentation tool will specify the exact deliverables required. Typically this includes:

- **SAS_detailed/** folder with comprehensive architectural artifacts
- All deliverables must meet the specifications returned by the MCP tool
- Follow the exact file structure and content requirements provided by the MCP prompt

## Step 3: Generate Final SAS Document

### Objective

Synthesize all detailed architecture documentation into a comprehensive, client-ready Solution Architecture Specification document.

### Prerequisites

- Completed `technical_requirements.md` from Step 1
- Complete `SAS_detailed/` folder from Step 2
- All architectural components documented and reviewed

### Prompt Template

```
<task>
You are tasked to create a comprehensive Solution Architecture Specification (SAS) based on @technical_requirements.md and @SAS_detailed folder that enables development teams to break down work into specific, well-defined tasks.
</task>

<instructions>
1. Use MCP Product Documentation to get the detailed instructions
2. Call the **get_prompt_create_sas** tool to retrieve the complete prompt template
3. Follow the exact instructions provided by the MCP tool
4. Use MCP Sequential Thinking to ensure logical flow and comprehensive coverage
5. Create the final SAS.md file in the /documentation folder
6. Ensure all deliverables match the specifications returned by the MCP tool
</instructions>

<mcp_tool_usage>
The MCP Product Documentation tool will provide you with:
- Complete task definition and context
- Detailed document structure (typically 10-15 pages with 14 mandatory sections)
- Specific content requirements for each section
- Quality criteria and success metrics
- Technical standards and formatting requirements
- Target audience specifications

Follow the MCP-returned instructions exactly as provided.
</mcp_tool_usage>
```

### Expected Deliverables

The MCP Product Documentation tool will specify the exact deliverables required. Typically this includes:

- **SAS.md**: Comprehensive Solution Architecture Specification document
- All deliverables must meet the specifications returned by the MCP tool
- Follow the exact structure and content requirements provided by the MCP prompt

## Quality Assurance Checklist

### Document Review Criteria

- [ ] All client requirements are addressed in the architecture
- [ ] Technical specifications are detailed and actionable
- [ ] Architecture decisions are well-justified and documented
- [ ] Security and compliance requirements are thoroughly covered
- [ ] Performance and scalability requirements are clearly defined
- [ ] Implementation roadmap is realistic and well-structured
- [ ] Risk assessment is comprehensive with mitigation strategies
- [ ] Documentation is professional and client-ready

### Technical Validation

- [ ] Architecture supports all functional requirements
- [ ] Non-functional requirements are adequately addressed
- [ ] Technology stack choices are appropriate and justified
- [ ] Integration patterns are well-defined and feasible
- [ ] Security architecture meets industry standards
- [ ] Scalability strategy addresses growth requirements
- [ ] Deployment strategy is practical and efficient

## Best Practices

### Documentation Standards

- **Clarity**: Use clear, unambiguous language throughout
- **Completeness**: Address all requirements and architectural domains
- **Consistency**: Maintain consistent terminology and formatting
- **Traceability**: Link architectural decisions back to requirements
- **Maintainability**: Structure documents for easy updates and revisions

### Architectural Principles

- **Modularity**: Design for component independence and reusability
- **Scalability**: Plan for growth and changing requirements
- **Security**: Implement security by design principles
- **Performance**: Optimize for required performance characteristics
- **Maintainability**: Design for long-term maintenance and evolution

### Client Communication

- **Executive Summary**: Provide high-level overview for stakeholders
- **Technical Detail**: Include sufficient detail for development teams
- **Visual Representation**: Use diagrams to clarify complex concepts
- **Implementation Focus**: Provide clear next steps and actionable guidance

## Troubleshooting

### Common Issues

**Incomplete Requirements Extraction**

- Solution: Review all client materials thoroughly
- Use follow-up questions to clarify ambiguities
- Validate requirements with stakeholders

**Architecture Complexity**

- Solution: Break complex systems into manageable components
- Use layered architecture approaches
- Prioritize simplicity and maintainability

**Technology Stack Decisions**

- Solution: Base decisions on requirements and constraints
- Consider team expertise and organizational standards
- Evaluate long-term maintenance and support

### Quality Improvement

- Regular review and validation of architectural decisions
- Stakeholder feedback incorporation
- Continuous refinement based on implementation learnings
- Documentation updates as requirements evolve
