# Canva Skills for Claude

Professional Claude skills for working with Canva designs. These skills enable powerful Canva workflows in both Claude Desktop and Claude Code CLI.

## Available Skills

### branded-presentation
Create on-brand presentations from outlines or briefs using Canva brand kits.

**Use when:** You want to generate a professional presentation with consistent branding from text content, outlines, or Canva docs.

**Capabilities:**
- Converts outlines and briefs into structured slide decks
- Automatically applies your Canva brand kits
- Reads content from text, Canva docs, or design links
- Generates multiple design candidates for selection

### design-translation
Translate all text in a Canva design to another language, creating localized copies.

**Use when:** You need to create multilingual versions of your designs without manually editing each text element.

**Capabilities:**
- Translates all text elements while preserving layout
- Creates a new copy, leaving the original untouched
- Supports any language Claude can translate
- Batch processes all text in a single operation

### implement-feedback
Implement reviewer feedback on a Canva design — read comment threads, make the clear-cut changes.

**Use when:** A design has been reviewed and you want to apply the feedback without manually reading every comment thread and editing each slide.

**Capabilities:**
- Reads all comment threads and replies across the design
- Triages feedback into actionable, ambiguous, and manual-only categories
- Applies API-supported changes (text, formatting, images) in a single batch
- Presents a checklist of remaining manual changes with step-by-step instructions
- Replies to comment threads to close the feedback loop

### resize-for-social-media
Resize designs for multiple social media platforms (Facebook, Instagram, LinkedIn) in one operation.

**Use when:** You want to quickly distribute a design across multiple social media formats.

**Capabilities:**
- Creates 5 platform-optimized versions (Facebook post/story, Instagram post/story, LinkedIn post)
- Exports all versions as high-quality PNGs
- Provides direct download links and Canva edit links
- Executes all operations in parallel for speed

## Installation

### For Claude Desktop

1. Clone or download this repository
2. Add skills to your Claude Desktop configuration
3. Restart Claude Desktop to load the skills

### For Claude Code CLI

1. Clone this repository
2. Follow the [Claude Code skill installation guide](https://github.com/anthropics/claude-code)
3. Start using the skills from your terminal

## Usage

Simply reference the skills naturally in your conversations:

**Examples:**

```
# Branded presentation
"Create a presentation from my product launch outline using our brand kit"

# Design translation
"Translate my Summer Sale Poster design to French"

# Implement feedback
"Implement the feedback on my deck"

# Social media resize
"Resize design DABcd1234ef for all social media platforms"
```

Works seamlessly in both Claude Desktop and Claude Code CLI.

## Repository Structure

```
canva-claude-skills/
├── README.md                    # This file
├── branded-presentation/        # Presentation generation skill
│   └── SKILL.md
├── design-translation/          # Translation skill
│   └── SKILL.md
├── implement-feedback/          # Review feedback skill
│   └── SKILL.md
└── resize-for-social-media/     # Multi-format resize skill
    └── SKILL.md
```

## Contributing

To add a new skill:

1. Create a new directory with a kebab-case name
2. Add a `SKILL.md` file with skill metadata and workflow
3. Follow the existing skill patterns for consistency
4. Update this README with the new skill

## License

[Add your license here]
