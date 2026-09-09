# Cloud & IoT projects

<span class="badge b-perso">End-of-studies projects</span><span class="badge b-qa">Test design</span><span class="badge b-work">Work</span>

!!! note ""
    My two end-of-studies projects, three years apart. In 2026 I moved the Reis™ KYC platform off
    manual deployment and onto Kubernetes, with an automated pipeline and a full observability
    stack, then validated it against 16 requirements I had written first. In 2023, at SAFRAN, a
    two-person team built a manufacturing-order tracking application with barcode scanning on the
    shop floor.

## Containerising the Reis™ KYC platform on Kubernetes

**Engineering degree, end-of-studies project, 2026 · Vneuron**

**Stack:** Docker · Kubernetes · GitHub Actions · Prometheus · Grafana · Loki

### The problem

Reis™ KYC ran as five services deployed by hand. A crashed service stayed down until somebody
noticed and went to the server. There was no rollback, no automated delivery, and no visibility
into what the platform was doing while it ran.

### What I did

I picked the orchestrator against documented criteria rather than by preference, comparing Docker
Compose, Docker Swarm, Kubernetes and HashiCorp Nomad on containerisation, autoscaling,
self-healing and pipeline support, and recording why each one won or lost.

Then I delivered it in four iterations, each with a written acceptance criterion I had to satisfy
before starting the next one:

1. Cluster and persistent storage ready
2. All five services running in containers
3. Delivery automated end to end
4. Metrics, logs and alert routing in place

The pipeline runs static analysis and the image build in parallel, then deploys only if both
succeed: under 14 minutes from a push to a running update, with no manual steps.

### How I validated it

This is the part of the project I care most about. I wrote the requirements first, 9 functional
and 7 non-functional, gave every one of them a verification method, then ran one test per
requirement and recorded what actually happened:

| Category | Tests | Pass | Partial | Fail |
| --- | --- | --- | --- | --- |
| Functional | 9 | 7 | 2 | 0 |
| Non-functional | 7 | 7 | 0 | 0 |
| **Total** | **16** | **14** | **2** | **0** |

Each test carries an identifier, the requirement it traces back to, the exact procedure, the
expected result, the observed result, and a status.

??? example "Three of the sixteen tests"
    **Self-healing.** Procedure: delete a running application pod, then watch the pod list.
    Expected: a replacement reaches Running in under 120 seconds. Actual: replacement created
    immediately and Running in **12 seconds**. Pass.

    **Autoscaling under load.** Procedure: apply the autoscaler, run a stress workload calling the
    service continuously, and watch the autoscaler. Expected: replicas increase once CPU passes
    the 70% threshold. Actual: CPU reached **315%** of the configured request and the platform
    scaled from **1 replica to 5**. Pass.

    **Secrets hygiene.** Procedure: search the repository history for credential keywords, then
    list the credentials held by the cluster. Expected: nothing in plaintext anywhere in history.
    Actual: no matches in history; every credential held as a cluster secret. Pass.

The two partial results are reported as partial rather than rounded up to a pass: alert routing
was defined but no notification channel was connected, and the static-analysis gate ran in
warning mode instead of blocking the pipeline. Both are written up as the next hardening steps,
alongside automated load testing in the pipeline and immutable image tags.

!!! tip "Why this belongs on a QA portfolio"
    Before designing anything, I took the existing internal deployment guide and followed it step
    by step on a clean machine. The friction points that surfaced became inputs to the design.
    That is the same habit as everything else on this site: execute the documented steps, and
    treat whatever breaks as a finding.

    The health-check timings in the final setup were also derived from an observed failure rather
    than guessed, which is the difference between configuration that looks right and configuration
    that has been tested.

!!! warning "Confidentiality"
    Reis™ is Vneuron's proprietary compliance software. This page covers my own infrastructure and
    testing work only. It deliberately contains no product internals: no component names or
    versions, no addresses, ports or namespaces, no configuration, no code, and nothing about any
    client.

## Manufacturing-order tracking at SAFRAN

**Bachelor's degree, end-of-studies project, 2023 · SAFRAN · two-person team**

**Stack:** Angular · Spring · Raspberry Pi 4 · barcode scanners

### The problem

Manufacturing orders moved through the workshops with no live tracking, and a significant share
of them were missing their contracted start and end dates. Nobody could see where a given order
actually was without walking the floor and asking.

### What we built

A web application with three dashboards: work-in-progress tracking, production planning, and a
KPI view covering work in progress and on-time production, each computable per production unit
and per workshop.

The tracking came from the shop floor itself. Every order carries one barcode on its routing
sheet, and each workshop got a scan point at its entry and another at its exit: a handheld
scanner feeding a script on a Raspberry Pi, which updates the order's state in the application.
Order states are colour-coded on the board, so status is readable at a glance rather than looked
up.

The hardware was chosen the same way I would later choose an orchestrator: Raspberry Pi 4 and
Arduino Uno compared against processing power, flexibility and ease of use, with the reasoning
written down.

### Test design, before I knew that was what it was

Each of the eight core use cases was specified with an actor, a precondition, a postcondition, a
nominal scenario and an exception scenario. Reading them back now, they are test cases: every one
has a happy path and a named failure path, including duplicate records, missing data on import,
the wrong file format, empty required fields, a scan with no matching order, and a rejection at
quality control.

Validation ran in the real environment. We installed the scanning bench in an actual workshop and
had the production agents scan orders in and out themselves, with the scope deliberately narrowed
to orders passing through a single workshop so that one path could be verified end to end. Each
scan had exactly one predictable expected result, the order's state changing on the board, which
made every scan a pass or a fail.

!!! note "What I would do differently"
    The performance requirement said processing should be "as close to real time as possible",
    with no number attached, which makes it impossible to test. I would put a figure on it now.
    The specification also contradicted itself about whether one of the three roles needed to
    authenticate: one table said it did not, two others listed authentication as a precondition.
    That is exactly the kind of inconsistency I now catch in review, and finding it in my own
    older work is a fair measure of the distance covered.

## What this shows

- :white_check_mark: Requirements written first, tested one by one, and partial results reported as partial
- :white_check_mark: Technology and hardware chosen against documented criteria, not preference
- :white_check_mark: Validation in real conditions with real users, and procedures verified by walking them
