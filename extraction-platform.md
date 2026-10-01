# Building a financial-data extraction platform

## The engineering problem

External financial data varies by provider and format. An application needs to turn those inputs into consistent portfolio information while accounting for differences in instruments, positions, transactions, and currencies.

Supporting that process requires both extraction software and a practical workflow for creating, checking, and updating extractors.

## My work

At Quartz, I built a financial-data extraction platform and developed its supporting generation and validation workflows. My work included:

- An API for running extraction logic and producing structured portfolio data.
- Typed data contracts and refinements to how extracted financial information is represented.
- AI-assisted generation of provider-specific extractors.
- Validation against expected outputs and feedback for refining generated implementations.
- Regression checks and safeguards against hardcoded assumptions in extraction logic.
- Automation connecting generation with repository changes and review.
- Container and delivery-pipeline work supporting the application and generation workflow.

## Decisions and tradeoffs

**Define the output contract before accepting an extractor.** Provider-specific formats should converge on explicit shared meanings. I worked on both the extraction logic and the contracts used to validate its output.

**Treat generated code as a candidate.** Generation is one step in a workflow that also needs expected outputs, validation, regression coverage, and review. A plausible implementation is not sufficient evidence of correctness.

**Avoid fitting a single sample.** Extractors that depend on hardcoded asset names or incidental sample values can appear correct without generalizing. My work included checks and guardrails targeting those assumptions.

**Make iteration repeatable.** Generation, validation feedback, and repository delivery need to work together so an extractor can be refined without relying on an undocumented sequence of manual steps.

## Result and limits

The platform brought extraction, structured contracts, AI-assisted generation, validation, and repository delivery into a shared engineering workflow. I built and iterated on that system as part of Quartz's wider product work.

This description excludes the internal project name, provider implementations, source documents, private schemas, infrastructure details, and code. It does not assert a measured accuracy improvement, universal provider coverage, or sole authorship of every later change.
