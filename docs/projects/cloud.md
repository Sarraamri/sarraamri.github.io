# Cloud & IoT projects

<span class="badge b-perso">End-of-studies projects</span><span class="badge b-work">Work</span>

!!! note ""
    My two end-of-studies projects, three years apart: containerising a compliance platform on
    Kubernetes with monitoring dashboards (2026, at Vneuron), and a real-time KPI monitoring
    solution built on Raspberry Pi hardware (2023, at SAFRAN Group). Both shipped with the
    documentation someone else could operate them from.

## Containerising Reis™ on Kubernetes

**Stack:** Docker · Kubernetes · AWS · Grafana

End-of-studies project for my Cloud Computing & DevOps engineering degree, carried out as a
Cloud & DevOps intern at Vneuron since February 2026. I containerise the Reis™ compliance
platform, run it on Kubernetes, and build Grafana dashboards so the state of a deployment is
something you can read rather than guess at. Alongside it I document the infrastructure setups
and the procedures that go with them.

That documentation is why this belongs in a QA portfolio: a setup procedure is only correct if
someone has actually followed it, so I write mine from deployments I have run myself.

<!-- TODO (Sarra): two things would make this concrete:
     1. What exactly is containerised (which services / components)?
     2. What do the Grafana dashboards track (pod health, job duration, resource usage)?
     Also: managed EKS or a self-managed cluster? -->

<!-- TODO: a sanitized architecture diagram would carry this whole page:
![Architecture](../assets/cloud-k8s-architecture.png) -->

!!! warning "Confidentiality"
    Reis™ is compliance software for financial institutions. Nothing here includes client names,
    real data, internal URLs, or internal screenshots. Approach and architecture are shown;
    specifics are not.

## Real-time KPI monitoring at SAFRAN Group

**Stack:** Raspberry Pi · Arduino · MQTT · operational dashboards

End-of-studies internship for my Computer Engineering degree (SAFRAN Group, 2023, six months).
I designed a real-time KPI monitoring solution: Arduino-based sensors publishing over MQTT to a
Raspberry Pi, feeding operational dashboards that production teams could read at a glance. I
delivered it with a complete technical documentation set for internal handover, which is the
part that made it usable after I left.

<!-- TODO (Sarra): which KPIs did it actually track, and what did it replace? One concrete
number (readings per minute, machines covered, manual reporting time removed) would make this
land much harder than the description alone. -->

## What this shows

- :white_check_mark: Containers, orchestration, and monitoring in practice, not just on a transcript
- :white_check_mark: Hardware to dashboard: I can follow a system from sensor to screen
- :white_check_mark: Every project handed over with documentation another engineer can work from
