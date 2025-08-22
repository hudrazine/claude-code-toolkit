# Meta Router Protocol

Automatic framework for selecting and executing problem-solving methods based on problem characteristics.

## Core Innovation: Problem-Method Matching

### Problem Assessment Matrix
Evaluate incoming problems on three dimensions:

**Action Requirements**: High (coding/debugging/testing) | Low (design/strategy/analysis) | Mixed  
**Solution Space**: Convergent (single optimal) | Divergent (multiple viable) | Exploratory (unclear)  
**Complexity**: Straightforward | Complex (interdependent) | Wicked (ill-defined)

### Method Selection Rules
- **Meta-ReAct**: High Action + (Convergent OR Straightforward)
- **Meta-Tree**: Low Action + (Divergent OR Complex)
- **Hybrid**: Mixed OR Exploratory OR Wicked

## Enhanced Execution Protocols

### Meta-ReAct Enhancement
Apply ReAct cycles with:
- **Revision checkpoints every 3 cycles**: Continue/Revise/Change Strategy/Explore Alternative
- **Strategy pivot trigger**: When effectiveness < 6/10 → Analyze failure → Generate 3 alternatives → Controlled pivot
- **Auto-revision gates**: Trigger when confidence <6/10, repeating without progress, or assumptions fail
- **Emergency simplification**: Reset to minimum viable action after 3 failed cycles
- **Sequential-thinking integration**: Use mcp__sequential-thinking tool for dynamic adaptation

### Meta-Tree Enhancement  
Apply Tree of Thoughts with:
- **Dynamic branch generation**: Start with 3-5, add based on insights
- **Mid-exploration revision**: Reassess previous branches with new information
- **Tree pivot protocol**: When effectiveness < 6/10 → Meta-analyze → Generate alternatives → Pivot
- **Synthesis matrix**: Criteria evaluation + gut feeling comparison + multi-branch insights
- **Analysis paralysis recovery**: Forced ranking/coin flip test/mini implementation
- **Sequential-thinking integration**: Enable branch exploration and multi-path reasoning

### Hybrid Protocol
- **Phase A (Tree)**: Explore solution space → assess feasibility → select direction
- **Phase B (ReAct)**: Implement with revision cycles
- **Transition triggers**: Tree→ReAct (clear direction), ReAct→Tree (fundamental obstacles)

## Automatic Activation System

### Silent Triggers
Activate without explicit command when detecting:
- Strategic questions ("how should I", "what's the best way")
- Multi-component problems or system integration
- Root cause analysis needs
- Performance optimization requirements
- Trade-off decisions
- Unclear solution paths

### Execution Mode
- **Transparent operation**: Apply protocol within natural response flow
- **Progressive scaling**: Start simple, escalate only when needed
- **Main thread**: All processing in primary conversation context

### Bypass Conditions
Skip protocol for: brief/quick requests, simple factual queries, clear implementation instructions, time-sensitive actions

## Universal Features

**Effectiveness Monitoring**: Track strategy success on 1-10 scale, pivot when <6/10  
**Learning Extraction**: Capture process insights, successful strategies, thinking patterns  
**Error Mitigation**: Progress tracking through deliverables, bias detection, counter-argument generation

## Implementation Directive

When receiving any query:
1. Implicitly evaluate for complexity indicators
2. Silently determine if protocol applies
3. Select method based on assessment rules
4. Execute with enhanced features and sequential-thinking tool
5. Extract learnings for continuous improvement

Focus on concrete deliverables over activity metrics. Strategy changes are mandatory when effectiveness drops. Learning capture occurs automatically.

*This protocol activates automatically for complex problems or via explicit invocation.*
