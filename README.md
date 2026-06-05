// Zed settings
//
// For information on how to configure Zed, see the Zed
// documentation: https://zed.dev/docs/configuring-zed
//
// To see all of Zed's default settings without changing your
// custom settings, run `zed: open default settings` from the
// command palette (cmd-shift-p / ctrl-shift-p)
{
  "agent_ui_font_size": 16.0,
  "agent_buffer_font_size": 14.0,
  "proxy": "",
  "diff_view_style": "unified",
  "base_keymap": "VSCode",
  "agent_servers": {
    "opencode": {
      "type": "registry"
    },
    "claude-acp": {
      "type": "registry",
    },
  },
  "project_panel": {
    "dock": "left",
  },
  "outline_panel": {
    "dock": "right",
  },
  "collaboration_panel": {
    "dock": "right",
    "button": false,
  },
  "search": {
    "button": false,
  },
  "agent": {
    "dock": "right",
    "sidebar_side": "right",
    "favorite_models": [],
    "model_parameters": [],
  },
  "git_panel": {
    "tree_view": false,
    "dock": "left",
  },
  "terminal": {
    "button": false,
  },
  "session": {
    "trust_all_worktrees": true,
  },
  "icon_theme": {
    "mode": "dark",
    "light": "Zed (Default)",
    "dark": "Catppuccin Frappé",
  },
  "ui_font_size": 16,
  "buffer_font_size": 15.0,
  "theme": {
    "mode": "light",
    "light": "One Dark",
    "dark": "One Dark",
  },
  "languages": {
    "Python": {
      "language_servers": ["ty", "ruff", "!basedpyright"],
    },
  },
}
