# Working with AI tools

Language models and their relatives are instruments. We treat them the way this School treats any other instrument: learn it properly, know its failure modes, and stay responsible for the output.

Refusing to use them is not a defensible professional position — you will work alongside people who use them well. Neither is using them uncritically, and that failure is currently far more common.

## The rule everything else follows from

> **You are accountable for everything you submit, regardless of what produced it.**

If a model wrote a derivation and the derivation is wrong, you submitted a wrong derivation. If it invented a reference, you cited a source that does not exist. If it produced code that runs and computes the wrong thing, you shipped a bug. "The model said so" describes how the error entered your work; it does not transfer responsibility for it.

## Disclose

Say what you used and what you used it for. A line in the README or at the end of the report is enough:

> *Draft code for the plotting script was generated with an LLM and reviewed and modified by me. The measurements, the analysis and the text are my own.*

This costs one sentence and settles the question permanently. Concealing it is the same category of act as concealing any other undeclared source — see [Credit and honesty](ethics.md#credit-and-honesty).

**Course policy overrides this page.** Some assessments prohibit these tools entirely, and they are entitled to. Ask, in writing, at the start of the course, and keep the answer.

!!! note "To be filled in by the School"
    Link the university's official policy on generative AI in assessed work here, and state the School's default where a course is silent. Until that default is written down, students will invent one.

## Where they help, and where they take something from you

They are genuinely good at: explaining an unfamiliar concept at whatever level you ask, boilerplate and glue code, translating between languages and formats, first drafts of documentation, finding what a library call does, refactoring, and being an infinitely patient thing to ask a stupid question at midnight.

They are bad at: anything where being confidently wrong is expensive. Numerical work. Novel derivations. Citations — models fabricate plausible references routinely. Anything depending on facts about *your* hardware, *your* data or *your* course.

And there is a third category, which matters more during a degree than during a career. **Some of the work is the point.** The reason you struggle through a derivation, debug your own control loop or write your own literature review is that the struggle is what builds the engineer. Outsourcing it produces a finished artefact and no engineer. You can tell the difference by a simple test: could you reproduce this on a whiteboard, without the tool, if someone asked? If not, you have an output but you have not learned anything, and the exam — or the first design review of your career — will find out.

## Verify

- **Recompute anything numerical.** By hand, or with a tool you trust, or both.
- **Open every reference.** If you cannot find the paper, the paper is probably not real.
- **Test the code against a case you know the answer to.** Code that runs is not code that is correct.
- **Check it against the primary source** — the datasheet, the standard, the manual, the specification. Models are confident about hardware they have never seen.
- **Be suspicious when it agrees with you.** Fluent confirmation of what you already believed is the failure mode you are least likely to catch.

## Two hard limits

**Do not paste what is not yours to paste.** Unpublished research data, other people's personal data, material under NDA, credentials, or anything from an industry partner. Assume anything sent to an external service has left your control permanently.

**Do not put a model in a control loop with hardware.** Not a robot, not a reactor, not a power supply, not a test rig. A model may help you write the controller; a human reviews it, and it runs inside a checked envelope with the limits and the stop enforced outside the model. This is not a hypothetical concern — it is written into our own [robot operating documentation](https://newuu-engineering.github.io/robotics-docs/) as a standing rule, because the failure is silent right up until it is not.

See [Safety is part of the culture](safety.md).
