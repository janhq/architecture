# ADR #001:Revamp Inference Extension

## Authors

@tikikun

## Legend

TBD

## Context

### Status Quo

The current approach to different inference providers are shown with the 3 extensions below
- https://github.com/janhq/jan/tree/dev/extensions/inference-nitro-extension
- https://github.com/janhq/jan/blob/dev/extensions/inference-openai-extension
- https://github.com/janhq/jan/tree/dev/extensions/inference-triton-trtllm-extension

Main technical concerns:

- The way these inference extensions are coded are defying the way how most of the extension framwork, or, as in Jan framework case, work.
  - Extension of how it was abtrated in Jan framework is a standalone application
  - Extension should handle more cases due to above nature rather than solve single use-case
  - Extension itself can be reused and add more functionalities (add more providers of inference, re-solve both local and remote cases)
- Ultilities must come from framework level (core), not coming from copy code files all over
- Code duplication

Main SDK/devrel concerns:
- We must have different layers of contributing.
  - For example if you are coming from Deepinfra and want to connect Jan to the Deepinfre. You only need to write or add a simple adapter or config to main inference extension, not rewrite the entire extension which is in itself a standalone app
  - Should cater for developer audience: Core/App contributor, Third-party provider (eg above), Inference engine provider. The current approach is, everyone is an extension developer.

### Consideration

![Proposed Change](img/inference-provider.png)

## Decision

TBD

## Detailed Design

TBD
