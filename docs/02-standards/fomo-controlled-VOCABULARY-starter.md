# FOMO Controlled Vocabulary - Core Starter Set

This starter set provides foundational terms for the FOMO system, organised by category. Each term follows the appropriate formatting convention and includes usage guidance.

## Level 1 Terms (Top-level Folders)

These terms use capitalised, single-word format following macOS conventions:

| Term | Definition | Usage Context | Related Terms |
|------|------------|---------------|--------------|
| Projects | Container for active creation work | Top-level directory for all current creative and development work | Development, Design |
| Resources | Supportive materials used across projects | Top-level directory for assets, templates, and reference materials | Assets, Templates, Reference |
| Knowledge | Information collection and management | Top-level directory for notes, documentation, and research | Documentation, Notes, Research |
| System | Computer configuration and management | Top-level directory for configs, scripts, and maintenance tools | Configuration, Automation, Maintenance |
| Downloads | Managed download location | Standard macOS folder for incoming files | Inbox, Processing, Archive |

## Level 2+ Terms (Nested Folders)

These terms use lowercase kebab-case format:

### Project-related Terms

| Term | Definition | Usage Context | Related Terms |
|------|------------|---------------|--------------|
| design | Design-focused project work | Second-level folder within Projects | client, personal |
| dev | Development-focused project work | Second-level folder within Projects | web, app, automation |
| client | Client-commissioned work | Third-level folder descriptor | project-name |
| personal | Self-initiated creative work | Third-level folder descriptor | project-name |
| archive | Completed projects for reference | Subfolder for inactive but valuable work | completed |

### Resource-related Terms

| Term | Definition | Usage Context | Related Terms |
|------|------------|---------------|--------------|
| assets | Design elements and media | Second-level folder within Resources | fonts, icons, images |
| templates | Starting points for new work | Second-level folder within Resources | boilerplate, starter |
| reference | Information consulted but rarely modified | Second-level folder within Resources | guides, documentation |
| fonts | Typography resources | Third-level folder within assets | typography |
| icons | Icon libraries and collections | Third-level folder within assets | graphics, ui |

### Knowledge-related Terms

| Term | Definition | Usage Context | Related Terms |
|------|------------|---------------|--------------|
| docs | Formal documentation | Second-level folder within Knowledge | manuals, specifications |
| notes | Personal information and insights | Second-level folder within Knowledge | journal, ideas |
| research | Collected information for analysis | Second-level folder within Knowledge | findings, data |
| vault | Personal knowledge management system | Second-level folder within Knowledge | obsidian, notes |

### System-related Terms

| Term | Definition | Usage Context | Related Terms |
|------|------------|---------------|--------------|
| configs | Configuration files and settings | Second-level folder within System | settings, preferences |
| scripts | Automation code and utilities | Second-level folder within System | automation, utilities |
| search | Saved searches and smart folders | Second-level folder within System | queries, filters |

## Status/Workflow Terms

These terms indicate state or stage in workflow processes:

| Term | Definition | Usage Context | Related Terms |
|------|------------|---------------|--------------|
| draft | Initial or work-in-progress version | File status indicator | in-progress, wip |
| review | Ready for feedback or evaluation | File status indicator | feedback, critique |
| approved | Signed off by client or team | File status indicator | final, accepted |
| archived | Final version for record-keeping | File status indicator | complete, inactive |
| active | Currently being worked on | Project or task status | current, in-progress |
| todo | Requires action | Task status indicator | pending, action |

## Temporal/Versioning Terms

These terms relate to time or version control:

| Term | Definition | Usage Context | Related Terms |
|------|------------|---------------|--------------|
| current | In active use | Temporal folder descriptor | active, latest |
| legacy | Outdated but preserved | Temporal folder descriptor | old, previous |
| v## | Version number with leading zeros | Version indicator (e.g., v01, v02) | revision |

## Implementation Notes

1. This starter set includes approximately 25 core terms that form the foundation of the FOMO system vocabulary.

2. When implementing this vocabulary:
   - Use Level 1 terms exactly as shown for top-level directories
   - Combine Level 2+ terms as needed using hyphens for compound concepts (e.g., `client-project`)
   - Apply status/workflow terms as suffixes with hyphens (e.g., `website-draft`)
   - Apply temporal terms as prefixes with hyphens (e.g., `legacy-configs`)

3. For tagging applications:
   - Use the same terms without capitalisation
   - Apply as individual tags rather than compound terms where possible
   - Example: For a client project draft, use tags `#client` + `#project` + `#draft` rather than `#client-project-draft`

4. This starter set will be expanded during implementation, focusing first on your primary work domains (design and development).
