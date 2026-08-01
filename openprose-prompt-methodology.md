# OpenProse Prompt Lab Methodology

This is the public description of the method used to evaluate changes to an
installed OpenProse skill. The evaluation workspace and its evidence history
remain private.

## Workflow

1. Record a bounded observation with its outcome, affected invariant, severity,
   confidence, and known limitations.
2. Turn repeatable, general lessons into paired candidate-visible inputs and
   evaluator-only checks.
3. Keep the production baseline immutable and evaluate candidates in a
   physically separate package.
4. Preregister a comparison, run every condition under the same controls, and
   preserve the result as a structured record.
5. Treat hard-gate failures as blocking. Soft scores cannot compensate for a
   failed safety or contract check.
6. Review findings into proposals, then require an independent verification
   pass and an explicit promotion decision.

## Evidence boundaries

- Synthetic fixtures test mechanics; they are not presented as real-world
  quality evidence.
- Observations distinguish facts, interpretations, and proposed follow-up
  evidence.
- Private transcripts, credentials, user content, and local machine paths are
  not part of the public methodology.
- Evaluation does not install or modify a production skill. Promotion is a
  separate decision with its own authority boundary.

## Verification

The lab uses one deterministic local verification entry point:

```sh
python3 tools/lab.py verify
```

That gate validates record structure, paired cases, immutable baseline and
candidate hashes, scoring arithmetic, and the expected promotion block. A
passing mechanics check does not imply deployment, production quality, or
authorization to publish a skill change.
