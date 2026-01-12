# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Discourse theme called "Clean" - a custom styling theme for Seqera's Discourse forum. It provides Seqera brand styling with custom fonts (Inter, Degular), colors, and UI modifications.

## Development Commands

```bash
# Format all files
yarn pretty:all

# Format only modified files
yarn pretty
```

Linting uses `@discourse/lint-configs` for ESLint, Prettier, and ember-template-lint.

## Architecture

This is a standard Discourse theme structure:

- **about.json** - Theme metadata, requires Discourse 3.0.0+
- **common/common.scss** - Main stylesheet with all CSS customizations
- **scss/components/** - Additional SCSS partials (imported by common.scss)
- **javascripts/discourse/** - JavaScript modules:
  - `initializers/init-clean.js` - Main initializer, renders CleanUserInfo component
  - `d-nav-controls/initializers/init-nav-controls.js` - Mobile scroll behavior for hiding nav controls
  - `components/` - Ember/Glimmer components
  - `templates/` - Handlebars templates
- **styles/** - Custom fonts (Inter, Degular)
- **assets/** - Static assets like icon sprites
- **settings.yml** - Theme settings (currently just custom SVG icons list)

## Key Customizations

The theme uses Discourse's Plugin API (`withPluginApi`) for JS modifications and CSS custom properties for theming. Main CSS variables are defined in `:root` in common.scss with Seqera brand colors like `--seqera-black`, `--seqera-blue-primary`, and `--seqera-grey-bg`.

## Discourse Compatibility

The `.discourse-compatibility` file maps Discourse versions to specific git commits for compatibility.
