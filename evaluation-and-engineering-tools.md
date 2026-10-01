# Making AI changes easier to evaluate and inspect

## The engineering problem

An AI change can pass software tests while still producing an unhelpful answer. Reviewers need to understand the input context, the tools used, and the reason for an evaluation result. Engineers also need a practical way to preview changes before proposing them for release.

## My contributions

At Quartz, I contributed to the evaluation workflow and its supporting interfaces:

- Built and extended conversation regression scenarios and their validation.
- Improved the evidence supplied to automated assessment, including relevant context and tool-source attribution.
- Contributed interfaces for human conversation review, automated assessments, and inspection of supporting traces.
- Worked on isolated editing, preview, validation, and change-proposal workflows.
- Contributed infrastructure and reliability fixes for the preview environment.
- Improved views of runtime configuration so reviewers could understand how the application was assembled.

## Decisions and tradeoffs

**Assess the evidence available at the time.** Later information should not silently change the basis for judging an earlier answer. I worked on carrying the appropriate context into assessment and keeping missing information explicit.

**Check the reason behind a verdict.** A rejection can coincide with an expected label while missing the actual defect. My evaluation work distinguished verdict agreement from evidence that the right problem was detected.

**Separate preview, validation, and publication responsibilities.** I contributed to a workflow in which an experimental edit could be inspected and tested before becoming a proposed repository change.

**Make configuration inspectable.** A useful system view should reflect the configuration in use and clearly handle missing metadata, rather than presenting an assumed configuration as fact.

## Result and limits

The resulting capabilities supported review of conversation behavior and proposed application changes, with more explicit context, evidence, and validation status.

This work includes evaluation and preview tooling; it is not a claim that automated assessment became infallible or that preview infrastructure was deployed to every environment. Test counts, private evaluation results, security configuration, and internal service topology are intentionally omitted.
