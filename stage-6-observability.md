# Stage 6 — Observability & Security (Monitoring, Logging, Tracing, IAM)

Overview:
- Observability pillars: metrics, logs, traces.
- Security basics: IAM, secrets, scanning, least privilege.

Core tooling:
- Metrics & dashboards: Prometheus + Grafana; cloud alternatives (CloudWatch, Azure Monitor, GCP Monitoring)
- Logs: ELK / OpenSearch / Loki; cloud logging (Cloud Logging, Azure Monitor Logs)
- Tracing: OpenTelemetry + Jaeger
- Security: image scanning (Trivy, Snyk), dependency scanning, secret scanning, IAM review

Cloud specifics:
- Enable cloud provider-managed monitoring (CloudWatch, Stackdriver, Azure Monitor) for quick telemetry.
- Use managed logging/metrics where possible to reduce ops overhead.

Tasks:
- Instrument a simple app to expose metrics (Prometheus client) and logs.
- Deploy Prometheus + Grafana locally or to a cluster; create a dashboard for basic metrics.
- Configure a sample alert (email/Slack) for a high error rate or CPU spike.
- Add tracing via OpenTelemetry and view traces in Jaeger or a hosted service.
- Run image and dependency scans in CI; fail builds on high-severity findings.
- Review and tighten IAM roles for a small set of resources (least privilege).
- Configure retention and log access policies in cloud logging.

Exercises:
- Add Prometheus metrics to the sample app, scrape with Prometheus, and build a Grafana panel.
- Create a CI step that runs Trivy and outputs full scan results.
- Simulate an incident and verify alerts and runbook steps.

Outcome:
- Collect telemetry, alert on key signals, and add baseline security checks to pipelines.

References:
- Prometheus: https://prometheus.io/
- Grafana: https://grafana.com/
- OpenTelemetry: https://opentelemetry.io/
- Trivy: https://github.com/aquasecurity/trivy