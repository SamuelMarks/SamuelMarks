Both scaling source-code and scaling deployments are difficult. They need not be.

I build tools for a different philosophy of software engineering… one that rejects the bloated, non-native defaults of the modern stack.

 - **Restore Monolithic Velocity**: Polyglot systems create a "synchronization tax" that kills development speed. My `cdd` compilers automate this away, making multi-language development as fast as a Ruby on Rails or Django. And synchronises tests and docs also; improving software quality.
 - **Demystify Deployment**: Software deployment is not as complex as the industry makes it seem. My **[verMan.io](https://verMan.io)** toolchain provides a direct path to reproducible, cross-platform, bare-metal environments, making containers a choice, not a mandate.
 - **Outpace ML Fragmentation**: The pace of ML innovation is relentless. Instead of rewriting models, my **[kitchenSink.ai](https://kitchenSink.ai)** compilers treat entire ML frameworks as its search space.

![SamuelMarks's GitHub stats](https://github-readme-streak-stats-eight.vercel.app/?user=SamuelMarks&card_width=600)

---
### Bidirectional Code Synchronization

My `cdd` compilers are the engine for restoring monolithic velocity. Each one works **bidirectionally**: you can generate typed code *from* a specification, or derive a specification *from* well-structured code. This keeps your polyglot architecture perfectly synchronized.

```mermaid
graph LR
    subgraph "A. Compilers"
        PyComp["cdd-python"]:::blue
        RsComp["cdd-rust"]:::red
        CComp["cdd-c"]:::yellow
        KtComp["cdd-kotlin"]:::green
        EtcComp["..."]
    end

    subgraph "B. Specification"
        OpenAPI["<b>Shared Spec</b><br>(OpenAPI)"]:::navy
    end
    
    PyComp <-- "to/from spec" --> OpenAPI
    RsComp <-- "to/from spec" --> OpenAPI
    CComp <-- "to/from spec" --> OpenAPI
    KtComp <-- "to/from spec" --> OpenAPI

    %% Styling
    classDef blue fill:#4285f4,stroke:#20344b,stroke-width:2px,color:#ffffff
    classDef green fill:#34a853,stroke:#20344b,stroke-width:2px,color:#ffffff
    classDef yellow fill:#f9ab00,stroke:#20344b,stroke-width:2px,color:#ffffff
    classDef red fill:#ea4335,stroke:#20344b,stroke-width:2px,color:#ffffff
    classDef navy fill:#20344b,stroke:#a0a0a0,stroke-width:1px,color:#ffffff
```

This toolkit eliminates boilerplate for data models, API clients, and tests, enabling maximum code reuse while demanding truly native performance.

| Language             | Native Compiler Repository                                   |
| -------------------- | ------------------------------------------------------------ |
| Python               | [cdd-python](https://github.com/offscale/cdd-python)         |
| C                    | [cdd-c](https://github.com/SamuelMarks/cdd-c)                |
| Rust                 | [cdd-rust](https://github.com/offscale/cdd-rust)             |
| Java (Android)       | [cdd-java](https://github.com/offscale/cdd-java)             |
| Kotlin (Android)     | [cdd-kotlin](https://github.com/offscale/cdd-kotlin)         |
| Swift (iOS)          | [cdd-swift](https://github.com/offscale/cdd-swift-ios)       |
| TypeScript (Angular) | [cdd-web-ng](https://github.com/offscale/cdd-web-ng)         |

**Application: Outpacing ML**
The `cdd-python` compiler powers the [kitchenSink.ai](https://kitchenSink.ai) project, which translates models between frameworks.

 | Google                                                             | Other vendors                                               |
 | ------------------------------------------------------------------ | ----------------------------------------------------------- |
 | [tensorflow](https://github.com/SamuelMarks/ml-params-tensorflow)  | [pytorch](https://github.com/SamuelMarks/ml-params-pytorch) |
 | [keras](https://github.com/SamuelMarks/ml-params-keras)            | [skorch](https://github.com/SamuelMarks/ml-params-skorch)   |
 | [flax](https://github.com/SamuelMarks/ml-params-flax)              | [sklearn](https://github.com/SamuelMarks/ml-params-sklearn) |
 | [trax](https://github.com/SamuelMarks/ml-params-trax)              | [xgboost](https://github.com/SamuelMarks/ml-params-xgboost) |
 | [jax](https://github.com/SamuelMarks/ml-params-jax)                | [cntk](https://github.com/SamuelMarks/ml-params-cntk)       |

---
### Demystifying Deployment

Applications, databases, and ML can be deployed by simply with **[verMan.io](https://verMan.io)**—my answer to the heavyweight, container-first paradigm. You can still use this within containers, but you are not limited to non-native abstractions like Docker.

```mermaid
graph TD
    subgraph " "
        Mgrs["<b>Polyglot Version Managers</b><br>Go | Rust | C | Shell"]:::blue
    end

    subgraph " "
        Cloud("Cloud VMs"):::yellow
        Native("Bare Metal<br>Win, Linux, BSD..."):::yellow
        Docker("Docker"):::yellow
    end

    Mgrs --> Cloud
    Mgrs --> Native
    Mgrs --> Docker

    %% Styling
    classDef blue fill:#4285f4,stroke:#20344b,stroke-width:2px,color:#ffffff
    classDef yellow fill:#f9ab00,stroke:#20344b,stroke-width:2px,color:#ffffff
    classDef navy fill:#20344b,stroke:#a0a0a0,stroke-width:1px,color:#ffffff
```

This toolkit uses lightweight, purpose-built _package managers_ for direct and efficient deployment. These work with or without Docker, Kubernetes, etc.

*   **Core Managers**: `rvm`/`nvm`-style _package managers_ written in [Go](https://github.com/offscale/postgres-version-manager-go), [Rust](https://github.com/orgs/offscale/repositories?q=-version-manager-rs), and [C](https://github.com/offscale/libacquire) for consistent cross-platform dependency and version management.
*   **Orchestration Layer**: A mature Python toolkit that uses the core managers to automate deployments across 50+ cloud providers.

| Purpose                                                                  | Repo                                                   |
| ------------------------------------------------------------------------ | ------------------------------------------------------ |
| Provision nodes specified in JSON, across 50+ clouds                     | [offstrategy](https://github.com/offscale/offstrategy) |
| SSH into node provisioned by offstrategy\|offset                         | [offshell](https://github.com/offscale/offshell)       |
| Deprovision node provisioned by offstrategy\|offset from cloud providers | [offswitch](https://github.com/offscale/offswitch)     |
| Bring Your Own Node (BYON) [so can use ↕]                                | [offset](https://github.com/offscale/offset)           |
| Deploy any of [50 "offregister-" prefixed](https://github.com/orgs/offscale/repositories?q=offregister-&language=python) softwares—including clustered databases—to nodes provisioned by offstrategy\|offset | [offregister](https://github.com/offscale/offregister) |
