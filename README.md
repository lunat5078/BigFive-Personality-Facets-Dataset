# Big Five Personality Facets Dataset

A dataset of behavioral statements labeled by the **Big Five (OCEAN)** personality dimensions and their 30 facets, designed for personality representation engineering and classification tasks.

## Overview

This dataset contains ~15,000 behavioral examples covering all 30 facets of the Big Five personality model. Each example is labeled with its dimension, subdimension (facet), polarity (positive/negative), and a binary label.

## Dataset Structure

Each JSON file contains a list of entries with the following fields:

| Field | Type | Description |
|---|---|---|
| `id` | string | Unique identifier |
| `dimension` | string | Big Five dimension (e.g., "Extraversion") |
| `subdimension` | string | Facet name (e.g., "Assertiveness") |
| `polarity` | string | `"positive"` or `"negative"` |
| `label` | int | Binary label (0 or 1) |
| `lang` | string | Language (`"en"`) |
| `text` | string | Behavioral statement |

### Example Entry

```json
{
  "id": "exa-str-000001",
  "dimension": "Agreeableness",
  "subdimension": "Straightforwardness",
  "polarity": "positive",
  "label": 1,
  "lang": "en",
  "text": "When asked for feedback, they provide honest and direct responses."
}
```

## File Organization

All data files are in the `data/` directory, named as `{dimension}_{facet}.json`.

### Agreeableness (7 facets)
- `agreeableness_altruism.json` - Altruism
- `agreeableness_compliance.json` - Compliance
- `agreeableness_cooperation.json` - Cooperation
- `agreeableness_modesty.json` - Modesty
- `agreeableness_straightforwardness.json` - Straightforwardness
- `agreeableness_tender_mindedness.json` - Tender-Mindedness / Sympathy
- `agreeableness_trust.json` - Trust

### Conscientiousness (6 facets)
- `conscientiousness_achievement_striving.json` - Achievement-Striving
- `conscientiousness_deliberation.json` - Deliberation
- `conscientiousness_dutifulness.json` - Dutifulness
- `conscientiousness_orderliness.json` - Orderliness
- `conscientiousness_self_discipline.json` - Self-Discipline
- `conscientiousness_self_efficacy.json` - Self-Efficacy / Competence

### Extraversion (6 facets)
- `extraversion_assertiveness.json` - Assertiveness
- `extraversion_energy.json` - Energy / Activity
- `extraversion_excitement_seeking.json` - Excitement-Seeking
- `extraversion_gregariousness.json` - Gregariousness
- `extraversion_positive_emotions.json` - Positive Emotions
- `extraversion_warmth.json` - Warmth

### Neuroticism (6 facets)
- `neuroticism_anger.json` - Angry Hostility / Anger
- `neuroticism_anxiety.json` - Anxiety
- `neuroticism_depression.json` - Depression
- `neuroticism_impulsiveness.json` - Impulsiveness
- `neuroticism_self_consciousness.json` - Self-Consciousness
- `neuroticism_vulnerability.json` - Vulnerability to Stress

### Openness (6 facets)
- `openness_actions.json` - Actions / Adventurousness
- `openness_aesthetics.json` - Aesthetics / Artistic Interests
- `openness_fantasy.json` - Fantasy
- `openness_feelings.json` - Feelings / Emotionality
- `openness_ideas.json` - Ideas
- `openness_values.json` - Values

## Statistics

| Dimension | Facets | Total Examples |
|---|---|---|
| Agreeableness | 7 | ~3,503 |
| Conscientiousness | 6 | ~3,010 |
| Extraversion | 6 | ~3,003 |
| Neuroticism | 6 | ~3,000 |
| Openness | 6 | ~3,001 |
| **Total** | **31** | **~15,517** |

## Usage

```python
import json
import os

# Load a single facet
with open("data/extraversion_assertiveness.json") as f:
    data = json.load(f)

# Load all facets
all_data = []
for filename in os.listdir("data"):
    if filename.endswith(".json"):
        with open(os.path.join("data", filename)) as f:
            all_data.extend(json.load(f))

print(f"Total examples: {len(all_data)}")
```

## Citation

If you use this dataset, please cite:

```bibtex
@misc{bigfive-facets-dataset,
  title={Big Five Personality Facets Dataset},
  author={Zhen Tang},
  year={2025},
  url={https://github.com/YOUR_USERNAME/BigFive-Personality-Facets-Dataset}
}
```

## License

This dataset is released under the [MIT License](LICENSE).
