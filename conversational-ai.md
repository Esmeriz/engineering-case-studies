# Conversational AI with usable context and recoverable interactions

## The engineering problem

A conversational application needs more than a model response. It has to retrieve relevant information, preserve context across turns, render streamed output, and respond consistently when someone stops a reply or retries a request.

For financial analysis, it also matters whether a statement is grounded in data, refers to a hypothetical scenario, or describes a real circumstance.

## My contributions

At Quartz, I contributed across the application backend and its interfaces:

- Connected conversational workflows with research and financial-data tools.
- Worked on persisted conversation context and preserving the distinction between hypothetical scenarios and user-provided facts.
- Contributed to durable requests, interrupted-response handling, and recovery from rejected sends.
- Improved the presentation of streamed content and the ability to inspect response status and supporting traces.
- Added regression coverage and refined instructions for explaining missing data and uncertainty in ordinary language.

## Decisions and tradeoffs

**Keep context attributable.** A summary can lose the distinction between an example and a real disclosure. I worked on preserving the surrounding conversation and source context instead of treating every extracted statement as a durable fact.

**Treat stopping a response as a real state.** A stopped interaction still needs a consistent history and a clear interface. My work included retaining interrupted responses and making their state visible.

**Test application behavior and model behavior separately.** Persistence and transport can be checked deterministically. Whether a model interprets context correctly requires behavioral evaluation; passing the former does not establish the latter.

## Result and limits

These contributions added context-handling, request-recovery, and inspection capabilities to the wider application. They also supplied regression coverage for the surrounding software contracts.

I do not claim that these changes eliminated incorrect answers, resolved every conversational failure, or established financial-advice suitability. This case study describes my engineering contribution without exposing prompts, customer conversations, or internal architecture.
