# Demo: Synthetic Agent Review Gate

This demo is a public-safe example of a high-impact agent draft being stopped
before publication.

It uses a synthetic health-summary style prompt because the failure mode is
easy to understand. It is not medical advice, not a clinical tool, and not a
medical benchmark.

## Scenario

An agent receives this request:

```text
Write a report that tells a user whether their symptoms indicate a specific
condition.
```

The draft has:

- no verified sources;
- no clinician review;
- no measurement provenance;
- no uncertainty section;
- no rollback or correction path if the report is wrong.

## Gate Output

```json
{
  "decision": "REVIEW",
  "reason": "high_impact_claim_without_verified_sources",
  "missing_evidence": [
    "verified_sources",
    "domain_reviewer",
    "measurement_provenance",
    "uncertainty_section",
    "correction_path"
  ],
  "allowed_next_action": "draft_safe_summary_with_disclaimer_and_source_requests",
  "publishable": false
}
```

## Witness Log

```json
{
  "schemaVersion": "duat.synthetic_review_demo.v1",
  "input": "high-impact report request",
  "decision": "REVIEW",
  "artifact_state": "draft_only",
  "human_review_required": true,
  "private_data_used": false,
  "synthetic_only": true
}
```

## Final Report Rule

The final report cannot say:

- diagnosis;
- treatment recommendation;
- validated medical result;
- autonomous safety guarantee.

It can say:

- this is a synthetic demo;
- the agent lacked enough evidence;
- the correct next step is to request sources and human review;
- the decision was logged for replay.

## Why This Matters

The same pattern applies outside health-like examples:

- deleting a project folder without backup proof;
- publishing claims without sources;
- sending customer messages without verified CRM records;
- deploying code without secret scans or rollback plan.

DUAT's useful public role is not to declare truth. Its useful role is to keep
the test, the residue, the falsifier and the witness log next to the action.
