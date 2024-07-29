# The 3 levels of costings
## Phase 1 - testing and sizing
Finding a sweet spot per pod is it one pod 1:1 ratio, or 1:4, or 8:1 per node.

## Phase 2 - optimising workload

- Scaling on Saturation vs. Utilisation. Scale on Saturation
- Test one pod
- Find smooth scaling metric
- Whole Node when setting requests
- Limits if you are actively monitoring

## Phase 3 - cost monitoring

- Realtime profiling tools
- Increase node sizes, to pay less tax M5.8xlarge~
- Do you need storage on ALL nodes?
- 