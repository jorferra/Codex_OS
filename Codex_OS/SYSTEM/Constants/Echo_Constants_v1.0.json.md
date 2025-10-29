{
  "version": "1.0",
  "system_name": "Codex (CDX)",
  "last_update": "2025-10-26",
  "sample_window_hours": 72,
  "caption_length_bins": {
    "short": [200, 350],
    "medium": [351, 550],
    "long": [551, 700]
  },
  "sincerity_bands": {
    "low": "<40",
    "medium": "40-70",
    "high": ">70"
  },
  "percentile_gap_threshold": 30,
  "sincerity_formula": "percentile_based",
  "sentiment_bonus": {
    "positive": 1.2,
    "neutral": 1.0,
    "negative": 0.8
  },
  "alert_thresholds": {
    "brilliant_misfire": 0.45,
    "hollow_hit": 0.88
  },
  "momentum_index": {
    "window_weeks": 4,
    "slope_threshold": 0.15
  },
  "metadata_fields": [
    "module_id",
    "parent_phase",
    "learning_link",
    "optional",
    "transversal"
  ],
  "language_protocol": {
    "system_docs": "en",
    "client_outputs": "es-AR"
  }
}