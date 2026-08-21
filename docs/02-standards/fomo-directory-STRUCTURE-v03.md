# FOMO Directory Structure v03

## 1. Introduction

### 1.1 Purpose

This document establishes the directory structure for the File Organisation, Management & Optimisation (FOMO) project. It provides a structured framework for organising files and directories in a way that balances human usability with machine processing, while addressing the specific needs of design, development, and personal workflows.

### 1.2 Scope

These directory structure guidelines apply to:

- Personal computing environment across multiple machines
- Design projects and assets (including fonts, mockups, and client deliverables)
- Development projects and repositories
- Knowledge management resources
- System configuration and settings
- Cloud-synced and locally-stored files

### 1.3 Benefits

Implementing this directory structure will:

- Reduce folder depth and navigation complexity
- Centralise resources for easier discovery and access
- Create a consistent organisational approach across different machines
- Enable efficient command-line and GUI navigation
- Establish clear separation of concerns between different file types
- Support both cloud synchronisation and local optimisation
- Simplify backup and maintenance procedures
- Enhance automation capabilities for file management

### 1.4 Implementation Overview

This restructuring includes:

- **4 new top-level folders** at the home directory level: `~/Projects/`, `~/Resources/`, `~/Knowledge/` & `~/System/`
- **9 total symlinks** pointed from cloud storage to local directories
    - 2x existing iCloud symlinks: `Desktop/`, `Documents/`
    - 2x new iCloud symlinks: `Downloads/`, `Obsidian/`
    - 5x Dropbox symlinks: `Assets/`, `Inspirations/`, `References/`, `Education/` & `Projects/`
- **Additional backups** to be established, ensuring all information is either cloud-sourced or backed up

## 2. Core Principles

### 2.1 Logical Coherence

The directory structure should reflect conceptual relationships between files and their purposes, not merely their technical attributes.

### 2.2 Appropriate Depth

Limit directory nesting to 3-4 levels when possible to reduce navigation complexity and path length.

### 2.3 Separation of Concerns

Distinguish between different functional areas (projects, resources, knowledge, system) to clarify purpose and reduce cognitive load.

### 2.4 Physical vs Logical Distinction

Maintain a separation between physical storage locations (where files exist on disk or in cloud services) and logical organisation (how they appear to users and applications).

### 2.5 Cloud-Local Harmony

Ensure seamless integration between cloud-synced and locally-stored files while preserving appropriate separation.

### 2.6 Balancing Access vs Organisation

Organise by access frequency and relation rather than strict hierarchical taxonomies, placing frequently-accessed items closer to the top level.

### 2.7 Naming Convention Adherence

Apply consistent naming conventions throughout the filesystem structure:

- Always complete folder renaming in cloud locations *before* working on local folders.
- Use standardised naming formats based on level:
    - Top-level folders (level 1): One-word with capitalisation, following macOS convention (e.g., `Projects`, `Resources`).
    - Nested folders (level 2+): All lowercase preferred one-word (e.g., `archive`,`config`) use hyphens as separators when necessary (e.g., `archive-branding`, `env-path`).
    - Refer to `Controlled Vocabulary` document for the standard terminology list.
- Make exceptions for top-level project and client folders, and domain-specific edge cases (e.g. font folders).

### 2.8 Backup Strategy

Ensure data protection through a thorough backup approach:

- Prioritise cloud storage for active files
- Back up any locally-stored content not in cloud services
- Use Time Machine for system-wide protection
- Implement Git repositories for code and configuration files
- Consider regular pushes to remote repositories (e.g., GitHub) or including local repositories in Time Machine backups.
- Maintain at least 4 backups to ensure all information is either cloud-sourced or backed up

## 3. Conceptual Framework

### 3.1 Assets vs Catalogues

A fundamental distinction in the FOMO system is between assets (the files themselves) and catalogues (the organisational systems):

- **Assets**: The original files and content (e.g. images, documents, code)
- **Catalogues**: Systems that organise, index, and provide access to assets

This separation allows a single asset to be accessed through multiple organisational views without duplication. For example:

- A font file is an asset stored once physically
- It may appear in multiple catalogue systems (font manager, design project, system fonts)
- Changes to the asset propagate to all views automatically

### 3.2 Physical vs Logical Structure

The FOMO system distinguishes between:

- **Physical Structure**: Where files are actually stored on disk or in cloud services
- **Logical Structure**: How files are presented to users through the directory hierarchy

This separation is implemented through strategic use of symbolic links (symlinks), creating a consistent logical view regardless of the underlying physical storage.

### 3.3 Cloud Directionality

A critical principle for the FOMO system is the directionality of symlinks between cloud and local storage:

- Symlinks should always point FROM cloud storage TO local organisation
- This establishes cloud storage as the "source of truth"
- Changes in cloud services automatically reflect in the logical structure
- The approach minimises sync conflicts and circular reference issues

## 4. Glossary of Key Terms

This glossary defines important terminology used throughout the FOMO directory structure system:

### 4.1 Core Concepts

**Assets**: Original files (primary content) like images, videos, audio, documents, and graphics that are stored, organised, and managed within the system.

**Metadata**: Information attached to assets that provides context, description, and helps in classification, searching and organising content.

**Catalogue (or Index)**: Organised and centralised listing of assets with detailed descriptions and metadata.

**Repository (or Collection)**: A centralised library where digital assets, often sharing common characteristics or purposes, are stored, organised, and systematically managed.

**Taxonomy**: A hierarchical classification system used to categorise and organise digital assets with similar characteristics.

### 4.2 Information Types

**References**: Supplemental materials or links that provide context, relationships, or additional information about the digital content. These are information consulted but rarely modified.

**Docs (Documentation)**: Written or digital materials that provide detailed guidance, instructions, and reference about a system, product, or process, facilitating understanding, implementation, and effective use.

**Guidelines**: Flexible recommended instructions or principles that provide guidance and direction, outline best practices, ensure consistency, and offer a framework for decision-making or action.

**Standards (or Specifications/Specs)**: Enforced requirements following a purposefully established ruleset to bring consistency, quality, and interoperability across systems and domains.

**Templates**: Predefined, reusable layouts or designs that can be used as a starting point for creating new content, ensuring consistency across different media items.

**Controlled Vocabulary**: A predefined list of standardised term used to consistently tag, categorise, and search digital assets. It ensures uniform metadata application, improves search accuracy, and helps efficiently organise and retrieve content across the system.

## 5. Top-Level Organisation 

### 5.1 Primary FOMO Directories

The FOMO directory structure establishes a clear, purpose-driven organisation at the top level of the user's home directory, while respecting macOS standard folders.

```
~/                                  # Home directory
├── Projects/                       # Work you're actively creating
├── Resources/                      # Materials that support your work
├── Knowledge/                      # Information you've collected or created
├── System/                         # Computer management and configuration
├── Downloads/                      # Managed download location
│    ├── inbox/                     # New downloads landing area
│    ├── processing/                # Files being sorted (using Hazel or similar)
│    └── archive/                   # Temporary storage (30 days before automatic deletion)
└── ...                             # Standard macOS folders
```

**Projects/**: Central location for active creation work
- Development projects (code repositories, applications)
- Design projects (client work, personal design projects)
- Current activities requiring significant ongoing effort

**Resources/**: Supportive materials used across projects
- Assets (directly usable design elements: media & templates)
- References (external rarely modified guides or visual inspirations)
- Catalogues (libraries, organisation and metadata for resources)

**Knowledge/**: Information collection and management
- Notes and personal knowledge base
- Docs (dynamic, actively maintained internal knowledge)
- Research and collected information

**System/**: Computer configuration and management
- Configuration files and settings
- Automation scripts and utilities
- System maintenance and monitoring tools

**Downloads/**: Centralised downloads management 
- Symlink connects local and cloud downloads folders
- A three-stage workflow automates the process and temporary storage
- Hazel or similar software cleans up files periodically
- For details, refer to section 10.1 Downloads Management

### 5.2 Standard macOS Integration

The FOMO structure integrates with standard macOS directories:

- Maintains standard `Desktop/`, `Documents/`, etc.
- Uses symlinks to integrate cloud-synced versions where appropriate
- Preserves system-expected locations for compatibility

## 6. Complete Directory Mapping

The complete logical directory structure provides a clean, purpose-driven organisation:

```
~/                                  # Home directory
├── Projects/                       # Container for active work (Level 1: Capitalised)
│    ├── dev/                       # Development projects (Level 2+: lowercase-kebab)
│    │    ├── project-one/          # Individual dev projects
│    │    └── project-two/
│    ├── design/                    # Design projects
│    │    ├── client-a/             # By client/category
│    │    └── client-b/
│    └── education/                 # University projects and courses
├── Resources/                      # Container for supportive materials
│    ├── assets/                    # Directly usable design/media elements
│    │    ├── fonts/                # Typography resources
│    │    ├── icons/                # Icon libraries
│    │    └── ... 
│    ├── catalogues/                # Organisation systems and metadata for resources  
│    │    ├── font-manager-data/    # Metadata for font management
│    │    ├── asset-manager-data/   # Metadata for asset management
│    │    └── ...
│    ├── inspirations/              # Visual creative fuel, moodboards, design examples
│    ├── references/                # Factual information and guidance, rarely modified
│    └── templates/                 # Starting points for new work
├── Knowledge/                      # Information management
│    ├── vault/                     # Personal knowledge management system
│    │    ├── notes/                # Note collections
│    │    ├── journal/              # Time-based entries
│    │    └── ...
│    └── docs/                      # Dynamic collection of information, actively maintained
├── System/                         # Computer management
│    ├── configs/                   # Application configurations
│    ├── scripts/                   # Automation scripts
│    └── search/                    # Saved searches and smart folders
├── Downloads/                      # Managed download location (synced to iCloud)
│    ├── inbox/                     # New downloads landing area
│    ├── processing/                # Automated sorting & optimisation process
│    └── archive/                   # Temporary storage for processed files
├── Desktop/                        # Standard macOS folder (synced to iCloud)
├── Documents/                      # Standard macOS folder (synced to iCloud)
│    ├── family/                    # Family documents
│    ├── finance/                   # Financial documents
│    ├── personal/                  # Personal documents
│    └── work/                      # Work documents
└── ...                             # Standard macOS folders
```

> Note: Level 1 folder names use macOS-style capitalisation (e.g. Projects, Resources), while nested folders use lowercase with hyphens as separators. Exceptions are made for top-level project/client folders, and domain-specific cases — in line with the FOMO naming standards. Please refer to relevant documents for more details.

### 6.1 Physical to Logical Mapping

The physical storage locations are mapped to the logical structure through symlinks:

| Physical Location         | Logical Path                |
|:--------------------------|:----------------------------|
| Local Dev Projects →      | `~/Projects/dev/`           |
| Dropbox/Projects →        | `~/Projects/design/`        |
| Dropbox/Education →       | `~/Projects/education/`     |
| Dropbox/Assets →          | `~/Resources/assets/`       |
| Dropbox/Inspirations →    | `~/Resources/inspirations/` |
| Dropbox/References →      | `~/Resources/references/`   |
| iCloud Obsidian vault →   | `~/Knowledge/vault/`        |
| iCloud synced Desktop →   | `~/Desktop/`                |
| iCloud synced Documents → | `~/Documents/`              |
| iCloud synced Downloads → | `~/Downloads/`              |

### 6.2 Cloud Storage Organisation

The cloud storage maintains its organisational structure, with the FOMO system creating a logical local view through symlinks.

**Dropbox:**

```
Dropbox/
├── Assets/                         # Formerly -DESIGN-
│    ├── assets-library/            # Eagle managed library
│    ├── colours/                   # Colour palette, swatch books
│    ├── fonts/                     # Organised font library
│    └── ...
├── Education/                      # University projects and courses
├── Inspirations/                   # Visual examples to spark creativity
├── Projects/                       # Formerly -PROJECTS-
└── References/                     # Guides, specs and factual info to consult
```

**iCloud Drive:**

```
iCloud Drive/
├── Desktop/                        # Synced desktop (standard)
├── Documents/                      # Synced documents (standard)
│    ├── family/                    # Formerly -FAMILY-
│    ├── finance/                   # Formerly -FINANCE-
│    ├── personal/                  # Formerly -PERSONAL-
│    └── work/                      # Work documents (formerly in Dropbox)
├── Downloads/                      # Formerly Downloads+
│    ├── inbox/
│    ├── processing/
│    └── archive/
└── Obsidian/                       # Knowledge management vault
     └── ...
```

### 6.3 Media/Network-Attached Storage

Media content is structured on network storage for easy access and management:

```
Media/                              # Network attached (renamed from ∆Media)
├── Books/                          # Calibre managed library
├── Movies/                         # Plex managed library
├── Music/                          # Plex managed library
├── Photos/                         # Plex managed library
├── Restricted/                     # Controlled access content
└── Shows/                          # Formerly TV Shows, Plex managed library
```

### 6.4 Symlink Strategy

The guidelines follow the Directionality Principle that establishes cloud storage as the "source of truth" while maintaining a consistent user experience through the logical directory structure.

1.  **Directionality Principle:** All symlinks follow a consistent direction:

    ```
    Cloud Storage Location --> Local Filesystem Location
    ```

    This approach:
    - Establishes cloud storage as the "source of truth"
    - Ensures changes in cloud services propagate to logical structure
    - Prevents circular references and sync conflicts
    - Maintains stability if local structure is reorganised

2.  **Implementation Guidelines:** When creating symlinks:

    - **Use Absolute Paths:** Always use complete paths from root for reliability.
    - **Point FROM Cloud TO Local:** Never link in the opposite direction.
    - **Higher-Level Linking:** Link entire directories rather than individual files when possible.
    - **Documentation:** Maintain a mapping of all symlinks for reference.
    - **Testing:** Verify sync functionality after creating each symlink.

3.  **Symlink Maintenance Considerations:** To ensure long-term stability:

    - **Periodic Verification:** Check symlinks quarterly for integrity.
    - **Change Management:** When changing cloud services, update symlinks before other changes.
    - **Backup Strategy:** Ensure backup systems properly handle symlinks.
    - **Sync Conflicts:** Handle by resolving in cloud location, then refreshing symlinks.
    - **Offline Access:** Consider strategies for offline access to critical files, such as selective local caching or creating offline copies.

## 7. Implementation Instructions

### 7.1 Preparation

Before implementing the structure:

1.  **Backup System**: Create a complete Time Machine or equivalent backup
2.  **Cloud Sync**: Ensure all cloud services are fully synced
3.  **Rename Cloud Folders**: Standardise name formats in cloud locations first, following the naming conventions:
    - Level 1 folders: One-word with capitalisation (e.g., Assets, References, Projects)
    - Nested folders: lowercase with hyphens (e.g., client-projects, design-templates)
4.  **Document Existing Structure**: Map your current setup for reference

### 7.2 Core Structure Creation

Create the base directory structure:

    ```bash
    # Create the core FOMO directories
    mkdir -p ~/Projects/{dev,design,education}
    mkdir -p ~/Resources/{assets,catalogues,inspirations,references,templates}
    mkdir -p ~/Knowledge/{vault,docs}
    mkdir -p ~/System/{configs,scripts,search}
    mkdir -p ~/Downloads/{inbox,processing,archive}
    ```

### 7.3 Symlink Establishment

> Important: Symlinks behave differently with existing directories. If a target directory already exists, the `ln -sf` command will not replace the directory with a symlink. Instead, it will create the symlink inside that directory, leading to unexpected nested symlinks. Always verify that target directories do not exist before creating symlinks, or explicitly remove/rename them first. 

1. Prepare target locations:

    ```bash
    # Check and backup existing directories before creating symlinks
    for dir in "$HOME/Downloads" "$HOME/Resources/assets" "$HOME/Resources/inspirations" "$HOME/Resources/references" "$HOME/Projects/design" "$HOME/Projects/education" "$HOME/Knowledge/vault"; do
       if [ -e "$dir" ] && [ ! -L "$dir" ]; then
           mv "$dir" "${dir}-backup-$(date +%Y%m%d)" 2>/dev/null
           echo "Backed up existing directory: $dir"
       fi
    done
    ```

2. Set up the symlinks from cloud to local directories:

    ```bash
    # Dropbox symlinks
    ln -sf "$HOME/Library/CloudStorage/Dropbox-Personal/Assets" "$HOME/Resources/assets"
    ln -sf "$HOME/Library/CloudStorage/Dropbox-Personal/Inspirations" "$HOME/Resources/inspirations"
    ln -sf "$HOME/Library/CloudStorage/Dropbox-Personal/References" "$HOME/Resources/references"
    ln -sf "$HOME/Library/CloudStorage/Dropbox-Personal/Projects" "$HOME/Projects/design"
    ln -sf "$HOME/Library/CloudStorage/Dropbox-Personal/Education" "$HOME/Projects/education"
        
    # iCloud symlinks
    ln -sf "$HOME/Library/Mobile Documents/iCloud~md~obsidian/Documents/Notes" "$HOME/Knowledge/vault"
    ln -sf "$HOME/Library/Mobile Documents/com~apple~CloudDocs/Downloads" "$HOME/Downloads"
    ```
    
3. Verify symlinks 

    ```bash
    # Quick verification
    for link in "$HOME/Downloads" "$HOME/Resources/assets" "$HOME/Resources/inspirations" "$HOME/Resources/references" "$HOME/Projects/design" "$HOME/Projects/education" "$HOME/Knowledge/vault"; do
       if [ ! -L "$link" ]; then
           echo "Warning: $link is not a symlink - check for issues"
       fi
    done
    ```

> Note: The Desktop and Documents symlinks are typically created automatically when enabling iCloud Drive in macOS. This implementation focuses on creating the remaining symlinks. 
> Troubleshooting: For symlink issues, refer to section 11.3 Troubleshooting Common Issues.

### 7.4 Shell Integration

Add quick navigation functions to your `.zshrc`, `.bashrc`, or `.bash_profile`:

    ```bash
    # Add to your shell configuration file (.zshrc, .bashrc, or .bash_profile)
    # Quick navigation to major areas
    alias proj="cd ~/Projects"
    alias res="cd ~/Resources"
    alias know="cd ~/Knowledge"
    alias sys="cd ~/System"
    alias dl="cd ~/Downloads"
        
    # Project jumping function
    proj() {
        local base="$HOME/Projects"
        if [ -z "$1" ]; then
            cd "$base"
        else
            local matches=($(find "$base" -maxdepth 2 -type d -name "*$1*"))
            local count=${#matches[@]}
        
            if [ "$count" -eq 0 ]; then
                echo "No matching project found."
            elif [ "$count" -eq 1 ]; then
                cd "${matches[0]}"
            else
                echo "Multiple projects found:"
                for i in "${!matches[@]}"; do
                    echo "$((i+1)): ${matches[$i]}"
                done
                read -p "Enter the number of the project to navigate to: " choice
                if [[ "$choice" -ge 1 && "$choice" -le "$count" ]]; then
                    cd "${matches[$((choice-1))]}"
                else
                    echo "Invalid selection."
                fi
            fi
        fi
    }
    ```

### 7.5 Phased Implementation

Implement the structure in phases:

1.  **Phase 1 (Days 1-2)**: Set up core structure and initial symlinks
2.  **Phase 2 (Days 3-7)**: Migrate active projects and high-value resources
3.  **Phase 3 (Days 8-14)**: Establish downloads workflow and automation
4.  **Phase 4 (Ongoing)**: Gradually reorganise historical content as needed

## 8. Migration Strategy

### 8.1 Pre-Migration Assessment

Before beginning migration:
1.  **Inventory Existing Files**: Document your current directory structure
    - Use tools like `find` or `ls -R` to capture the current state
    - Note existing naming patterns and conventions
    - Identify problematic areas with excessive nesting or inconsistent organisation

2.  **Identify Content Categories**: Group content by type
    - Active projects vs. archived work
    - Shared resources vs. project-specific assets
    - System configurations and settings
    - Knowledge and reference materials

3.  **Flag High-Priority Items**: Mark actively used files and directories
    - Current client projects
    - Frequently accessed resources
    - Critical system configurations
    - Regular workflow files

4.  **Document Application Settings**: Note paths in applications that may need updating
    - Design application libraries and preferences
    - Development environment configurations
    - Browser download locations
    - Backup software settings

### 8.2 Phased Migration Approach

Implement migration in these four phases:

#### Phase 1: Core Structure 

- Create the FOMO directory structure
- Establish symlinks
- Test with small sample files
- Do not migrate actual content yet

#### Phase 2: Active Projects 

- Begin with 1-2 active projects
- Move to appropriate locations in ~/Projects/
- Update application references
- Test workflows before continuing

#### Phase 3: Resources & Knowledge 

- Reorganise design assets into ~/Resources/assets/
- Set up knowledge management in ~/Knowledge/
- Migrate templates and reference materials
- Configure cataloguing systems

#### Phase 4: Historical Content (Ongoing)

- Gradually migrate archived projects.
- Apply naming conventions to historical files.
- Document exceptions for legacy materials.

### 8.3 Project-Specific Migration Guidelines

#### Design Projects

1.  Create project folder in `~/Projects/design/[client-name]/`.
2.  Move design source files, maintaining version history.
3.  Extract shared assets to `~/Resources/assets/`.
4.  Update application libraries to new locations.

#### Development Projects

1.  Clone repositories to `~/Projects/dev/`.
2.  Update local references and configuration.
3.  Add shared code libraries to appropriate locations.
4.  Configure IDEs to use new paths.

#### Knowledge and Documents

1.  Move reference materials to `~/Resources/references/`.
2.  Import notes into a knowledge management system.
3.  Establish links between related content.
4.  Set up automated organisation where possible.

### 8.4 Post-Migration Verification

After migrating each section:

1.  **Verify Access:** Ensure all files can be accessed through the new structure.
2.  **Test Applications:** Confirm that applications can find relocated files.
3.  **Check Symlinks:** Validate that all symlinks are working correctly.
4.  **Document Changes:** Update project documentation with new locations.

## 9. Multi-Machine Implementation

### 9.1 Setup Script

Use this script to establish consistent structure across machines:

    ```bash
    #!/bin/bash
      # fomo-directory-setup.sh
      
      # Determine machine type for machine-specific settings
      HOSTNAME=$(hostname)
      case "$HOSTNAME" in
      "MacMini"*)
         MACHINE_TYPE="server"
         ;;
      "Work"*)
         MACHINE_TYPE="work"
         ;;
      *)
         MACHINE_TYPE="personal"
         ;;
      esac
    
    # Set base paths (adjust if needed per machine)
    DROPBOX_PATH="$HOME/Library/CloudStorage/Dropbox-Personal"
    ICLOUD_PATH="$HOME/Library/Mobile Documents/com~apple~CloudDocs"
    OBSIDIAN_PATH="$HOME/Library/Mobile Documents/iCloud~md~obsidian/Documents/Notes"
    
    # Create base directories
    mkdir -p "$HOME/Projects"/{dev,design,education}
    mkdir -p "$HOME/Resources"/{assets,catalogues,inspirations,references,templates}
    mkdir -p "$HOME/Knowledge"/{vault,docs}
    mkdir -p "$HOME/System"/{configs,scripts,search}
    mkdir -p "$HOME/Downloads"/{inbox,processing,archive}
    
    # Set up symlinks based on machine type
    echo "Setting up for $MACHINE_TYPE machine..."
    
    # Common symlinks across all machines
    ln -sf "$DROPBOX_PATH/Assets" "$HOME/Resources/assets"
    ln -sf "$DROPBOX_PATH/Inspirations" "$HOME/Resources/inspirations"
    ln -sf "$DROPBOX_PATH/References" "$HOME/Resources/references"
    ln -sf "$DROPBOX_PATH/Projects" "$HOME/Projects/design"
    ln -sf "$DROPBOX_PATH/Education" "$HOME/Projects/education"
    ln -sf "$OBSIDIAN_PATH" "$HOME/Knowledge/vault"
    ln -sf "$ICLOUD_PATH/Downloads" "$HOME/Downloads"
    
    # Machine-specific configurations
    if [ "$MACHINE_TYPE" = "server" ]; then
    # Server-specific settings
    echo "Adding server-specific configurations..."
    # Additional server-specific symlinks
    elif [ "$MACHINE_TYPE" = "work" ]; then
    # Work machine settings
    echo "Adding work machine configurations..."
    # Work-specific configurations
    else
    # Personal machine gets everything
    echo "Adding personal machine configurations..."
    # Full personal setup
    fi
    
    echo "Directory structure created successfully for $MACHINE_TYPE!"
    ```

### 9.2 Machine-Specific Considerations

Adapt the structure for different environments:

**Personal Machine**:
- Full implementation of all directories
- Complete set of symlinks
- Media access paths to home server

**Work Machine**:
- Limited personal content
- Expanded work-related directories
- Stricter separation between work and personal

**Server/Home Machine**:
- Enhanced media directories
- Backup configurations
- Reduced development environment

### 9.3 Consistency Guidelines

To maintain consistency across machines:

1. **Use Relative Paths**: When possible, use $HOME instead of hardcoded paths
2. **Machine Detection**: Use hostname or other identifiers to apply appropriate settings
3. **Configuration Files**: Store machine-specific configurations in version control
4. **Synced Settings**: Keep shell aliases and functions consistent via dotfiles repository

## 10. Special Considerations

### 10.1 Downloads Management

The three-stage Downloads structure provides a clear workflow:

1. **inbox/**: All new files land here initially
    - Set as default download location in browsers
    - Configure screenshots to save here
    - First target for automation rules

2. **processing/**: Files actively being sorted
    - Temporary staging area
    - Files moved here during processing
    - Hazel or similar monitors for automated sorting

3. **archive/**: Temporary storage for processed files
    - *30-day* holding area before deletion
    - Last chance to recover accidentally processed files
    - Automatic cleanup after retention period

### 10.2 Font Management

Fonts require special handling due to their dual nature:

1. **Storage Location**: `~/Resources/assets/fonts/`
    - Organised by family/style following typography standards
    - Retains PascalCase naming per FOMO Naming Standards as an explicit exception to the kebab-case convention
2. **Font Management Tool Integration**:
    - Font manager data stored in `~/Resources/catalogues/font-manager-data/`
    - Activation states managed through font management software
    - Variable fonts handled based on industry standards
    - The font manager data is stored locally. Ensure this data is included in Time Machine backups or create a separate backup strategy for this content.
   
### 10.3 Git Repository Organisation

Git repositories have specific requirements:

1. **Development Projects**: `~/Projects/dev/[project-name]/`
    - Each repository in its own directory
    - Follow language/framework conventions within repos
    - Example: `~/Projects/dev/fomo-system/`
2. **Knowledge Management**: Git repositories within Obsidian vault
    - Selective tracking of text content
    - `.gitignore` configured to exclude binary files
    - Example: `~/Knowledge/vault/notes/.git/`
3. **System Configuration**: Version-controlled dotfiles
    - Stored in `~/System/configs/dotfiles/`
    - Includes shell configurations, application settings
    - Symlinked to appropriate locations
    - Ensure local Git repositories (e.g., in `~/Projects/dev/`) are backed up, either through regular pushes or Time Machine.

### 10.4 Cloud Service Considerations

Each cloud service has unique characteristics to consider:

**Dropbox**:
- Optimised for shared project files
- Handles large binary files well
- Reliable symlink handling
- Used for design assets and projects

**iCloud**:
- Deep macOS integration
- Variable offline file handling
- Desktop and Documents syncing enabled
- Better for frequently changed text files

> Note: /Desktop and /Documents sync mechanisms
> macOS iCloud integration creates specific sync mechanisms for `Desktop` and `Documents` directories that should not be modified, even though they may appear to be different to the guideline's specifications. These special cases should be excluded from compliance checks. Actual sync configuration may vary based on settings and OS versions.

**Local Storage**:
- Used for development files requiring fast access
- Appropriate for large multimedia projects
- Houses git repositories with frequent operations
- Requires separate backup strategy
- Consider strategies for offline access to critical files, such as:
    1. Using cloud service options to keep specific files locally available offline
    2. Creating local copies of frequently used assets in a separate ‘offline’ directory
    3. Setting up scheduled synchronisation for key working files

## 11. Maintenance Procedures

### 11.1 Regular Verification

Perform these checks to ensure system integrity:

1.  **Weekly Quick Check**:
    - Verify core symlinks are functioning
    - Check Downloads workflow is processing correctly
    - Confirm new files are appearing in correct locations

2.  **Monthly System Review**:
    - Validate all symlinks in the structure
    - Check cloud service sync status
    - Review folder growth and storage usage
    - Identify potential reorganisation opportunities

3.  **Quarterly Deep Audit**:
    - Run directory structure validation scripts (see example below)
    - Update machine-specific configurations
    - Review and update automation rules
    - Check compliance with naming conventions

    ```bash
    #!/bin/bash
    # fomo-symlink-check.sh
        
    # Array of symlinks to check
    symlinks=(
      "$HOME/Resources/assets"
      "$HOME/Resources/inspirations"
      "$HOME/Resources/references"
      "$HOME/Projects/design"
      "$HOME/Projects/education"
      "$HOME/Knowledge/vault"
      "$HOME/Downloads"
    )
    
    # Check each symlink
    for link in "${symlinks[@]}"; do
      if [[ ! -L "$link" ]]; then
        echo "Error: $link is not a symlink"
      else
        target=$(readlink "$link")
        if [[ ! -d "$target" ]]; then
          echo "Error: $link points to a non-existent directory: $target"
        fi
      fi
    done
        
    echo "Symlink check complete."
    ```

### 11.2 Backup Management

Ensure appropriate data protection:

1.  **Cloud-Synced Content**:
    - Verify cloud services are syncing correctly
    - Confirm all symlinks are properly connected to cloud sources
    - Test cloud service recovery functionality periodically

2.  **Local-Only Content**:
    - Identify any content not stored in cloud services
    - Ensure Time Machine backups are current for system-wide protection
    - Use Git repositories for code, configuration files, and documentation
    - Consider additional backup solutions for critical local-only data (e.g., locally stored font manager data)
    - Ensure local Git repositories (e.g., in `~/Projects/dev/`) are backed up, either through regular pushes to remote repositories or inclusion in Time Machine backups

3.  **Backup Verification**:
    - Regularly test recovery from backups
    - Document backup locations and procedures
- Maintain at least 4 backups to ensure all information is either cloud-sourced or backed up
   - Verify backup integrity quarterly

### 11.3 Troubleshooting Common Issues

Guidelines for resolving typical problems:

1.  **Broken Symlinks**:
    - Check if target exists in cloud storage
    - Verify cloud service is properly synced
    - Recreate symlink with correct target
    - Example: `ln -sf "[correct-cloud-path]" "[local-path]"`
2.  **Cloud Sync Conflicts**:
    - Resolve at the cloud storage level first
    - Never create bidirectional symlinks
    - After resolution, refresh affected symlinks
    - Consider temporarily disconnecting problem symlinks
3.  **Path Too Long Errors**:
    - Identify problematic deep paths
    - Restructure to reduce directory depth
    - Create higher-level symlinks where appropriate
    - Consider shorter directory names in deep structures
    
### 11.4 Adapting the Structure

Guidelines for evolving the system over time:

1.  **Adding New Directories:**
    - Follow existing naming patterns.
    - Place at the appropriate level in the hierarchy.
    - Update documentation to reflect changes.
    - Example: Adding `~/Resources/courses/` for educational materials.

2.  **Retiring Directories:**
    - Archive content if potentially needed.
    - Remove symlinks before deleting targets.
    - Update shell aliases and scripts.
    - Document changes in the maintenance log.

3.  **Cloud Service Changes:**
    - Document the existing symlink structure before making changes.
    - Update cloud paths at the source first.
    - Recreate symlinks after cloud reorganisation.
    - Test thoroughly after migration.

## 12. Examples and Use Cases

### 12.1 Design Workflow Example

   ```
   # Starting a new client project
   mkdir -p ~/Projects/design/acme-corp/website
   mkdir -p ~/Projects/design/acme-corp/website/{briefs,design,assets,production}
   
   # Creating design assets
   touch ~/Projects/design/acme-corp/website/assets/acme-logo-primary-v01.ai
   touch ~/Projects/design/acme-corp/website/assets/acme-header-homepage-v01.psd
   
   # Design handoff for development
   mkdir -p ~/Projects/design/acme-corp/website/production
   touch ~/Projects/design/acme-corp/website/production/acme-website-homepage-handoff-v01.sketch
   ```

### 12.2 Development Workflow Example

   ```
   # Starting a new development project
   cd ~/Projects/dev
   git clone https://github.com/username/project-name.git
   cd project-name
   
   # Setting up project structure
   mkdir -p src/{components,utils,styles}
   mkdir -p docs
   touch README.md
   
   # Working on features
   touch src/components/Button.tsx
   touch src/utils/api-client.js
   ```

### 12.3 Knowledge Management Example

   ```
   # Creating new notes
   cd ~/Knowledge/vault/notes
   touch project-research-fomo.md
   mkdir -p reference/design-systems
   touch reference/design-systems/atomic-design-principles.md
   
   # Organising documentation
   cd ~/Knowledge/docs
   mkdir -p tutorials/css
   touch tutorials/css/grid-layout-guide.md
   ```

### 12.4 Downloads Processing Example

   ```
   # Browser downloads file to inbox
   # ~/Downloads/inbox/random-download.pdf
   
   # Hazel moves to processing for renaming
   # ~/Downloads/processing/random-download.pdf → client-presentation-20250301.pdf
   
   # File is moved to final destination
   # ~/Projects/design/client/presentations/client-presentation-20250301.pdf
   
   # If file isn't moved within 30 days, it goes to archive
   # ~/Downloads/archive/client-presentation-20250301.pdf
   
   # After 30 days in archive, it's automatically deleted
   ```

## 13. Integration with FOMO Documents

This Directory Structure document works in conjunction with other FOMO project documents to form a unified system:

- **fomo-project-charter-v##.md**: Establishes the overall vision and principles for the fomo system
- **fomo-naming-standards-v##.md**: Defines the file naming conventions used within this structure
- _fomo-directory-structure-v##.md (this document)_: Defines the folder hierarchy these named files will live within
- **fomo-process-diagram-v##.mmd**: identifies automation opportunities through series of flow diagrams 
- **fomo-controlled-vocabulary-v##.md**: Standardised terms for systematic and consistent naming
- **fomo-implementation-plan-v##.md**: Details the step-by-step approach for system deployment
- **fomo-automation-overview-v##.md**: Contains scripts, tools and workflow setup for file management
- **fomo-special-cases-v##.md**: Provides guidance for exceptions to the standard structure
- **fomo-system-cheatsheet-v##.md**: Quick reference guide for daily application
- **fomo-maintenance-log-v##.md**: Tracks changes and issues encountered during implementation

## 14. Success Measures Suggestions

The effectiveness of this directory structure can be measured by:

- **Navigation Efficiency**: 50% reduction in path depth and navigation time
- **Resource Location**: 70% faster retrieval of commonly used files
- **Cross-Machine Consistency**: 95% structural similarity across different devices
- **Automation Success**: 80% of file organisation handled automatically
- **Cognitive Load**: 60% reduction in decision points during file operations
- **Shell Navigation**: 40% reduction in CLI keystrokes for common operations
- **Multi-System Harmony**: Zero sync conflicts due to symlink issues

---

_Version History:_
- v01 - 2025-03-10: Initial directory structure document created
- v02 - 2025-03-18: Corrections and updates made to ensure consistency, Enhanced implementation clarity, fixed formatting issues, and improved technical accuracy
- v03 - 2025-03-24: Updated symlink structure to include Inspirations folder, standardised References (plural) usage, corrected symlink counts and mappings, improved shell configuration options, and clarified Knowledge/docs directory purpose