---
name: canva-branded-presentation
description: Create on-brand Canva presentations from an outline or brief, or autofill brand templates with content. Use when the user asks to "create a branded presentation", "make an on-brand deck", "turn an outline into slides", "generate a presentation from a brief", "use a brand template", "autofill a template", or "search for a template". Input can be text directly in the message, a reference to a Canva doc by name, or a Canva design link (e.g., https://www.canva.com/design/...).
---

# Canva Branded Presentation

Create professional, on-brand presentations in Canva from user-provided outlines or briefs, or autofill brand templates with content.

## Workflow: Generate from Outline

### Step 1: Get the Content Source

- If the user provides text directly, use that as the outline/brief
- If the user provides a Canva design link (e.g., `https://www.canva.com/design/DAG.../...`), extract the design ID from the URL and use `Canva:start-editing-transaction` to read its contents
- If the user references a Canva doc by name, use `Canva:search-designs` to find it, then `Canva:start-editing-transaction` to read its contents

### Step 2: Select a Brand Kit

- Call `Canva:list-brand-kits` to retrieve the user's brand kits
- If only one brand kit exists, use it automatically without asking
- If multiple brand kits exist, present the options and ask the user to select one

### Step 3: Generate the Presentation

- Call `Canva:generate-design` with:
  - `design_type`: "presentation"
  - `brand_kit_id`: the selected brand kit ID
  - `query`: a detailed prompt following the presentation format below
- Show the generated candidates to the user

### Step 4: Finalize

- Ask the user which candidate they prefer
- Call `Canva:create-design-from-candidate` to create the editable design
- Provide the user with the link to their new presentation

## Presentation Query Format

Structure the query for `Canva:generate-design` with these sections:

**Presentation Brief**
- Title: working title for the deck
- Topic/Scope: 1-2 lines describing the subject
- Key Messages: 3-5 main takeaways
- Style Guide: tone and imagery style based on the brief

**Narrative Arc**
One paragraph describing the story flow (e.g., Hook → Problem → Solution → Proof → CTA).

**Slide Plan**
For each slide include:
- Slide N — "Exact Title"
- Goal: one sentence on the slide's purpose
- Bullets (3-6): short, parallel phrasing with specifics
- Visuals: explicit recommendation (chart type, diagram, image subject)
- Speaker Notes: 2-4 sentences of narrative detail

## Workflow: Autofill a Brand Template

### Step 1: Find a Template

- Call `Canva:search-brand-templates` to search templates by name or keywords
- When the user mentions "templates", always use `search-brand-templates` — never `search-designs`
- If multiple templates match, present the options and ask the user to pick one

### Step 2: Inspect Template Fields

- Call `Canva:get-brand-template-dataset` to see which data fields (text, images) the template expects
- Review the field names and types to understand what content is needed

### Step 3: Autofill the Template

- Call `Canva:autofill-design` with the template ID and a data mapping of field names to values
- The tool creates a new design from the template with the provided content filled in
- Provide the user with the link to the new design

## Notes

- If the outline is sparse, expand it into a complete slide plan with reasonable content
- For briefs (narrative descriptions), extract key points and structure them into slides
- Aim for clear, action-oriented slide titles
- Autofill may require a paid Canva plan (Pro or Enterprise)
