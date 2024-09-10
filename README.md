# Renovate Configuration

## Overview
This configuration file sets up Renovate to manage dependency updates across various package managers. It automates minor and patch updates for most dependencies while requiring manual review for major updates. All updates are labeled and tracked according to their type and package manager.

## Key Features
- Automerge: Enabled for patch and minor updates if they are stable for 30 days. Major updates require manual review.
- Labels: Updates are labeled by type (patch, minor, major) and package manager (Maven, npm, NuGet, Dockerfile).
- Branch and PR Management: Updates are handled in separate branches and pull requests with a custom prefix and message format.
- Ignored Paths: Specific directories (e.g., node_modules, dist, target, docker) are excluded from updates.

## Configuration Details
- Automerge: Disabled globally; enabled individually for patch and minor updates.
- Stability Days: 30 days before automerging.
- Branch Prefix: Sentinel-Renovate-
- Commit Message Prefix: Sentinel-Renovate:
- PR Footer: Automatic dependency bump created by Sentinel-Renovate.

## Package Rules
### Maven
- Patch: Automerged with label ["Maven", "patch"].
- Minor: Automerged with label ["Maven", "minor"].
- Major: Requires manual review with label ["Maven", "major"].
### npm
- Patch: Automerged with label ["npm", "patch"].
- Minor: Automerged with label ["npm", "minor"].
- Major: Automerged with label ["npm", "major"].
### NuGet
- Patch: Automerged with label ["NuGet", "patch"].
- Minor: Automerged with label ["NuGet", "minor"].
- Major: Requires manual review with label ["NuGet", "major"].
### Dockerfile
- Patch: Automerged with label ["Docker", "patch"].
- Minor: Automerged with label ["Docker", "minor"].
- Major: Requires manual review with label ["Docker", "major"].
