# Start9 Community

[![packaging](https://img.shields.io/badge/packaging-guide-important)](https://docs.start9.com/packaging)
[![developer](https://img.shields.io/badge/developer-matrix-blueviolet)](https://matrix.to/#/#community-dev:matrix.start9labs.com)
[![community](https://img.shields.io/badge/community-matrix-yellow)](https://matrix.to/#/#community:matrix.start9labs.com)
[![registry](https://img.shields.io/badge/registry-community-green)](https://community-registry.start9.com)
[![start9](https://img.shields.io/badge/Start9-Labs-lightgrey)](https://github.com/Start9Labs)

## What This Organization Is

This is the home of every service package on the **StartOS Community Registry**.

[StartOS](https://github.com/Start9Labs/start-technologies) is a Linux-based operating system for running a personal server. Software runs on it as a **service package** (`.s9pk`) — a wrapper that lets an ordinary open-source application be discovered, installed, configured, backed up, and monitored through the StartOS interface. Anyone can write one, and anyone can distribute one; you do not need Start9's permission or infrastructure to do either.

Every repository in this organization is a `<service>-startos` package repo — a **fork of a community developer's own packaging repo**. The developer continues to maintain the package. Start9 hosts the fork, builds it, and publishes the resulting `.s9pk` to the Community Registry.

That division of labor is the whole point of the org, and it's what separates it from [Start9Labs](https://github.com/Start9Labs), where the packages are ones Start9 maintains itself:

|                    | **Start9 Registry** ([Start9Labs](https://github.com/Start9Labs)) | **Community Registry** (this org)       |
| ------------------ | ----------------------------------------------------------------- | --------------------------------------- |
| Written & maintained by | Start9                                                       | The community developer who submitted it |
| Vetted for quality | Yes — recommended by Start9                                        | No — meets objective technical criteria only |
| Covered by Start9 support | Yes                                                         | No                                       |
| Built & published by | Start9                                                           | Start9                                   |

Listing on the Community Registry does **not** imply endorsement or disapproval by Start9, and says nothing about the quality of the service. It means the package met the technical requirements for listing and Start9 chose not to maintain it. See [Default Registries](https://docs.start9.com/start-os/default-registries.html) in the StartOS manual.

## For Users

You already have this registry. The Community Registry ships with StartOS — open the **Marketplace** and click **Switch** beneath the registry title in the sidebar to browse it. Nothing to add or configure.

Bugs and feature requests for a community service belong on **that service's repo in this organization**, not with Start9 support.

## For Developers: Submitting a Package

Read the [Packaging Guide](https://docs.start9.com/packaging) first — it covers the whole workflow, and packaging is designed to be done with an AI coding agent alongside you.

1. **Build your package.** `start-cli s9pk init-workspace` scaffolds a workspace; `start-cli s9pk init-package "<Name>"` scaffolds the package. Follow the [Quick Start](https://docs.start9.com/packaging/quick-start.html) and the [recipes](https://docs.start9.com/packaging/recipes.html).
2. **Work the [Pre-Publish Checklist](https://docs.start9.com/packaging/publishing.html#pre-publish-checklist).** Tag conventions followed, `tsc` / tests / pack all green, README current, and the service installed and exercised end-to-end on a real StartOS device. These must pass *before* you submit — the pipeline builds and ships on merge, so anything broken ships too.
3. **Email [submissions@start9.com](mailto:submissions@start9.com)** with a link to your public GitHub repository.
4. **Start9 forks your repo into this organization** and replies with any feedback.
5. **Address feedback with PRs against the fork** — not against your original repo. From this point on, the fork in this org is the upstream for the community pipeline.

## The Release Pipeline

Once your fork lives here, packages move through two registries:

| Registry           | URL                                                                              | How a build gets there              |
| ------------------ | -------------------------------------------------------------------------------- | ----------------------------------- |
| **community-beta** | [community-beta-registry.start9.com](https://community-beta-registry.start9.com) | Automatically, on every PR merge     |
| **community**      | [community-registry.start9.com](https://community-registry.start9.com)           | Promoted from beta, on your go-ahead |

So the loop for every change and every version bump is:

1. **Open a PR** against your fork here.
2. **Merge** — a workflow automatically builds, tags, and deploys to **community-beta**. You never run a publish command yourself.
3. **Test the beta build**, and get others to. This is where a release soaks before it reaches users.
4. **Give the go-ahead** when it's ready — email [submissions@start9.com](mailto:submissions@start9.com) or open an issue on your fork, and Start9 promotes it to production. The developer makes this call, not Start9.

> [!NOTE]
> The email-and-issue loop is clunky — we know. A developer portal with self-service submission and one-click promotion is actively being built. Until it ships, this is the interface.

## You Don't Have To Publish Here

Nothing about StartOS packaging requires Start9. You can run **your own registry** forever — install the StartOS Registry service on a StartOS device, point `start-cli` at it, and publish to it directly. See [Hosting a Registry](https://docs.start9.com/packaging/host-registry.html).

Plenty of developers do both: a personal registry for alpha builds they iterate on, and a community submission for the stable ones.

## Get Help

- **[Packaging Guide](https://docs.start9.com/packaging)** — the full reference
- **[Developer Matrix room](https://matrix.to/#/#community-dev:matrix.start9labs.com)** — packaging questions, live help
- **[Community Matrix room](https://matrix.to/#/#community:matrix.start9labs.com)** — general StartOS discussion
</content>
</invoke>
