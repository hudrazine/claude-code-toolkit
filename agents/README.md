# Universal Agent Templates

Generic subagent templates for common development tasks. These agents can be used as-is or customized for project-specific needs.

## Available Agents

### 🌐 `playwright-browser-automation` - Browser Automation Specialist
Handles all browser-related tasks with Playwright MCP tools to preserve main context.

**Key Capabilities:**
- Web scraping and data extraction
- UI testing and form validation
- Screenshot capture and visual verification
- Dynamic content handling and AJAX requests

**Best for:**
- Checking website functionality
- Extracting data from web pages
- Automated UI testing
- Browser session management

**When to use:**
```
"Check if example.com is loading correctly"
"Extract pricing information from this product page"
"Test the login form functionality"
```

### 🔍 `web-research-analyst` - Research & Information Gathering
Conducts comprehensive web research with systematic searches and source verification.

**Key Capabilities:**
- Multi-source information gathering
- Fact-checking and verification
- Market research and trend analysis
- Current events and real-time data

**Best for:**
- Technology trend research
- Fact verification from multiple sources
- Market analysis and competitive research
- Gathering up-to-date information

**When to use:**
```
"What are the latest developments in quantum computing?"
"Verify if this new policy was actually passed"
"Research current market trends in renewable energy"
```

### 📚 `library-docs-specialist` - Library Documentation Specialist
Provides comprehensive, version-specific documentation and implementation guidance for any library, framework, or package using Context7 and DeepWiki MCPs.

**Key Capabilities:**
- Version-specific documentation retrieval via Context7 MCP
- GitHub repository analysis and source-level insights via DeepWiki MCP
- API references and implementation guides
- Troubleshooting and error resolution
- Version migration assistance and breaking changes
- Cross-library integration guidance
- Implementation details and design pattern analysis

**Best for:**
- Library-specific function usage and syntax
- Framework implementation patterns
- Version upgrade and migration guidance
- Source code analysis and implementation details
- Comparative analysis between libraries
- Resolving library-related errors

**When to use:**
```
"How do I use the useEffect hook in React 18?"
"I'm getting an error when trying to use Prisma with Next.js 14"
"How does Redux Toolkit's createSlice actually work under the hood?"
```

### 🧪 `qa-test-designer` - Test Design Specialist
Creates comprehensive test cases and test scenarios using industry-standard techniques like boundary value analysis, equivalence partitioning, and risk-based testing.

**Key Capabilities:**
- Systematic test case design and scenario development
- Boundary value analysis and equivalence partitioning
- Risk-based testing and test prioritization
- Test coverage analysis and gap identification
- Use case and user journey testing
- Error guessing and negative testing scenarios

**Best for:**
- Creating test suites for new features
- Designing comprehensive API test scenarios
- Ensuring thorough test coverage
- Validating complex business logic
- Planning regression test strategies
- Optimizing test case efficiency

**When to use:**
```
"I've just created a user registration function that validates email addresses and passwords. Can you help me test it?"
"I need test scenarios for my REST API that handles CRUD operations for products"
"I've implemented a shopping cart feature with add, remove, and update quantity functions. What test cases should I have?"
```

### 🐛 `qa-bug-investigator` - Bug Analysis Specialist
Analyzes, reproduces, and investigates software bugs and defects with systematic debugging and pattern recognition.

**Key Capabilities:**
- Root cause analysis using systematic techniques
- Bug reproduction and minimal test case creation
- Pattern recognition in defect clusters
- Log analysis and trace interpretation
- Severity assessment and impact analysis
- Regression vs. new defect determination
- Environment and configuration analysis

**Best for:**
- Investigating intermittent production issues
- Analyzing complex or hard-to-reproduce bugs
- Understanding patterns in failure clusters
- Performing systematic root cause analysis
- Optimizing bug reproduction steps
- Triaging and prioritizing defects

**When to use:**
```
"We're seeing random 500 errors on the checkout page, happens about 1 in 10 times"
"Can you help me figure out why this function sometimes returns null when it shouldn't?"
"We've had 5 similar crashes this week, all seeming to involve user authentication"
```

### ⚙️ `qa-automation-strategist` - Test Automation Strategy Expert
Provides strategic guidance on test automation initiatives, framework architecture, and ROI optimization.

**Key Capabilities:**
- Test automation strategy development from scratch
- ROI analysis and automation candidacy evaluation
- Framework architecture design and tool selection
- Test pyramid optimization and coverage planning
- Phased automation roadmap creation
- Maintenance planning and governance strategies
- Anti-pattern identification and mitigation

**Best for:**
- Developing comprehensive automation strategies
- Evaluating which tests to automate for maximum ROI
- Designing scalable test automation frameworks
- Planning automation implementation phases
- Optimizing existing automation suites
- Making strategic tool selection decisions

**When to use:**
```
"We're starting a new project and need to figure out our test automation approach"
"Should we automate our regression suite? It takes 3 days to run manually"
"We need to design a scalable test automation framework for our microservices"
```

### 🔒 `qa-security-reviewer` - Security Assessment Specialist
Performs security assessments, vulnerability analysis, threat modeling, and compliance verification.

**Key Capabilities:**
- Security vulnerability identification and assessment
- OWASP Top 10 and STRIDE threat analysis
- Authentication and authorization testing
- Data protection and encryption validation
- Compliance verification (GDPR, PCI DSS, HIPAA)
- Threat modeling and risk assessment
- Security test case design

**Best for:**
- Reviewing authentication and authorization code
- Creating comprehensive threat models
- Identifying OWASP security vulnerabilities
- Ensuring regulatory compliance
- Designing security test strategies
- Assessing API and web application security

**When to use:**
```
"I've just implemented a new login system with password reset functionality"
"Can you create a threat model for our e-commerce platform?"
"We need to verify our data handling meets GDPR requirements"
```

### 📊 `qa-performance-analyst` - Performance Testing Expert
Designs, executes, and analyzes performance tests including load testing, stress testing, and capacity planning.

**Key Capabilities:**
- Load, stress, and scalability test design
- Performance bottleneck identification and analysis
- Statistical analysis of response times and throughput
- Capacity planning and growth projection modeling
- SLA/SLO definition and validation
- Resource utilization analysis
- Performance optimization recommendations

**Best for:**
- Validating system performance under load
- Identifying performance bottlenecks
- Planning capacity for growth scenarios
- Establishing performance baselines
- Analyzing test results and metrics
- Optimizing system scalability

**When to use:**
```
"I need to validate that our API can handle 1000 concurrent users"
"Here are the results from our load test - response times increased from 500ms to 3s under load"
"We expect 50% growth in traffic over the next 6 months. How should we scale?"
```

## Usage

### Automatic Delegation
Claude Code will automatically use these agents when appropriate based on task context.

### Explicit Invocation
Request a specific agent in your command:
```
Use the playwright-browser-automation agent to test the checkout flow
Have the web-research-analyst agent investigate recent AI breakthroughs
```

### Agent Location
- **Project agents**: `.claude/agents/`
- **User agents**: `~/.claude/agents/`
