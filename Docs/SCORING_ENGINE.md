# Scoring / Pattern Engine (rules-based) - (Default settings)

Goal: interpretable indicators and observations. Not grades. Not sorting people. (DEFAULT SETTINGS- Can be changed based on perspective and or environment) 

## Dimensions (initial)- (Default settings) 

- ContextDependent
- ConstraintFirst
- Literal
- RiskFirst
- SystemOriented
- AmbiguityTolerance

## How it works - (Default settings)

1. Each option maps to signals (weights).
2. Session aggregates signals across prompts.
3. Normalize into 0–100 indicators.
4. Render as observations:
   - "This pattern often prioritizes..."
   - "This pattern tends to de-prioritize..."
   - "In some environments, this tends to show up as..."

## Output assembly - (Default settings)

Results are modular (see OUTPUT_MODULES.md). Core is always available; other modules are selected per environment.

## Required core outputs - (Default settings)

- Dimension indicators
- Pattern description (observational bullets)

## Notes

Unknown/depends responses are meaningful signals. Treat as ambiguity tolerance, not missing data.
