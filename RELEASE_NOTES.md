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
