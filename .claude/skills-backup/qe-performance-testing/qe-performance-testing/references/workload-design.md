# Workload design

Model demand explicitly: arrival rate versus concurrent users, think time, session length, operation ratios, payload sizes, data cardinality, caching, and warm/cold states. A concurrency cap does not guarantee a request rate. Closed-loop clients can reduce offered load when a system slows; record how this affects the interpretation.

Measure end-user transaction latency and throughput alongside errors, queueing, saturation, and relevant server resources. Specify percentile population, duration, sample size, and warm-up exclusions. Do not add or average unrelated percentiles as if mathematically interchangeable. Separate client-side timeouts, generator overload, and server failures. Repetition and variability matter when comparing baselines.

Define concrete stop criteria before running: approved latency/error/health limits, maximum load/duration/cost, unexpected external traffic, lost observability, or data safety concerns. Start the authorized campaign with the reviewed minimal-load phase only if included; progression to higher load must also be approved, not inferred. Restore injected configuration and data within the authorized cleanup scope.

Source: [Grafana k6 load test types](https://grafana.com/docs/k6/latest/testing-guides/test-types/), checked 2026-09-21. Its traffic-pattern distinctions inform this original planning workflow; numerical examples in documentation are not project requirements. Verify the installed tool's configuration semantics before implementation.
