# Contributing to BodyAtlas

Thanks for your interest in improving BodyAtlas! This guide explains how to add new organs, diseases, or translations.

## How the Data Works

All data lives in `index.html` inside a JavaScript array called `DATA`. Each entry follows this structure:

```js
{
  id: "organ_id",           // unique lowercase string, no spaces
  system: "cardiovascular", // see system list below
  name: "Heart",            // display name
  img: "https://...",       // Wikipedia Commons image URL (preferred)
  desc: "A short description of the organ (2-3 sentences).",
  parts: [
    "Left Ventricle",
    "Right Ventricle",
    // ... all anatomical subparts
  ],
  diseases: [
    {
      name: "Disease Name",
      type: "Chronic",       // see type list below
      emoji: "❤️",
      symptoms: "Comma-separated list of common symptoms",
      cures: {
        medication: ["Drug 1 (generic name)", "Drug 2"],
        vaccine:    ["Vaccine name"],
        surgery:    ["Procedure name"],
        therapy:    ["Therapy type"],
        lifestyle:  ["Lifestyle change"],
      }
    }
  ]
}
```

Only include the `cures` keys that apply — not every disease has a vaccine or surgery option.

---

## Available Body Systems

| Key | System |
|---|---|
| `nervous` | Nervous System |
| `cardiovascular` | Cardiovascular |
| `respiratory` | Respiratory |
| `digestive` | Digestive |
| `integumentary` | Skin / Integumentary |
| `sensory` | Sensory |
| `urinary` | Urinary |
| `musculoskeletal` | Musculoskeletal |
| `endocrine` | Endocrine |
| `reproductive` | Reproductive |

---

## Disease Types

Use one of these for consistency: `Acute`, `Chronic`, `Infection`, `Viral Infection`, `Autoimmune`, `Malignant`, `Degenerative`, `Inflammatory`, `Neurological`, `Neurodegenerative`, `Metabolic`, `Structural`, `Vascular`, `Traumatic`, `Functional`, `Endocrine`, `Pressure`, `Arrhythmia`, `Mucosal`

---

## Step-by-Step: Adding a New Organ

1. **Fork** the repository
2. Open `index.html` in a text editor
3. Find the `const DATA = [` array
4. Add your organ object at the end of the array (before the closing `]`)
5. Use a Wikipedia Commons image URL for `img` (free license, reliable hosting)
6. Test by opening `index.html` in your browser
7. Submit a **Pull Request** with the title: `Add: [Organ Name]`

---

## Step-by-Step: Adding a Disease to an Existing Organ

1. Find the organ in the `DATA` array by its `id`
2. Add a new object to its `diseases` array
3. Include at minimum: `name`, `type`, `emoji`, `symptoms`, and at least one `cures` category
4. Submit a **Pull Request** with the title: `Disease: [Disease Name] → [Organ Name]`

---

## Image Guidelines

- Use **Wikimedia Commons** images when possible (free license)
- URL format: `https://upload.wikimedia.org/wikipedia/commons/thumb/.../200px-....png`
- Prefer anatomical diagrams over photos
- Recommended size: ~200px width

---

## Reporting Issues

If you find incorrect medical information, please open an **Issue** with:
- The organ and disease name
- What's incorrect
- A reliable source (PubMed, WHO, NHS, Mayo Clinic preferred)

---

## Code of Conduct

Be respectful. This is a health education project, accuracy and clarity matter more than speed. Cite sources where possible.
