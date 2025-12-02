# Contributing to the Human Embedded Technology Wiki

Thank you for your interest in contributing to the Human Embedded Technology Wiki! This project aims to be a comprehensive resource for anyone interested in biohacking, implantable technology, and human-technology integration.

## How to Contribute

### Quick Start

1. **Fork the repository** on GitHub
2. **Clone your fork** locally
3. **Make your changes** to the appropriate markdown files in the `wiki/` folder
4. **Commit your changes** with a clear, descriptive commit message
5. **Push to your fork** and submit a Pull Request

### What You Can Contribute

We welcome contributions in many forms:

- 📝 **Content additions** — New information, guides, or resources
- 🐛 **Error corrections** — Fixing typos, outdated information, or inaccuracies
- 🔗 **Link updates** — Fixing broken links or adding relevant resources
- 📚 **New wiki pages** — If you have expertise in an area not yet covered
- 🌐 **Translations** — Help make this wiki accessible to more people
- 💡 **Suggestions** — Open an issue with ideas for improvement

## Project Structure

```
human-embedded-tech/
├── wiki/                        # Main wiki content
│   ├── getting-started.md       # Introduction for newcomers
│   ├── implants-guide.md        # Detailed implant information
│   ├── tools-and-equipment.md   # Hardware and software tools
│   ├── diy-projects.md          # Hands-on project guides
│   ├── safety-and-legal.md      # Safety information and legal considerations
│   ├── glossary.md              # Terminology definitions
│   └── resources.md             # External links and references
├── pegleg/                      # PegLeg project documentation
├── implant-tech-files/          # Technical files and notes
├── mkdocs.yml                   # MkDocs configuration
├── README.md                    # Repository readme
├── CONTRIBUTING.md              # This file
└── biohacking-history.md        # History of biohacking
```

## Content Guidelines

### Focus Areas

This wiki focuses on **human embedded technology**, including:

- RFID and NFC implants
- Magnetic implants
- Biocomputing devices (like PegLeg)
- Related tools and equipment
- Safety practices and legal considerations
- DIY projects and experiments

### Writing Style

- **Be clear and accessible** — Write for readers who may be new to the topic
- **Be accurate** — Verify information before adding it
- **Be neutral** — Present information objectively
- **Be respectful** — This community values bodily autonomy and informed decision-making

### Safety First

When writing about procedures, installations, or experiments:

- Always emphasize safety considerations
- Include warnings where appropriate
- Never encourage unsafe practices
- Recommend professional installers for implant procedures

## Making Changes

### Editing Existing Content

1. Navigate to the relevant file in `wiki/`
2. Make your changes using Markdown formatting
3. Ensure internal links still work
4. Preview your changes locally if possible (see below)

### Adding New Pages

If you want to add a new wiki page:

1. Create a new `.md` file in the `wiki/` folder
2. Follow the existing page structure
3. Add links to the new page from relevant existing pages
4. Update `mkdocs.yml` to include the new page in navigation

### Testing Locally

To preview your changes:

```bash
# Install MkDocs and the Material theme
pip install mkdocs mkdocs-material

# Serve the site locally
mkdocs serve

# Open http://localhost:8000 in your browser
```

## Markdown Guidelines

We use standard Markdown with some MkDocs Material extensions:

### Headers

```markdown
# Page Title (H1)
## Section (H2)
### Subsection (H3)
```

### Admonitions (Callout Boxes)

```markdown
!!! note "Optional Title"
    Note content here.

!!! warning
    Warning content here.

!!! danger "Important"
    Critical information here.
```

### Tables

```markdown
| Column 1 | Column 2 |
|----------|----------|
| Data 1   | Data 2   |
```

### Code Blocks

````markdown
```python
print("Hello, World!")
```
````

### Internal Links

```markdown
[Link Text](other-page.md)
[Link to Section](page.md#section-heading)
```

## Code of Conduct

### Our Pledge

We are committed to providing a welcoming and inclusive environment for everyone interested in human embedded technology.

### Expected Behavior

- Be respectful and considerate
- Welcome newcomers and help them learn
- Provide constructive feedback
- Respect differing viewpoints and experiences

### Unacceptable Behavior

- Harassment or discrimination
- Trolling or inflammatory comments
- Personal attacks
- Sharing others' private information
- Promoting unsafe practices

## Questions?

If you have questions about contributing:

1. Check existing issues for similar questions
2. Open a new issue with your question
3. Join the community discussions

## Recognition

Contributors who submit accepted pull requests will be recognized for their contributions. Thank you for helping make this wiki better!

---

## License

By contributing to this wiki, you agree that your contributions will be licensed under the same license as the project.

---

Thank you for contributing to the Human Embedded Technology Wiki! Together, we can build a comprehensive resource for the biohacking community.
