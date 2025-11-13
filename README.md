I write open-source developer tools to speedup engineering of scalable software. [`#rewriteInC`](https://rewriteInC.io). Foci on: [cross-platform multicloud](https://verMan.io), [multi-ML](https://kitchenSink.ai), and compilers ([python](https://github.com/offscale/cdd-python); [C](https://github.com/SamuelMarks/cdd-c); …) to translate types across—and within—codebases.

![SamuelMarks](https://github-readme-streak-stats-eight.vercel.app/?user=SamuelMarks)

Graphically, I maintain a [cross-platform multicloud Docker-optional 1-click deployment platform](https://verMan.io) and engineer new compilers to: [keep languages in-sync](https://compilers.com.au); [make ML libraries the search-space](https://kitchenSink.ai); and [generate C SDKs + wrap them for dozens of languages](https://rewriteInC.io):

```mermaid
graph TD
    subgraph Deployment
        cloud("Cloud (AWS; Azure; Google; ...)")
        native("Native (Windows; Linux; UNIX; ...)")
        vm("VMs; Docker; …")
        wasm("WASM")
    end

    subgraph ML
        ml_python("Python compiler")
    end
```

```mermaid
graph TD
    subgraph Frontend
        android["Android (Kotlin [KMP])"]
        ios("iOS (Swift / KMP)")
        desktop("Desktop (KMP)")
        web("Web (KMP)")
        cli("CLI")
        sdk("SDK (C)")
    end

    subgraph Backend
        c("C")
        python("Python")
        rust("Rust")
        typescript("TypeScript")
    end

    Backend <-->|OpenAPI compilers| Frontend
```

### Deploy at any scale
*From one [e.g., embedded] device to 10,000 servers:*
 - [old] 59+ Python repos with ["off" prefix](https://github.com/offscale?q=off&language=python);
 - [new] cross-platform [very] cross-platform package managers:
   - C89 base depending on each OS's crypto and network lib [libacquire](https://github.com/offscale/libacquire);
   - [rvm](https://rvm.io)/[nvm](https://github.com/nvm-sh/nvm) style cross-platform package managers:
      - [postgres-version-manager-go](https://github.com/offscale/postgres-version-manager-go) in Go;
      - ["version-manager-rs" suffixed](https://github.com/orgs/offscale/repositories?q=-version-manager-rs&language=rust) and [verman-schema-rs](https://github.com/verman-io/verman-schema-rs) Rust crates.
 - [new] [verMan.io](https://verMan.io) for 1-click deploys: any {ML,database,server}; any {cloud,VM,docker,machine}; from/to any OS.

| Purpose                                                                  | Repo                                                   |
| ------------------------------------------------------------------------ | ------------------------------------------------------ |
| Provision nodes specified in JSON, across 50+ clouds                     | [offstrategy](https://github.com/offscale/offstrategy) |
| SSH into node provisioned by offstrategy\|offset                         | [offshell](https://github.com/offscale/offshell)       |
| Deprovision node provisioned by offstrategy\|offset from cloud providers | [offswitch](https://github.com/offscale/offswitch)     |
| Bring Your Own Node (BYON) [so can use ↕]                                | [offset](https://github.com/offscale/offset)           |
| Deploy any of [50 "offregister-" prefixed](https://github.com/orgs/offscale/repositories?q=offregister-&language=python) softwares—including clustered databases—to nodes provisioned by offstrategy\|offset | [offregister](https://github.com/offscale/offregister) |

#### Competitive advantage

  - Support for more cloud vendors;
  - Uses normal Python packages deployable to PyPi, as opposed to Puppet/Chef/Ansible with their custom systems;
  - [WiP] Deploy to any operating system (cross-platform: SunOS, Windows, Linux, macOS, OpenBSD);
  - [WiP] Experiment with different versions of each package, including clustered variants.

### Multicloud
*From one cloud vendor to many:*
 - [old] See aforementioned [Apache Libcloud](https://libcloud.apache.org) and [Fabric](https://fabfile.org) utilising Python repos;
 - [new] C89 [google-cloud-c](https://github.com/offscale/google-cloud-c) library (soon: auto-generate entire library, and other vendors);
 - [planned] autogenerate vendors other than Google Cloud.

#### Competitive advantage

  - [C89] Can be called from most any programming language and runs in all environments;
  - [planned] Build specific abstractions for multicloud, like: container-as-a-Service; ML-as-a-Service; Storage-as-a-Service; &etc.

### Multi-ML
*From one machine-learning framework to many:*
 - [old] Python repo from my first PhD: [ml-glaucoma](https://github.com/SamuelMarks/ml-glaucoma);
 - [new] 10+ Python repos with ["ml-params" prefix](https://github.com/SamuelMarks?tab=repositories&q=ml-params&language=python):

 | Google                                                             | Other vendors                                               |
 | ------------------------------------------------------------------ | ----------------------------------------------------------- |
 | [tensorflow](https://github.com/SamuelMarks/ml-params-tensorflow)  | [pytorch](https://github.com/SamuelMarks/ml-params-pytorch) |
 | [keras](https://github.com/SamuelMarks/ml-params-keras)            | [skorch](https://github.com/SamuelMarks/ml-params-skorch)   |
 | [flax](https://github.com/SamuelMarks/ml-params-flax)              | [sklearn](https://github.com/SamuelMarks/ml-params-sklearn) |
 | [trax](https://github.com/SamuelMarks/ml-params-trax)              | [xgboost](https://github.com/SamuelMarks/ml-params-xgboost) |
 | [jax](https://github.com/SamuelMarks/ml-params-jax)                | [cntk](https://github.com/SamuelMarks/ml-params-cntk)       |

#### Competitive advantage

  - Keep up-to-date with latest innovations without porting to favourite framework;
  - Experiment with every model on all major Python ML frameworks.

### Native development, cross-platform, without tradeoffs

Compilers to automatically translate—within and—between:

| Language             | Compiler                                               |
| -------------------- | ------------------------------------------------------ |
| Python               | [cdd-python](https://github.com/offscale/cdd-python)   |
| C                    | [cdd-c](https://github.com/SamuelMarks/cdd-c)          |
| Java (Android)       | [cdd-java](https://github.com/offscale/cdd-java)       |
| Kotlin (Android)     | [cdd-kotlin](https://github.com/offscale/cdd-kotlin)   |
| Swift (iOS)          | [cdd-swift](https://github.com/offscale/cdd-swift-ios) |
| TypeScript (Angular) | [cdd-web-ng](https://github.com/offscale/cdd-web-ng)   |
| Rust                 | [cdd-rust](https://github.com/offscale/cdd-rust)       |

#### Competitive advantage

  - [intra-language] Automatically synchronise tests (& mocks), docs, types & interfaces;
  - [exolanguage] Translate changes across language boundaries;
  - Develop multi-language applications—e.g., Android, iOS, web, backend—as fast as single-language applications (compare with: Django or Ruby on Rails) and at a higher quality thanks to increased consistency, test coverage and doc coverage.
