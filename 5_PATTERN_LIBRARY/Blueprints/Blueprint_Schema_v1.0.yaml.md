# 🧾 Pattern Blueprint Schema — Codex OS
# Layer: 5 — Pattern Library
# Version: 1.0
# Author: CDX Router (Jor Ferraro)
# Status: Active
# Visibility: Internal

schema_version: "1.0"
description: >
  Defines the data model and validation rules for all Pattern Blueprints in Codex OS.
  Ensures machine-readable consistency across automation layers (n8n, Obsidian Dataview, and Remix Engine).

---

fields:
  - id: pattern_id
    type: string
    required: true
    example: "CDX_PATTERN_2025_11_SB_004"

  - id: source_post_id
    type: string
    required: true
    example: "CDX_POST_2025_11_SB_0007"

  - id: learning_vector
    type: float
    range: [0, 1]
    validation: "≥ 0.8 for validated patterns"
    example: 0.86

  - id: momentum_index
    type: float
    range: [0, 1]
    example: 0.82

  - id: validated_on
    type: date
    format: "YYYY-MM-DD"
    required: true

  - id: theme
    type: string
    example: "Resonant Minimalism"

  - id: tone
    type: string
    example: "Warm Precision"

  - id: context
    type: string
    example: "SB_Instagram_Post_07"

  - id: status
    type: enum
    values: ["active", "dormant", "archived"]
    default: "active"

  - id: platforms
    type: array
    items: string
    example: ["Instagram", "LinkedIn"]

  - id: essence
    type: text
    description: "Core truth statement or emotional insight driving the pattern."
    example: "Contener más que convencer. La pausa como gesto de confianza."

  - id: attributes
    type: object
    properties:
      tone: string
      cadence: string
      energy_level: integer
      visual_ratio: string
      cta_type: string
      ideal_platforms: array
      temporal_context: string

  - id: structure
    type: object
    properties:
      hook: text
      body: text
      closure: text

  - id: design_guidelines
    type: object
    properties:
      typography: string
      color_mood: string
      imagery_style: string
      framing_ratio: string
      animation: string

  - id: philosophical_alignment
    type: object
    description: "Mapping to Philosophical Genome."
    properties:
      thinker: string
      concept: string
      application: string

  - id: performance_snapshot
    type: object
    properties:
      learning_vector: float
      sincerity_proxy_score: float
      momentum_index: float
      engagement_rate: float

  - id: router_notes
    type: text
    description: "Human reflections and qualitative observations."

  - id: cross_links
    type: object
    properties:
      forward: string
      backward: string

  - id: archive_behavior
    type: object
    properties:
      threshold_lv: float
      threshold_mi: float
      duration_days: integer
      action: string

  - id: metadata
    type: object
    properties:
      module_id: string
      parent_phase: string
      linked_layers: array
      update_frequency: string
      status: string

---

validation_rules:
  - rule: "LV must be ≥ 0.8 to enter Blueprint directory."
  - rule: "Momentum Index (MI) must not trend down for 14 consecutive days."
  - rule: "Each Blueprint must include at least one cross-link."
  - rule: "All YAML frontmatter must be validated via Resilience Log before ingestion."
  - rule: "Router approval required for pattern promotion to Remix Engine."

---

automation_hooks:
  - id: blueprint_validator
    tool: "n8n"
    function: "Validate structure and schema compliance."
  - id: remix_integrator
    tool: "n8n"
    function: "Ingest validated pattern into Remix Engine templates."
  - id: archive_trigger
    tool: "n8n"
    function: "Move outdated or decayed patterns into /Archive/."
  - id: router_alert
    tool: "Telegram"
    function: "Notify Router on schema or validation errors."

---

metadata:
  module_id: "CDX_PatternLibrary_BlueprintSchema_v1.0"
  parent_phase: "Pattern Library"
  linked_layers: ["Reflection", "Creation", "System"]
  update_frequency: "on_validation"
  status: "active"


