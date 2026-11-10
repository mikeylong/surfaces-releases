# Surfaces 0.1.0-alpha.5

Alpha 5 processes commits automatically while Surfaces is open: build locally,
check accepted guidance, apply supported corrections, rebuild and recheck, then
deploy locally. Routine runs do not require **Build**, **Deploy**, or another
approval of the same guidance. New or contested requirements still need your
decision.

Corrections use a private source version. Your original repository, commits and
unsaved or untracked work stay unchanged. Existing workspaces retain their source,
accepted guidance, builds, deployments, feedback and history. The canvas and owner
controls are unchanged; manual build and Deploy remain available.

## Work with automatic changes

For a supported application with its source, local destination and correction
scope authorized, commit changes in the **original connected Git repository**.
Keep Surfaces open while it processes the commit and serves the local deployment.
When the destination shows the completed build running, **Open local deployment**
opens the application on this Mac.

Saving files alone does not trigger this path. Changes saved only in Surfaces'
managed working folder remain part of the optional manual workflow. Corrections
are not copied back to the original repository, so later commits may need the
same accepted correction again.

After a restart, Surfaces checks the latest committed tip rather than replaying
every intermediate commit. The tip must descend from the last recorded automatic
revision; rewritten or unrelated history needs reconciliation. The watcher follows
the repository's HEAD, not a selected branch name or remote webhook.

## Updating an existing workspace

The signed app reused the existing Portfolio workspace's accepted guidance and
completed build, then deployed it locally without another build, Deploy click or
guidance approval. Original and managed source, accepted guidance and historical
records were preserved.

Eligible connections without accepted guidance or unfinished work can prepare an
updated environment alongside the retained one. Connections with accepted guidance
keep their environment. Earlier builds and captures retain their original evidence.
Verified stopped local-serving history is preserved during shutdown.

Build and local-serving preparation coordinate access to their environment.
Interrupted preparation can continue only after Surfaces verifies that execution
never started, saved inputs remain unchanged and the original deadline applies.
Automatic deployment waits for the saved destination to become ready. An exact
completed build interrupted before deployment begins can continue without
rebuilding or repeated guidance approval. Unknown outcomes remain retained for
reconciliation.

## Install

Download `Surfaces-0.1.0-alpha.5-macOS-arm64.zip` and `SHA256SUMS` from the same
release. The package is signed and notarized. Extract the ZIP, move Surfaces to
Applications and open it.

You need an Apple silicon Mac running macOS 13 or later, at least 16 GiB of memory,
more than 20 GiB of free disk space for new environment preparation, and internet
access for preparation and dependencies. Keep additional room for retained builds
and local serving. Host Node, Python and Lima installations are not required.

## Alpha limits

- Imported contracts are checked, and build inspection shows their version and
  results. The general **Guidance** panel can still appear empty for imported
  guidance; use the build's inspection to see those results.
- Next.js support covers one application with an npm or pnpm lockfile pinning
  stable Next 16, the declared `next build` script, default `.next` output and
  supported declarative configuration. It runs with `next start`, without static
  conversion. Custom plugins/build commands/output modes, multi-package workspaces,
  and nonempty base paths or asset prefixes remain unsupported.
- Local serving accepts GET and HEAD. Server actions, write endpoints,
  authentication or secret-dependent journeys, external runtime services and
  outbound application networking remain unsupported. Installation uses the
  lockfile with scripts disabled; supported font downloads are allowed at build time.
- Checks cover declared selectors, rendered properties, literal DOM attributes
  and supported interaction recipes. Missing or unsupported checks remain visible
  and do not establish compliance. A failed correction or unresolved checks after
  correction retain an exception and preserve the previous publication. Optional
  manual **Deploy** remains available
  for a valid artifact with findings visible and normal destination/recovery checks.
- Corrections require accepted source-bound mappings and allow one pass per run.
  This is not arbitrary code repair or complete visual/accessibility checking.
- Keep Surfaces open to process commits and serve deployments. This alpha adds no
  public hosting, independent background service, remote commit service or app updater.

# Surfaces 0.1.0-alpha.4

Alpha 4 adds support for Next.js 16 applications with npm or pnpm, including
server builds that run with `next start`. You can connect a supported Next.js
application, build it locally, and use **Deploy** to put the selected completed
build in Surfaces' local destination. Supported static applications use the same
deployment action.

**Deploy** appears beside the selected build on the canvas and in its inspection
details. Surfaces checks availability automatically and explains temporary
problems in the build's details. Accepted guidance continues to apply without
another approval for each build or deployment. Findings remain visible.

Your original application folder stays unchanged. Surfaces builds from its
managed working folder and keeps earlier source snapshots and builds. Updating
also preserves existing workspaces, connections and history.

## Connect and deploy

For a new application, choose **Connect application**, use **Browse…** to select a
committed local Git application with one origin, and choose **Connect and build
application** after reviewing the settings. Surfaces imports its committed revision.

For each later version:

1. Choose **Project → Open working folder**. Make and save your edits in that
   folder with your existing coding tool. Later edits in the original folder are
   not copied into it.
2. Choose **Build saved changes** in Project. Pause editing until Surfaces has
   saved the snapshot, then let the build finish.
3. Select that completed build on the canvas and choose **Deploy**. The
   destination is labeled **Local destination on this Mac**. One click starts
   deployment; saving files or completing a build does not deploy automatically.
4. When the destination shows the selected build running, choose
   **Open local deployment** to use it.

Keep Surfaces open while using the local deployment. This serves the application
on your Mac; it does not publish a public website.

## Install

Download `Surfaces-0.1.0-alpha.4-macOS-arm64.zip`, extract it, move Surfaces to
Applications, and open it. The release includes `SHA256SUMS` for verification.

You need an Apple silicon Mac running macOS 13 or later, at least 16 GiB of memory,
more than 20 GiB of free disk space, and an internet connection for environment
preparation and application dependencies. Host Node, Python and Lima installations
are not required.

## Alpha limits

Next.js support covers a single application with a lockfile that pins a stable
Next 16 version, a build script of `next build`, the default `.next` output, and
supported declarative configuration. Custom configuration plugins, custom build
commands and output modes, multi-package workspaces, and nonempty base paths or
asset prefixes are unsupported.

Local serving accepts GET and HEAD requests. Server actions, write endpoints,
authentication and secret-dependent journeys, external runtime services, and
outbound network access from the deployed application are unsupported. Dependency
installation still requires internet access; supported font downloads are allowed
during the build.

Next.js captures may report unresolved routes or resources. Portable guidance
evaluation is not yet supported for this adapter. A successful build or deployment
does not establish complete checking coverage. This alpha does not include
automatic updates.

# Surfaces 0.1.0-alpha.3

Alpha 3 fixes connection setup when an older unfinished setup blocks startup.
Surfaces checks that the previous build environment is inactive, then offers
**Start a new workspace**. That action restarts Surfaces in separate storage and
keeps your previous workspace and application files on disk. Your old canvas and
history are not migrated into the new workspace.

The connection form now has **Browse…** to select an application folder. Its name
fills the project name, and Surfaces uses your macOS username for new connection
attribution. The extra owner field is gone. Canceling the picker keeps your entries,
and setup status appears once with a useful next action.

A compatible Alpha 2 workspace keeps its existing environment, connections and
builds. Alpha 3 includes the same signed runtime support so updating the app does
not require preparing that environment again.

## Install and try it

Download `Surfaces-0.1.0-alpha.3-macOS-arm64.zip`, extract it, move Surfaces to
Applications, and open it. The release includes `SHA256SUMS` for verification.

You need an Apple silicon Mac running macOS 13 or later, at least 16 GiB of memory,
more than 20 GiB of free disk space, and an internet connection for environment
preparation and application dependencies. Host Node, Python and Lima installations
are not required.

Choose **Connect application**, then **Browse…** and select a committed local Git
application with a single origin, supported lockfile, build command and static
output. Review its discovered settings and choose **Connect and build application**.
You can leave the panel open while Surfaces prepares the environment. Inspect the
completed build on the canvas, open its preview, or deploy it locally.

Accepted guidance continues to apply to later builds. Advance, Hold, Reject and
findings remain visible without adding a deployment approval gate.

## Alpha limits

Recovery requires an inactive, verifiable old environment and sufficient disk
space. An active or unknown environment stays preserved and unavailable for this
action. Alpha 3 does not provide general repair or migration of damaged workspaces.

Application support remains bounded to declared static web build integrations.
Dynamic routes and multi-step interactions may remain unresolved. A successful
build does not establish that all guidance was checked or that an external coding
tool used the instructions. This early alpha does not include automatic updates.
