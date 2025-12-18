# Asymbl Documentation Centralization Strategy

**Version:** 1.0.0
**Date:** December 1, 2025
**Status:** Proposed

---

## Table of Contents
- [Executive Summary](#executive-summary)
- [Current State Analysis](#current-state-analysis)
- [Proposed Solution: 3-Phase Approach](#proposed-solution-3-phase-approach)
  - [Phase 1: Centralized Documentation Hub](#phase-1-centralized-documentation-hub-start-here)
  - [Phase 2: Migrate to Markdown + Git](#phase-2-migrate-to-markdown--git)
  - [Phase 3: Smart Documentation Automation](#phase-3-smart-documentation-automation)
- [Implementation Plan](#implementation-plan)
- [Process Documentation](#process-documentation)
- [Success Metrics](#success-metrics)
- [Next Steps](#next-steps)

---

## Executive Summary

**Problem:**
Managing documentation for 6 Salesforce products with monthly releases creates a complex matrix of ~30+ documentation items scattered across Google Docs, making it difficult to maintain, version, and access.

**Solution:**
A 3-phase approach that starts with a simple centralized hub (non-disruptive) and evolves into an automated, version-controlled documentation system powered by Git, Markdown, and AI-assisted generation.

**Benefits:**
- ✅ Single source of truth for all documentation
- ✅ Professional presentation to customers and internal teams
- ✅ Version control with full change tracking
- ✅ Automated documentation generation from code changes
- ✅ Reduced manual documentation effort by 40-60%
- ✅ Improved documentation quality and consistency

**Timeline:**
- **Phase 1:** 1 week (immediate value)
- **Phase 2:** 3-6 months (foundational improvement)
- **Phase 3:** 6-12 months (advanced automation)

---

## Current State Analysis

### Products
1. **ATS** - Applicant Tracking System
2. **ASM** - Asymbl Search and Match
3. **AST** - Asymbl Time (Timekeeping/Payroll)
4. **AIN** - Asymbl Integration
5. **ARA** - Asymbl Recruiting Agent
6. **ASIN** - (Product 6)

### Documentation Types (Per Release)
1. **Release Notes** - New document for each release
2. **Pre-Deployment Steps** - Living document, updated with each release
3. **Post-Deployment Steps** - Living document, updated with each release
4. **Technical Documentation** - Living document, updated with each release
5. **User Guide** - Living document, updated with each release

### Current Challenges

**Volume:**
- 6 products × 5 doc types = 30+ documentation items
- Monthly release cycle = 12-24 new release notes per year
- Continuous updates to 24 living documents

**Organization:**
- Documentation scattered across Google Docs
- No centralized index or discovery mechanism
- Difficult to find the right doc for the right product/release
- No clear version history or change tracking

**Accessibility:**
- Multiple links to remember and share
- No single URL for customers/partners
- Unprofessional presentation

**Maintenance:**
- Manual updates prone to errors
- No review process for documentation changes
- Difficult to ensure consistency across products

**Example Current Documentation:**
- [Release Notes Sample](https://docs.google.com/document/d/1zLbO4Q0I1qilrcimTuIC_b7dhX9ncHOA/edit)
- [Pre-Deployment Steps Sample](https://docs.google.com/document/d/1-NpXlQKLjLaH6z1LV0oPRSWEero8Vsw_/edit#heading=h.imx898kkbcnu)
- [Post-Deployment Steps Sample](https://docs.google.com/document/d/1I3GxZHwOekdMqPgwql7CyNPiyAbNX4S9/edit#heading=h.vbz3kcfpxzjl)
- [Tech Documentation Sample](https://docs.google.com/document/d/1vLmKyXc9eNezYof9oxUxD-LeFwxg3UlZ/edit#heading=h.irdo7965x7tj)
- [User Guide Sample](https://docs.google.com/document/d/1reHtsxktseXFMpY5w3g2HWYFoyC_RGjB/r/edit/edit#heading=h.xgrwto13rk5t)

---

## Proposed Solution: 3-Phase Approach

### Phase 1: Centralized Documentation Hub (Start Here)

**Timeline:** 1 week
**Effort:** Low
**Risk:** None
**Value:** High (Immediate)

#### Overview
Create a professional documentation landing page on the existing `asymblinc.github.io` GitHub Pages site that serves as the **single source of truth** for finding all documentation.

#### Structure
```
asymblinc.github.io/
├── index.html                    # Existing landing page
├── docs/
│   ├── index.html                # NEW - Documentation Hub
│   ├── docs.css                  # NEW - Styling
│   ├── structure.json            # NEW - Documentation links data
│   └── images/                   # NEW - Documentation assets
├── ats/                          # Existing API docs
├── ast/                          # Existing API docs
├── asm/                          # Existing API docs
└── ain/                          # Existing API docs
```

#### Documentation Hub Layout

```
+------------------------------------------------------------------+
|              Asymbl Documentation Portal                         |
|                  Your Single Source of Truth                     |
+------------------------------------------------------------------+
| [ATS] [ASM] [AST] [AIN] [ARA] [ASIN]                           |
+------------------------------------------------------------------+

For Each Product:
┌────────────────────────────────────────────────────────────────┐
│ 📦 ATS - Applicant Tracking System                             │
├────────────────────────────────────────────────────────────────┤
│ 📋 Latest Release: v1.121.3 (December 2025)                   │
│                                                                 │
│ 📖 Release Notes              → [Google Doc Link]             │
│ ⚙️  Pre-Deployment Steps      → [Google Doc Link]             │
│ ⚙️  Post-Deployment Steps     → [Google Doc Link]             │
│ 📘 Technical Documentation    → [Google Doc Link]             │
│ 📗 User Guide                 → [Google Doc Link]             │
│                                                                 │
│ 📚 Release History:                                            │
│    • v1.121.3 (Dec 2025)  - [Release Notes]                   │
│    • v1.121.2 (Nov 2025)  - [Release Notes]                   │
│    • v1.121.1 (Oct 2025)  - [Release Notes]                   │
│    • [View All Releases...]                                    │
└────────────────────────────────────────────────────────────────┘

[Repeat for ASM, AST, AIN, ARA, ASIN]
```

#### Data Structure (structure.json)

```json
{
  "lastUpdated": "2025-12-01",
  "products": [
    {
      "id": "ats",
      "name": "ATS - Applicant Tracking System",
      "description": "Comprehensive applicant tracking and recruiting management",
      "icon": "📦",
      "currentVersion": "1.121.3",
      "releaseDate": "2025-12-01",
      "docs": {
        "releaseNotes": "https://docs.google.com/document/d/...",
        "preDeployment": "https://docs.google.com/document/d/...",
        "postDeployment": "https://docs.google.com/document/d/...",
        "techDoc": "https://docs.google.com/document/d/...",
        "userGuide": "https://docs.google.com/document/d/..."
      },
      "apiDocs": "/ats/ats.html",
      "releaseHistory": [
        {
          "version": "1.121.3",
          "date": "2025-12-01",
          "releaseNotesUrl": "https://docs.google.com/document/d/..."
        },
        {
          "version": "1.121.2",
          "date": "2025-11-01",
          "releaseNotesUrl": "https://docs.google.com/document/d/..."
        }
      ]
    },
    {
      "id": "asm",
      "name": "ASM - Asymbl Search and Match",
      "description": "AI-powered candidate matching and search",
      "icon": "🔍",
      "currentVersion": "0.X.X",
      "releaseDate": "2025-XX-XX",
      "docs": {
        "releaseNotes": "https://docs.google.com/document/d/...",
        "preDeployment": "https://docs.google.com/document/d/...",
        "postDeployment": "https://docs.google.com/document/d/...",
        "techDoc": "https://docs.google.com/document/d/...",
        "userGuide": "https://docs.google.com/document/d/..."
      },
      "apiDocs": "/asm/asm.html",
      "releaseHistory": []
    },
    {
      "id": "ast",
      "name": "AST - Asymbl Time",
      "description": "Timekeeping, payroll, and billing management",
      "icon": "⏱️",
      "currentVersion": "0.X.X",
      "releaseDate": "2025-XX-XX",
      "docs": {
        "releaseNotes": "https://docs.google.com/document/d/...",
        "preDeployment": "https://docs.google.com/document/d/...",
        "postDeployment": "https://docs.google.com/document/d/...",
        "techDoc": "https://docs.google.com/document/d/...",
        "userGuide": "https://docs.google.com/document/d/..."
      },
      "apiDocs": "/ast/ast.html",
      "releaseHistory": []
    },
    {
      "id": "ain",
      "name": "AIN - Asymbl Integration",
      "description": "External system integrations and webhooks",
      "icon": "🔗",
      "currentVersion": "0.37.0",
      "releaseDate": "2025-XX-XX",
      "docs": {
        "releaseNotes": "https://docs.google.com/document/d/...",
        "preDeployment": "https://docs.google.com/document/d/...",
        "postDeployment": "https://docs.google.com/document/d/...",
        "techDoc": "https://docs.google.com/document/d/...",
        "userGuide": "https://docs.google.com/document/d/..."
      },
      "apiDocs": "/ain/ATS_External_Integration_Gui.html",
      "releaseHistory": []
    },
    {
      "id": "ara",
      "name": "ARA - Asymbl Recruiting Agent",
      "description": "AI-powered recruiting assistant with Agentforce",
      "icon": "🤖",
      "currentVersion": "0.26.1",
      "releaseDate": "2025-XX-XX",
      "docs": {
        "releaseNotes": "https://docs.google.com/document/d/...",
        "preDeployment": "https://docs.google.com/document/d/...",
        "postDeployment": "https://docs.google.com/document/d/...",
        "techDoc": "https://docs.google.com/document/d/...",
        "userGuide": "https://docs.google.com/document/d/..."
      },
      "apiDocs": null,
      "releaseHistory": []
    },
    {
      "id": "asin",
      "name": "ASIN - [Product Name]",
      "description": "[Product Description]",
      "icon": "📋",
      "currentVersion": "0.X.X",
      "releaseDate": "2025-XX-XX",
      "docs": {
        "releaseNotes": "https://docs.google.com/document/d/...",
        "preDeployment": "https://docs.google.com/document/d/...",
        "postDeployment": "https://docs.google.com/document/d/...",
        "techDoc": "https://docs.google.com/document/d/...",
        "userGuide": "https://docs.google.com/document/d/..."
      },
      "apiDocs": null,
      "releaseHistory": []
    }
  ]
}
```

#### Features

**Product Cards:**
- Visual grid layout with product icons
- Current version and release date prominently displayed
- Quick access to all 5 documentation types
- Link to API documentation (if available)
- Expandable release history

**Search & Filter:**
- Filter by product
- Search across all documentation titles
- Quick links to latest releases

**Responsive Design:**
- Mobile-friendly layout
- Accessible on tablets and desktops
- Clean, professional styling matching existing site

**Easy Maintenance:**
- Update `structure.json` when releasing new versions
- No code changes required for routine updates
- Automatic deployment via GitHub Pages

#### Benefits

✅ **Single source of truth:** One URL to share with everyone
✅ **Professional presentation:** Branded, organized, accessible
✅ **Non-disruptive:** Keep using Google Docs as you do today
✅ **Immediate value:** Deployed within 1 week
✅ **Easy maintenance:** Update JSON file when releasing new versions
✅ **Scalable foundation:** Sets up structure for Phase 2 migration
✅ **No infrastructure costs:** Uses existing GitHub Pages

#### Implementation Checklist

- [ ] Create `/docs/` directory structure
- [ ] Design and build `index.html` (Documentation Hub)
- [ ] Create `docs.css` with responsive styling
- [ ] Populate `structure.json` with current product data
- [ ] Gather all Google Doc links for each product
- [ ] Add navigation link from main site to documentation hub
- [ ] Test on mobile, tablet, desktop
- [ ] Internal review with team
- [ ] Deploy to GitHub Pages
- [ ] Share new documentation URL with stakeholders

---

### Phase 2: Migrate to Markdown + Git

**Timeline:** 3-6 months
**Effort:** Medium
**Risk:** Low (gradual migration)
**Value:** High (Long-term)

#### Overview
Migrate documentation from Google Docs to Markdown files stored in Git, enabling version control, peer review, and automated publishing.

#### Why Migrate?

**Current Pain Points with Google Docs:**
- ❌ No version control (hard to track changes over time)
- ❌ No review process (anyone can edit, no approval workflow)
- ❌ Difficult to search across all documents
- ❌ No way to automate documentation generation
- ❌ Limited collaboration features for developers
- ❌ Cannot diff changes between versions

**Benefits of Markdown + Git:**
- ✅ **Version Control:** Every change tracked with who/when/why
- ✅ **Review Process:** Pull requests for documentation changes
- ✅ **Search:** Full-text search across all documentation
- ✅ **Automation:** Auto-generate HTML, PDF, or other formats
- ✅ **Developer-Friendly:** Update docs alongside code changes
- ✅ **Diff Support:** See exactly what changed between versions
- ✅ **Backup:** Git provides automatic backup and recovery
- ✅ **Collaboration:** Multiple people can work on docs simultaneously

#### Repository Structure

**Option A: Dedicated Documentation Repository**
```
asymbl-docs/
├── README.md
├── docs/
│   ├── releases/
│   │   ├── ats/
│   │   │   ├── 1.121.3/
│   │   │   │   ├── release-notes.md
│   │   │   │   ├── pre-deployment.md
│   │   │   │   ├── post-deployment.md
│   │   │   │   ├── tech-doc.md
│   │   │   │   └── user-guide.md
│   │   │   ├── 1.121.2/
│   │   │   └── 1.121.1/
│   │   ├── asm/
│   │   │   └── [similar structure]
│   │   ├── ast/
│   │   ├── ain/
│   │   ├── ara/
│   │   └── asin/
│   ├── templates/
│   │   ├── release-notes-template.md
│   │   ├── pre-deployment-template.md
│   │   ├── post-deployment-template.md
│   │   ├── tech-doc-template.md
│   │   └── user-guide-template.md
│   └── guides/
│       ├── documentation-process.md
│       └── markdown-style-guide.md
├── scripts/
│   ├── generate-release-docs.sh
│   ├── validate-links.sh
│   └── publish-to-pages.sh
└── .github/
    └── workflows/
        ├── publish-docs.yml
        ├── validate-links.yml
        └── generate-pdf.yml
```

**Option B: Monorepo with Code (Recommended)**
```
asymbl-integration/ (existing repo)
├── force-app/                     # Salesforce code
├── docs/
│   ├── releases/                  # NEW - Release documentation
│   │   ├── ats/
│   │   ├── asm/
│   │   ├── ast/
│   │   ├── ain/
│   │   ├── ara/
│   │   └── asin/
│   ├── templates/                 # NEW - Documentation templates
│   └── guides/                    # NEW - Process guides
├── .github/workflows/
│   └── publish-docs.yml           # NEW - Auto-publish workflow
└── CLAUDE.md                      # Existing
```

#### Markdown File Structure

**Release Notes Example:**
```markdown
# ATS Release v1.121.3

**Release Date:** December 1, 2025
**Package Version:** 1.121.3
**API Version:** 62.0

## Summary
Brief overview of this release (2-3 sentences).

## New Features
- Feature 1: Description with screenshots
- Feature 2: Description with benefits

## Enhancements
- Enhancement 1: What improved and why
- Enhancement 2: Performance improvements

## Bug Fixes
- BUG-123: Fixed issue with candidate search
- BUG-124: Resolved email template rendering

## Related Documentation
- [Pre-Deployment Steps](./pre-deployment.md)
- [Post-Deployment Steps](./post-deployment.md)
- [Technical Documentation](./tech-doc.md)
- [User Guide](./user-guide.md)

## Support
For questions or issues, contact support@asymbl.com
```

**Pre-Deployment Steps Example:**
```markdown
# ATS Pre-Deployment Steps

**Last Updated:** December 1, 2025 (v1.121.3)

## Overview
Steps to complete BEFORE deploying ATS to production.

## Prerequisites
- [ ] Salesforce admin access
- [ ] Backup current configuration
- [ ] Review release notes

## Steps

### 1. Create Custom Fields
Navigate to Setup → Object Manager → Contact

| Field Name | Type | Required | Description |
|------------|------|----------|-------------|
| Resume_Score__c | Number(3,0) | No | AI-generated resume score |
| Skills_Match__c | Percent | No | % match to job requirements |

### 2. Update Permission Sets
Grant new permissions to ATS users:
- Read/Write access to `Resume_Score__c`
- Read access to `Skills_Match__c`

[Screenshot: Permission Set Configuration]

### 3. Configure Custom Settings
Update ATS Settings with new API endpoints...

## Validation
After completing pre-deployment steps:
- [ ] Verify custom fields are accessible
- [ ] Test permission sets with test user
- [ ] Validate custom settings values

## Rollback Plan
If issues occur during deployment, follow rollback procedure in [Emergency Rollback Guide](../guides/rollback.md).
```

#### GitHub Actions Automation

**Auto-Publish Workflow:**
```yaml
name: Publish Documentation

on:
  push:
    branches: [master]
    paths:
      - 'docs/**'

jobs:
  publish:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3

      - name: Convert Markdown to HTML
        run: |
          npm install -g markdown-to-html
          ./scripts/generate-html.sh

      - name: Generate PDFs
        run: |
          npm install -g md-to-pdf
          ./scripts/generate-pdfs.sh

      - name: Deploy to GitHub Pages
        uses: peaceiris/actions-gh-pages@v3
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          publish_dir: ./build
```

**Link Validation Workflow:**
```yaml
name: Validate Documentation Links

on:
  pull_request:
    paths:
      - 'docs/**'

jobs:
  validate:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3

      - name: Check for broken links
        run: |
          npm install -g markdown-link-check
          find docs -name '*.md' -exec markdown-link-check {} \;

      - name: Validate formatting
        run: |
          npm install -g markdownlint-cli
          markdownlint 'docs/**/*.md'
```

#### Migration Strategy

**Step-by-Step Migration:**

1. **Pilot with One Product (Week 1-2)**
   - Choose ATS as pilot product
   - Convert most recent release (v1.121.3) to Markdown
   - Test Git workflow with team
   - Gather feedback and refine process

2. **Migrate Recent Releases (Week 3-4)**
   - Convert last 3 releases for ATS
   - Set up GitHub Actions automation
   - Train team on Markdown editing

3. **Expand to Other Products (Month 2-3)**
   - Roll out to ASM, AST, AIN
   - Convert recent releases (last 3 months)
   - Continue using Google Docs for older archives

4. **Full Migration (Month 4-6)**
   - Migrate remaining products (ARA, ASIN)
   - Archive old Google Docs (read-only)
   - Update all links to point to new documentation

**Parallel Operation:**
- Keep Google Docs active during migration
- New releases use Markdown immediately
- Gradually migrate older releases as time permits

#### Documentation Workflow (Post-Migration)

```
┌──────────────────────────────────────────────────────────┐
│ Developer completes feature for ATS v1.122.0             │
└──────────────────┬───────────────────────────────────────┘
                   │
                   ▼
┌──────────────────────────────────────────────────────────┐
│ Create new release docs from templates:                  │
│ $ npm run create-release -- --product=ats --version=1.122│
└──────────────────┬───────────────────────────────────────┘
                   │
                   ▼
┌──────────────────────────────────────────────────────────┐
│ Edit Markdown files:                                     │
│ - docs/releases/ats/1.122.0/release-notes.md             │
│ - docs/releases/ats/1.122.0/pre-deployment.md            │
│ - Update docs/releases/ats/1.122.0/tech-doc.md          │
└──────────────────┬───────────────────────────────────────┘
                   │
                   ▼
┌──────────────────────────────────────────────────────────┐
│ Create Pull Request:                                     │
│ - GitHub Actions validate links and formatting           │
│ - Team reviews documentation changes                     │
│ - Make revisions based on feedback                       │
└──────────────────┬───────────────────────────────────────┘
                   │
                   ▼
┌──────────────────────────────────────────────────────────┐
│ Merge PR → Auto-publish:                                 │
│ - Generate HTML for web viewing                          │
│ - Create PDFs for customer distribution                  │
│ - Update documentation hub (Phase 1 site)                │
│ - Deploy to asymblinc.github.io/docs/                    │
└──────────────────────────────────────────────────────────┘
```

#### Team Training

**Week 1: Markdown Basics**
- Markdown syntax overview (headings, lists, tables, links)
- VS Code setup with Markdown preview
- Practice editing sample documents

**Week 2: Git Workflow**
- Creating branches for documentation updates
- Making commits with clear messages
- Opening pull requests and requesting reviews

**Week 3: Process Integration**
- Using documentation templates
- Running validation scripts locally
- Reviewing and approving documentation PRs

**Ongoing Support:**
- Quick reference guide in repository
- Slack channel for documentation questions
- Monthly documentation review meetings

#### Success Metrics

**Quality Improvements:**
- Documentation review cycle time < 2 days
- Zero broken links in published documentation
- 100% of releases have complete documentation

**Efficiency Gains:**
- Time to publish documentation reduced by 50%
- Documentation update errors reduced by 80%
- Team satisfaction with documentation process increases

---

### Phase 3: Smart Documentation Automation

**Timeline:** 6-12 months
**Effort:** High
**Risk:** Medium
**Value:** Very High (Long-term)

#### Overview
Use AI (Claude Code agents) to automatically generate draft documentation from code changes, reducing manual documentation effort by 40-60%.

#### Auto-Generation Capabilities

**1. Release Notes Generation**
```
Code Changes Analyzed → AI-Generated Draft → Human Review → Published
```

**What can be auto-detected:**
- New Apex classes and methods
- New Lightning Web Components
- New custom fields and objects
- Modified flows and process builders
- Updated permission sets
- API endpoint changes
- Dependency updates

**Example AI-generated content:**
```markdown
## New Features

### AI-Powered Candidate Scoring
This release introduces intelligent candidate scoring with the new
`ATS_CandidateScoreService` Apex class. The service analyzes resumes
against job requirements and provides a match percentage.

**New Components:**
- `ATS_CandidateScoreService.cls` - Main scoring logic
- `ATS_CandidateScoreServiceTest.cls` - Test coverage (96%)
- `Resume_Score__c` field on Contact object
- `Skills_Match__c` field on Contact object

**Usage:**
Candidate scores are automatically calculated when a resume is uploaded.
Recruiters can view scores in the Candidate Detail page.

[Auto-detected from Git diff: +523 lines, -12 lines]
```

**2. Pre/Post-Deployment Steps Detection**

**AI analyzes metadata changes:**
```
New Custom Fields → "Create custom fields before deployment"
New Permission Sets → "Grant permissions to user profiles"
New Custom Metadata → "Configure settings in Custom Metadata"
Flow Changes → "Deactivate flows before deployment"
```

**Auto-generated Pre-Deployment Steps:**
```markdown
## Pre-Deployment Steps (Auto-Generated)

### 1. Create Custom Fields
The following fields must be created manually before deployment:

**Contact Object:**
- `Resume_Score__c` (Number, 3, 0) - Stores AI-generated resume score
- `Skills_Match__c` (Percent) - Percentage match to job requirements

**Detected from:** force-app/main/default/objects/Contact/fields/

### 2. Update Permission Sets
Grant the following permissions to ATS users:

**ATS_Recruiter Permission Set:**
- Read/Write access to `Resume_Score__c`
- Read access to `Skills_Match__c`

**Detected from:** force-app/main/default/permissionsets/ATS_Recruiter.permissionset-meta.xml
```

**3. Technical Documentation Updates**

**AI analyzes code and generates:**
- API endpoint documentation
- Method signatures and descriptions
- Field definitions and relationships
- Integration requirements

**Example auto-generated API docs:**
```markdown
## New API Endpoints (v1.122.0)

### POST /services/apexrest/ATS/CandidateScore

**Description:** Calculate candidate scoring for resume matching.

**Request:**
```json
{
  "contactId": "003xx000004TmiQ",
  "jobId": "a00xx000001234X"
}
```

**Response:**
```json
{
  "score": 85,
  "matchPercentage": 85.5,
  "keySkillsMatched": ["Java", "Salesforce", "Agile"],
  "missingSkills": ["Python"]
}
```

**Authentication:** Required (OAuth 2.0)
**Permissions:** Requires ATS_Recruiter permission set

**Detected from:** force-app/main/default/classes/ATS_CandidateScoreAPI.cls
```

#### Implementation Architecture

**Claude Code Agent Setup:**

```
.claude/agents/
├── doc-generator.md              # Main orchestration agent
├── release-notes-generator.md    # Release notes specialist
├── deployment-steps-analyzer.md  # Pre/post deployment detector
└── tech-doc-updater.md           # Technical documentation specialist
```

**Workflow:**

```
┌─────────────────────────────────────────────────────────────┐
│ Developer completes feature development                     │
│ $ git commit -m "Add candidate scoring feature"             │
└────────────────────┬────────────────────────────────────────┘
                     │
                     ▼
┌─────────────────────────────────────────────────────────────┐
│ Trigger documentation generation:                           │
│ $ npm run generate-docs -- --product=ats --version=1.122.0  │
└────────────────────┬────────────────────────────────────────┘
                     │
                     ▼
┌─────────────────────────────────────────────────────────────┐
│ Claude Agent analyzes Git diff:                             │
│ - New files: ATS_CandidateScoreService.cls                  │
│ - Modified files: ATS_CandidateController.cls               │
│ - New fields: Resume_Score__c, Skills_Match__c              │
│ - Updated permission sets: ATS_Recruiter                    │
└────────────────────┬────────────────────────────────────────┘
                     │
                     ▼
┌─────────────────────────────────────────────────────────────┐
│ Generate draft documentation:                               │
│ ✓ Release notes (70% complete)                              │
│ ✓ Pre-deployment steps (90% complete)                       │
│ ✓ Post-deployment steps (80% complete)                      │
│ ✓ Tech doc updates (85% complete)                           │
│ ✓ User guide sections (60% complete)                        │
└────────────────────┬────────────────────────────────────────┘
                     │
                     ▼
┌─────────────────────────────────────────────────────────────┐
│ Create documentation PR:                                    │
│ - Branch: docs/ats-1.122.0                                  │
│ - Files: 5 Markdown documents created/updated               │
│ - Status: Ready for human review                            │
└────────────────────┬────────────────────────────────────────┘
                     │
                     ▼
┌─────────────────────────────────────────────────────────────┐
│ Human review and refinement:                                │
│ - Verify technical accuracy                                 │
│ - Add context and business value                            │
│ - Include customer-facing language                          │
│ - Add screenshots and examples                              │
└────────────────────┬────────────────────────────────────────┘
                     │
                     ▼
┌─────────────────────────────────────────────────────────────┐
│ Approve and merge → Auto-publish                            │
│ Documentation available within minutes                      │
└─────────────────────────────────────────────────────────────┘
```

#### Example CLI Commands

**Generate full release documentation:**
```bash
$ npm run generate-docs -- --product=ats --version=1.122.0
✓ Analyzing Git changes since last release...
✓ Detected 15 modified files, 5 new classes, 3 new fields
✓ Generating release notes...
✓ Analyzing deployment requirements...
✓ Updating technical documentation...
✓ Creating documentation PR...

Documentation PR created: https://github.com/asymbl/docs/pull/123
Review the generated documentation and merge when ready.
```

**Generate specific documentation type:**
```bash
$ npm run generate-release-notes -- --product=ats --version=1.122.0
$ npm run generate-deployment-steps -- --product=ats --version=1.122.0
$ npm run update-tech-docs -- --product=ats --version=1.122.0
```

**Update documentation for specific commit range:**
```bash
$ npm run generate-docs -- --product=ats --from=v1.121.3 --to=HEAD
```

#### Human-in-the-Loop Approach

**AI Strengths:**
- ✅ Detect structural changes (new classes, fields, objects)
- ✅ Extract method signatures and technical details
- ✅ Identify deployment requirements
- ✅ Generate consistent formatting
- ✅ Cross-reference related documentation

**Human Judgment Required:**
- 🔍 Business context and customer value
- 🔍 User-facing language and clarity
- 🔍 Priority and impact assessment
- 🔍 Screenshots and visual examples
- 🔍 Known issues and workarounds
- 🔍 Migration strategies for breaking changes

**Recommended Split:**
- **AI generates 70-80%** of initial draft
- **Humans refine 20-30%** with context and polish
- **Final review** by technical writer or product manager

#### Integration with Development Workflow

**Pre-Commit Hook:**
```bash
# .git/hooks/pre-commit
#!/bin/bash

# Check if significant changes warrant documentation update
CHANGED_FILES=$(git diff --cached --name-only)

if echo "$CHANGED_FILES" | grep -q "force-app/main/default/classes"; then
  echo "⚠️  Apex classes modified. Consider running:"
  echo "   npm run generate-docs -- --product=ats"
fi

if echo "$CHANGED_FILES" | grep -q "force-app/main/default/objects"; then
  echo "⚠️  Objects/fields modified. Update deployment steps:"
  echo "   npm run generate-deployment-steps -- --product=ats"
fi
```

**Pull Request Checks:**
```yaml
# .github/workflows/check-docs.yml
name: Check Documentation Updates

on:
  pull_request:
    branches: [master, main]

jobs:
  check-docs:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3

      - name: Check if documentation needs update
        run: |
          # Analyze code changes
          CHANGED_APEX=$(git diff origin/master...HEAD --name-only | grep "\.cls$" | wc -l)
          CHANGED_OBJECTS=$(git diff origin/master...HEAD --name-only | grep "/objects/" | wc -l)

          # Check if documentation was updated
          CHANGED_DOCS=$(git diff origin/master...HEAD --name-only | grep "^docs/" | wc -l)

          if [ "$CHANGED_APEX" -gt 5 ] || [ "$CHANGED_OBJECTS" -gt 2 ]; then
            if [ "$CHANGED_DOCS" -eq 0 ]; then
              echo "⚠️  Significant code changes detected but no documentation updates."
              echo "Consider running: npm run generate-docs"
              exit 1
            fi
          fi
```

#### Expected Efficiency Gains

**Time Savings:**
| Documentation Type | Manual Effort | AI-Assisted Effort | Time Saved |
|--------------------|---------------|-------------------|------------|
| Release Notes | 2-3 hours | 30-45 minutes | ~70% |
| Pre-Deployment Steps | 1-2 hours | 15-30 minutes | ~75% |
| Post-Deployment Steps | 1-2 hours | 15-30 minutes | ~75% |
| Technical Documentation | 3-4 hours | 1-1.5 hours | ~65% |
| User Guide Updates | 2-3 hours | 45-60 minutes | ~60% |
| **Total per Release** | **9-14 hours** | **3-5 hours** | **~65%** |

**Per Year (12 releases × 6 products):**
- Manual approach: ~648-1,008 hours
- AI-assisted approach: ~216-360 hours
- **Time saved: ~432-648 hours per year**

**Quality Improvements:**
- Fewer missing documentation items
- Consistent formatting across products
- Better cross-referencing between documents
- Reduced human error in technical details
- Faster documentation delivery

#### Success Metrics

**Automation Coverage:**
- % of documentation auto-generated
- % of release notes requiring minimal human editing
- % of deployment steps automatically detected

**Quality Metrics:**
- Documentation completeness score
- Time from code commit to documentation publish
- Number of documentation errors reported

**Team Satisfaction:**
- Developer satisfaction with documentation process
- Time spent on documentation per release
- Number of documentation-related support tickets

---

## Implementation Plan

### Phase 1 Implementation (Week-by-Week)

#### Week 1: Setup and Design
- [x] Review proposal with team
- [ ] Gather all product information (versions, Google Doc links)
- [ ] Create project structure in `asymblinc.github.io`
- [ ] Design documentation hub layout
- [ ] Create wireframes for review

#### Week 2: Development
- [ ] Build `docs/index.html` with product cards
- [ ] Create `docs/docs.css` with responsive styling
- [ ] Implement search/filter functionality
- [ ] Create `structure.json` data file
- [ ] Test on multiple devices/browsers

#### Week 3: Content Population
- [ ] Populate `structure.json` with all product data
- [ ] Add all Google Doc links for current releases
- [ ] Gather release history for each product
- [ ] Add product descriptions and icons
- [ ] Test all links

#### Week 4: Testing and Launch
- [ ] Internal testing with team
- [ ] Gather feedback and make revisions
- [ ] Final QA (links, formatting, mobile)
- [ ] Deploy to GitHub Pages
- [ ] Announce new documentation hub
- [ ] Update bookmarks and shared links

### Phase 2 Migration Plan (Monthly)

#### Month 1: Pilot Setup
- [ ] Choose pilot product (ATS)
- [ ] Set up documentation repository structure
- [ ] Create Markdown templates
- [ ] Convert ATS v1.121.3 to Markdown
- [ ] Test Git workflow with team

#### Month 2: Automation Setup
- [ ] Set up GitHub Actions for publishing
- [ ] Create link validation workflow
- [ ] Implement PDF generation
- [ ] Train team on Markdown and Git
- [ ] Convert last 3 ATS releases

#### Month 3-4: Expand to More Products
- [ ] Migrate ASM documentation
- [ ] Migrate AST documentation
- [ ] Migrate AIN documentation
- [ ] Refine processes based on learnings

#### Month 5-6: Complete Migration
- [ ] Migrate ARA documentation
- [ ] Migrate ASIN documentation
- [ ] Archive old Google Docs (read-only)
- [ ] Update all documentation links
- [ ] Celebrate completion! 🎉

### Phase 3 Automation Plan (Quarterly)

#### Q1: Foundation
- [ ] Design AI agent architecture
- [ ] Create Claude Code agents for doc generation
- [ ] Build CLI commands for documentation generation
- [ ] Test on small feature releases

#### Q2: Integration
- [ ] Integrate with development workflow
- [ ] Add pre-commit hooks
- [ ] Create PR checks for documentation
- [ ] Train team on AI-assisted documentation

#### Q3: Refinement
- [ ] Analyze automation effectiveness
- [ ] Improve AI prompts based on feedback
- [ ] Expand coverage to more document types
- [ ] Optimize generation speed

#### Q4: Production
- [ ] Full rollout to all products
- [ ] Measure time savings and quality improvements
- [ ] Continuous improvement based on metrics
- [ ] Document best practices

---

## Process Documentation

### New Release Documentation Process (Phase 1)

**When releasing a new version:**

1. **Update Google Docs** (as usual)
   - Create new release notes document
   - Update pre-deployment steps (if needed)
   - Update post-deployment steps (if needed)
   - Update technical documentation
   - Update user guide

2. **Update Documentation Hub** (30 seconds)
   - Open `docs/structure.json`
   - Find your product section
   - Update `currentVersion` and `releaseDate`
   - Update `docs.releaseNotes` with new Google Doc link
   - Add new entry to `releaseHistory` array
   - Save and commit

3. **Publish** (automatic)
   - Push to GitHub
   - GitHub Pages auto-deploys within 1-2 minutes
   - Documentation hub is updated!

**Example update:**
```json
{
  "id": "ats",
  "currentVersion": "1.122.0",  // Changed from 1.121.3
  "releaseDate": "2025-01-15",  // Changed from 2025-12-01
  "docs": {
    "releaseNotes": "https://docs.google.com/document/d/NEW_LINK_HERE",  // New link
    "preDeployment": "https://docs.google.com/document/d/...",  // Same (living doc)
    "postDeployment": "https://docs.google.com/document/d/...",  // Same (living doc)
    "techDoc": "https://docs.google.com/document/d/...",  // Same (living doc)
    "userGuide": "https://docs.google.com/document/d/..."  // Same (living doc)
  },
  "releaseHistory": [
    {
      "version": "1.122.0",  // NEW ENTRY
      "date": "2025-01-15",
      "releaseNotesUrl": "https://docs.google.com/document/d/NEW_LINK_HERE"
    },
    {
      "version": "1.121.3",  // Previous release
      "date": "2025-12-01",
      "releaseNotesUrl": "https://docs.google.com/document/d/..."
    }
    // ... older releases
  ]
}
```

### New Release Documentation Process (Phase 2)

**When releasing a new version:**

1. **Create documentation branch**
   ```bash
   git checkout -b docs/ats-1.122.0
   ```

2. **Generate documentation from templates**
   ```bash
   npm run create-release -- --product=ats --version=1.122.0
   ```
   This creates:
   - `docs/releases/ats/1.122.0/release-notes.md` (from template)
   - `docs/releases/ats/1.122.0/pre-deployment.md` (from template)
   - `docs/releases/ats/1.122.0/post-deployment.md` (from template)
   - Updates `docs/releases/ats/1.122.0/tech-doc.md`
   - Updates `docs/releases/ats/1.122.0/user-guide.md`

3. **Edit Markdown files**
   - Open files in VS Code
   - Fill in release details
   - Add screenshots, examples
   - Use Markdown preview to check formatting

4. **Commit and create PR**
   ```bash
   git add docs/
   git commit -m "Add documentation for ATS v1.122.0"
   git push origin docs/ats-1.122.0
   ```
   - Open PR on GitHub
   - Request review from team
   - GitHub Actions will validate links and formatting

5. **Review and merge**
   - Team reviews documentation
   - Make revisions based on feedback
   - Merge PR when approved

6. **Auto-publish** (automatic)
   - GitHub Actions converts Markdown to HTML
   - Generates PDF versions
   - Updates documentation hub
   - Deploys to GitHub Pages

### New Release Documentation Process (Phase 3)

**When releasing a new version:**

1. **Complete feature development**
   ```bash
   git add .
   git commit -m "Add candidate scoring feature"
   ```

2. **Generate documentation automatically**
   ```bash
   npm run generate-docs -- --product=ats --version=1.122.0
   ```
   Claude agent:
   - Analyzes Git diff since last release
   - Detects new classes, fields, objects
   - Generates draft documentation (70-80% complete)
   - Creates documentation PR automatically

3. **Review AI-generated documentation**
   - Open documentation PR on GitHub
   - Review auto-generated content
   - Add business context and customer value
   - Include screenshots and examples
   - Make any necessary corrections

4. **Approve and publish**
   - Merge PR when satisfied
   - Documentation auto-publishes within minutes

**Time saved: ~6-9 hours per release!**

---

## Success Metrics

### Phase 1 Success Criteria

**Adoption Metrics:**
- [ ] Documentation hub receives 100+ views per week
- [ ] 90% of team uses hub as primary documentation source
- [ ] Documentation links shared externally use hub URL

**Quality Metrics:**
- [ ] Zero broken links in documentation hub
- [ ] Mobile-friendly score: 95+ (Google PageSpeed)
- [ ] All products have complete documentation links

**Maintenance Metrics:**
- [ ] Time to update hub: < 5 minutes per release
- [ ] Hub updated within 24 hours of each release
- [ ] Team satisfaction: 8+ out of 10

### Phase 2 Success Criteria

**Migration Progress:**
- [ ] 100% of new releases use Markdown
- [ ] Last 6 months of releases migrated for all products
- [ ] Google Docs archived (read-only)

**Process Improvements:**
- [ ] Documentation PR cycle time: < 2 days
- [ ] Zero documentation errors reported
- [ ] 100% of releases have complete documentation

**Team Efficiency:**
- [ ] Time to create documentation: reduced by 30%
- [ ] Documentation quality score: 8+ out of 10
- [ ] Team prefers Markdown over Google Docs

### Phase 3 Success Criteria

**Automation Coverage:**
- [ ] 70%+ of documentation auto-generated
- [ ] 90%+ of deployment steps auto-detected
- [ ] 60%+ of release notes require minimal editing

**Time Savings:**
- [ ] Documentation time per release: < 4 hours (was 10+ hours)
- [ ] Total time saved: 400+ hours per year
- [ ] ROI: 10x return on AI tool investment

**Quality Improvements:**
- [ ] Documentation completeness: 100%
- [ ] Technical accuracy: 95%+
- [ ] Customer satisfaction with docs: 9+ out of 10

---

## Next Steps

### Immediate Actions (This Week)

1. **Review and Approve Phase 1 Plan**
   - Review this strategy document
   - Gather feedback from team
   - Approve proceeding with Phase 1 implementation

2. **Collect Product Information**
   - Product names and current versions
   - Google Doc links for all documentation
   - Release history for each product
   - Product descriptions and use cases

3. **Assign Responsibilities**
   - Who will maintain the documentation hub?
   - Who will update `structure.json` for releases?
   - Who will review documentation changes?

### Decision Points

**Required Decisions:**
- [ ] Approve Phase 1 implementation (Documentation Hub)
- [ ] Confirm product list and priorities
- [ ] Select date for internal launch
- [ ] Identify team members for documentation ownership

**Optional Decisions (for later):**
- [ ] Commit to Phase 2 migration timeline
- [ ] Allocate budget for Phase 3 AI automation
- [ ] Define documentation quality standards

### Questions to Answer

1. **Product Information:**
   - What are the full names and current versions of all 6 products?
   - Are there any products that should be prioritized?

2. **Access Control:**
   - Are Google Docs public or private?
   - Should documentation hub be public or require authentication?

3. **Branding:**
   - Should documentation hub match existing site styling?
   - Any specific color schemes or branding requirements?

4. **Team:**
   - Who will be the documentation hub maintainer(s)?
   - Who has authority to approve documentation changes?

5. **Timeline:**
   - When is your next release?
   - What's the target date for Phase 1 launch?

---

## Appendix

### Resources

**Markdown Resources:**
- [Markdown Guide](https://www.markdownguide.org/)
- [GitHub Flavored Markdown Spec](https://github.github.com/gfm/)
- [VS Code Markdown Extensions](https://marketplace.visualstudio.com/items?itemName=yzhang.markdown-all-in-one)

**GitHub Pages:**
- [GitHub Pages Documentation](https://docs.github.com/en/pages)
- [Jekyll Documentation](https://jekyllrb.com/docs/) (optional static site generator)

**Documentation Tools:**
- [MkDocs](https://www.mkdocs.org/) - Markdown documentation site generator
- [Docusaurus](https://docusaurus.io/) - Modern documentation framework
- [GitBook](https://www.gitbook.com/) - Documentation platform

**AI/Automation:**
- [Claude Code](https://claude.ai/code) - AI-powered development assistant
- [GitHub Actions](https://docs.github.com/en/actions) - Workflow automation

### Sample Templates

**Release Notes Template:**
```markdown
# [Product] Release v[Version]

**Release Date:** [Date]
**Package Version:** [Version]
**API Version:** [API Version]

## Summary
[2-3 sentence overview of this release]

## New Features
- **[Feature Name]:** Description
  - Benefit 1
  - Benefit 2
  - [Screenshot or demo]

## Enhancements
- **[Enhancement Name]:** What improved and why

## Bug Fixes
- **[TICKET-ID]:** Description of fix

## Related Documentation
- [Pre-Deployment Steps](./pre-deployment.md)
- [Post-Deployment Steps](./post-deployment.md)
- [Technical Documentation](./tech-doc.md)
- [User Guide](./user-guide.md)

## Support
For questions or issues, contact [support email/link]
```

**Pre-Deployment Steps Template:**
```markdown
# [Product] Pre-Deployment Steps

**Last Updated:** [Date] (v[Version])

## Overview
Steps to complete BEFORE deploying [Product] to production.

## Prerequisites
- [ ] [Prerequisite 1]
- [ ] [Prerequisite 2]

## Steps

### 1. [Step Name]
[Detailed instructions]

| Field/Config | Value | Required | Notes |
|--------------|-------|----------|-------|
| [Field] | [Value] | Yes/No | [Notes] |

[Screenshot if helpful]

### 2. [Step Name]
[Detailed instructions]

## Validation
After completing pre-deployment steps:
- [ ] [Validation check 1]
- [ ] [Validation check 2]

## Rollback Plan
If issues occur, follow [Emergency Rollback Guide](../guides/rollback.md).
```

### FAQ

**Q: Will this replace our Google Docs?**
A: Phase 1 keeps Google Docs intact. Phase 2 gradually migrates to Markdown, but only when the team is ready.

**Q: How much time will this save?**
A: Phase 1 saves ~5-10 minutes per release lookup. Phase 2 saves ~30% documentation time. Phase 3 saves ~65% documentation time.

**Q: What if the team doesn't like Markdown?**
A: Phase 1 doesn't require Markdown. We can stay there indefinitely if preferred. Phase 2 is optional.

**Q: How do we maintain this long-term?**
A: Phase 1 requires updating a JSON file (30 seconds). Phase 2 uses Git (same as code). Phase 3 is mostly automated.

**Q: What about historical documentation?**
A: Phase 1 links to existing docs. Phase 2 gradually migrates recent releases. Old docs stay in Google Docs as archives.

**Q: Can customers access this?**
A: Yes! GitHub Pages is public. You can also make it private with GitHub Enterprise.

**Q: What if GitHub Pages goes down?**
A: GitHub Pages has 99.9% uptime. We can also export to S3/CloudFront as backup.

---

## Contact

For questions about this strategy:
- **Author:** Claude Code
- **Date:** December 1, 2025
- **Version:** 1.0.0

**Next Review:** After Phase 1 completion

---

*This document is part of the Asymbl Documentation Centralization Initiative.*
