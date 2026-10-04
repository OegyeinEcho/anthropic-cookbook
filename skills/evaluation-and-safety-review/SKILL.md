---
name: evaluation-and-safety-review
description: Use when designing or reviewing a repeatable evaluation, moderation rubric, classifier, or safety-sensitive assistant workflow and the result needs measurable criteria, test coverage, and conservative failure handling.
---

# Evaluation and safety review

Make a workflow testable before optimizing it. This combines the cookbook's evaluation and moderation patterns into a product-neutral review process.

## Workflow

1. Define the task boundary and intended behavior in one sentence. List explicit non-goals, especially actions the workflow must not take.
2. Build a representative case set. Include ordinary cases, edge cases, ambiguous cases, adversarial wording, out-of-domain inputs, and cases where the correct result is refusal or clarification. Keep the distribution close to expected real use.
3. For each case, record:
   - input
   - expected output or rubric
   - risk level
   - acceptable alternatives
   - evidence needed to judge the result
4. Choose the least expensive reliable grader:
   - exact match, schema, range, or rule checks when the task permits
   - human review for nuanced or high-consequence judgments
   - model-assisted grading only with a written rubric, sampled human audit, and explicit agreement limits
5. For moderation or classification, define labels positively and negatively, give boundary examples, and include an uncertain or escalation path when binary labels would be unsafe. Do not treat a model label as a legal, medical, employment, or other final determination.
6. Keep evaluation data, expected answers, and grader instructions separate from the workflow being tested to reduce leakage and make regressions visible.
7. Run a baseline before changing prompts or policies. Compare versions on the same cases and report per-category results, not only an average.
8. Inspect false positives and false negatives manually. Pay special attention to vulnerable groups, ambiguous language, sarcasm, quoted harmful content, and distribution shifts.
9. Set stop conditions: missing evidence, low grader agreement, unsafe action request, unsupported domain, or a score that hides a severe failure should pause rollout.
10. Report method, dataset scope, grader type, sample size, aggregate and per-class results, notable failures, and limitations. Never claim that an unrun evaluation passed.

## Safe default

When the workflow could trigger a consequential action, prefer classification plus a human-review or explicit-confirmation boundary. A draft, recommendation, or refusal is safer than silently performing the action.
