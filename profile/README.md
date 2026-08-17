<p align="center">
  <img src="../brand/uns-openhub-wordmark.svg" alt="UNS OpenHub" width="720">
</p>

Self-hosted semantic context infrastructure with open SDKs.

**Website:** [www.uns-openhub.com](https://www.uns-openhub.com)

**Platform:** [Product model and scope](https://www.uns-openhub.com/platform/)

**Integrations:** [Public components and connectivity status](https://www.uns-openhub.com/integrations/)

**Articles:** [Industrial context and architecture notes](https://www.uns-openhub.com/articles/)

**Videos:** [UNS OpenHub on YouTube](https://www.youtube.com/@UNSOPENHUB)

UNS OpenHub combines a self-hosted Runtime with open TypeScript and Python SDKs
for building a governed Unified Namespace. It connects live values, events,
history, metadata, and relationships without tying an object's identity to its
current path.

The Runtime keeps stable entity identity separate from namespace placement,
makes lifecycle relationships queryable, and installs domain semantics on one
generic core.

Manufacturing and Gaming are the current concrete domain profiles. The public
hot-rolling demo is one end-to-end example of the model, not the boundary of
the platform.

> The namespace shows where an object is. The graph explains how it became
> what it is.

## Start with the Runtime

UNS OpenHub Runtime brings the controller, local infrastructure,
configuration, and lifecycle tooling together on infrastructure you control.
Its core data plane combines the controller with open-source PostgreSQL,
Eclipse Mosquitto, QuestDB, and Caddy and requires no managed cloud service.

The SDKs, supporting services, reference application, and bootstrap are
public. The complete integrated Runtime is currently distributed through a
private preview.

Users with preview access can install the public, version-matched bootstrap on
macOS or Linux:

```sh
curl -fsSL \
  https://github.com/uns-openhub/uns-openhub-bootstrap/releases/latest/download/install.sh |
  sh

"$HOME/.local/bin/uns-bootstrap" install
```

Docker or Podman with Compose is required. During the preview, Runtime access
and private controller-image access are separate. Complete version-matched
installation and operating instructions are included in the downloaded
Runtime bundle.

[Open Runtime documentation](https://www.uns-openhub.com/docs/).
[Review the public bootstrap](https://github.com/uns-openhub/uns-openhub-bootstrap).
[Request preview access](https://www.uns-openhub.com/#early-access).

## Choose your SDK

| Language | Package | Use it for |
| --- | --- | --- |
| TypeScript | [`@uns-kit/*`](https://www.npmjs.com/org/uns-kit) | Typed UNS applications, runtime services, metadata, and project scaffolding |
| Python | [`uns-kit`](https://pypi.org/project/uns-kit/) | Python UNS MQTT clients, runtime services, OpenHub access, and project scaffolding |

Both SDKs are developed in the public [`uns-kit`](https://github.com/uns-openhub/uns-kit)
repository. The Python source and documentation live in
[`packages/uns-py`](https://github.com/uns-openhub/uns-kit/tree/master/packages/uns-py).

## Public components

| Repository | Purpose |
| --- | --- |
| [`uns-kit`](https://github.com/uns-openhub/uns-kit) | TypeScript and Python toolkits, runtime libraries, and project scaffolding |
| [`rtt-demo-app`](https://github.com/uns-openhub/rtt-demo-app) | Seeded hot-rolling simulator and end-to-end reference application |
| [`uns-archiver`](https://github.com/uns-openhub/uns-archiver) | QuestDB archiver for UNS data and table packets |
| [`uns-api-global`](https://github.com/uns-openhub/uns-api-global) | Authenticated REST API for current and historical UNS data |
| [`node-red-contrib-uns`](https://github.com/uns-openhub/node-red-contrib-uns) | Node-RED nodes for subscribing to and publishing UNS messages |
| [`uns-openhub-bootstrap`](https://github.com/uns-openhub/uns-openhub-bootstrap) | Minimal verified installer for version-matched Runtime releases |

The integrated controller additionally provides stable entity identity,
namespace placement history, typed relationships, solution profiles,
declarative domain packs, provider add-ons, schema and data-catalog tooling,
automations, service lifecycle supervision, configuration snapshots, and
cluster-aware workload placement.

[Explore the platform model and scope](https://www.uns-openhub.com/platform/).
[Review public and developing integrations](https://www.uns-openhub.com/integrations/).

## How the public pieces fit

```text
TypeScript, Python and Node-RED producers
                  |
                  v
             MQTT / UNS
               |     |
               |     +----> UNS applications built with @uns-kit or uns-kit
               |
               +----------> UNS Archiver ----> QuestDB ----> UNS API Global
```

Each public repository documents its own prerequisites, configuration, and
verification commands. Use `rtt-demo-app` for a first end-to-end example and
`uns-kit` as the TypeScript and Python SDK reference.

## Connectivity direction

Current private development and pilot preparation include:

- `uns-openhub-runtime` — the current private preview and planned deployable
  public entry point.
- `uns-bridge-mqtt` — mapping existing third-party MQTT topics and payloads
  into governed OpenHub context.
- `uns-bridge-opcua` — mapping OPC UA nodes and values into the same model.
- Ignition Edge integration — a read-oriented pilot in preparation, with
  Ignition retaining device drivers, tags, local buffering, and edge behavior.

Assistant capabilities are planned for a later phase as a governed consumer
of platform context. Current private work explores cited operational guidance,
operator-reviewed schema proposals, validated TypeScript and Python service
generation, and disabled-by-default MCP-compatible local tool access. It
currently uses OpenAI; provider and on-prem inference alternatives are being
evaluated.

Follow current delivery status at
[www.uns-openhub.com/integrations/](https://www.uns-openhub.com/integrations/).

## Participate

- Read the shared [contribution guide](https://github.com/uns-openhub/.github/blob/main/CONTRIBUTING.md).
- Report security issues privately as described in the
  [security policy](https://github.com/uns-openhub/.github/blob/main/SECURITY.md).
- Use the affected repository's issue tracker for bugs and focused feature
  requests.

Unless a repository says otherwise, public source is licensed under the MIT
License.
