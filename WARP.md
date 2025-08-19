# WARP.md

This file provides guidance to WARP (warp.dev) when working with code in this repository.

## Repository Overview

This is a personal resume repository containing structured resume data in multiple formats. The repository maintains professional resume information for Jetoine Mathurin, an IT professional with 8+ years of experience.

## Core Architecture

### Data Structure
- **Source of Truth**: `enhanced_resume_json.json` - Contains structured resume data following JSON Resume Schema conventions
- **Presentation Layer**: `professional_resume.html` - Self-contained HTML file with embedded CSS for visual presentation

### File Organization
```
/
├── enhanced_resume_json.json    # Structured resume data (JSON)
├── professional_resume.html     # Rendered HTML resume
└── WARP.md                     # This guidance file
```

The JSON file serves as the canonical data source, containing:
- Personal information (basics)
- Work experience with detailed highlights
- Education and certification details
- Technical skills organized by category
- All data structured for programmatic access

The HTML file is a complete, standalone resume document with:
- Responsive design for various screen sizes
- Professional styling with CSS3 gradients and flexbox
- Print-friendly formatting
- Self-contained (no external dependencies)

## Common Development Commands

### Viewing Files
```bash
# View JSON resume data
cat enhanced_resume_json.json | jq '.'

# Open HTML resume in browser
open professional_resume.html

# Validate JSON structure
python -m json.tool enhanced_resume_json.json > /dev/null
```

### Git Operations
```bash
# Standard git workflow for updates
git add .
git commit -m "Update resume: [description]"
git push origin main
```

### File Validation
```bash
# Check HTML validity (if w3c validator is available)
curl -H "Content-Type: text/html; charset=utf-8" --data-binary @professional_resume.html https://validator.w3.org/nu/?out=json

# Validate JSON format
jq empty enhanced_resume_json.json
```

## Data Management Guidelines

### JSON Schema Adherence
The `enhanced_resume_json.json` follows these structural conventions:
- **basics**: Contact information and professional summary
- **work**: Array of employment history with company, position, dates, summary, and highlights
- **education**: Academic credentials and current enrollment status
- **certificates**: Professional certifications with issuer and validity
- **skills**: Technical competencies organized by category with keyword arrays

### Content Consistency
When updating resume data:
1. Maintain consistent date formatting (YYYY-MM format for work dates)
2. Keep highlight bullet points action-oriented and quantified
3. Ensure skills categories align between JSON structure and intended presentation
4. Verify contact information matches across both files

### HTML Presentation
The HTML file includes:
- Responsive design breakpoints for mobile/desktop viewing
- Professional color scheme using CSS custom properties
- Print optimization through media queries
- Semantic HTML structure for accessibility

## File Relationship Management

When making updates, consider the relationship between files:
- JSON changes should be reflected in HTML if updating presentation
- HTML styling modifications don't require JSON updates
- Both files should maintain the same factual information
- Version control both files together for consistency

## Professional Context

This resume represents an IT professional specializing in:
- Microsoft ecosystem management (SCCM, Intune, Active Directory)
- ServiceNow implementations and workflow optimization
- Multi-platform technical support (Windows, macOS, Linux)
- Federal compliance standards (NIST, HIPAA)
- Cloud platforms (Microsoft 365, AWS)

The structured data supports various use cases including job applications, portfolio websites, and professional networking profiles.
