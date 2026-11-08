# Surfaces 0.1.0-alpha.2

Connect a local web application, inspect its builds, turn design feedback into reusable guidance, and deploy a completed build locally with one action.

This update fixes first-run connection readiness. You can enter your application details while the build environment is preparing and leave **Connect application** open. Verification progresses to **Project ready to connect** automatically, keeping your entries and keyboard focus. No close-and-reopen workaround is needed.

Real preparation failures remain visible, and **Connect and build application** still checks the current source and runtime before starting work.

The macOS alpha includes:

- A desktop workspace that prepares its own isolated Linux build environment.
- Application and design-source connections, retained build captures, and a native application preview.
- Guidance that you accept once and reuse for later work.
- One Deploy action. Advance, Hold, Reject and unresolved findings remain visible without blocking deployment.
- Feedback attached to the artifact, with work retained after closing and reopening Surfaces.

## Install and try it

Download `Surfaces-0.1.0-alpha.2-macOS-arm64.zip` from the release, extract it, move Surfaces to Applications, and open it. The release includes `SHA256SUMS` for download verification.

You need an Apple silicon Mac running macOS 13 or later, at least 16 GiB of memory, more than 20 GiB of free disk space, and an internet connection for initial environment preparation and application dependencies. You do not need to install Node, Python or Lima on the host.

Choose **Connect application** and select a committed local Git application with a single origin, supported package-manager lockfile, build command and static output. Review its discovered settings and choose **Connect and build application**. Then select **Inspect** on Build 1, open its local preview, or choose **Deploy locally**.

To guide a change, use **Improve this view**, select design-system source, review and accept the guidance, and prepare an editing task for your existing coding tool. Work in the managed application folder shown by Surfaces. Use the supplied source-ready instructions to capture the next build. The accepted guidance remains available for subsequent builds.

## Alpha scope

This release supports fresh installations. Recovery or migration of failed workspaces from previous engineering builds is not supported; preserve those workspaces rather than deleting them to retry. Existing engineering-build users should use a fresh macOS user account for this alpha.

Application support is bounded to the declared static web build integrations. Dynamic routes and multi-step interactions can remain unresolved. A successful build is not a claim that all guidance was checked, and Surfaces does not claim that an external coding tool consumed its instructions. Findings remain available for review.

This is an early alpha for trying the local workflow. It does not include automatic updates.
