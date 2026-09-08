# Terraform modules with auto-generated documentation

<span class="badge b-doc">Docs as code</span><span class="badge b-perso">Personal project</span>

!!! note "The idea"
    Terraform modules for AWS (VPC, EC2, S3) whose reference documentation is generated straight
    from the source with `terraform-docs`, kept honest by a GitHub Actions workflow that validates
    and redeploys the docs continuously. Hand-written infrastructure docs drift the moment the
    code changes — this makes the source of truth literal.

## How it works

1. Each module (VPC, EC2, S3) carries descriptions on its variables and outputs.
2. `terraform-docs` generates the reference tables from those descriptions.
3. A GitHub Actions workflow runs `terraform validate` and regenerates docs on every push.
4. <!-- TODO if true: the workflow fails when generated docs are out of date — drift becomes a broken build. -->

```yaml title=".github/workflows/docs.yml (excerpt)"
# TODO: paste the real excerpt from your repo
- name: Generate module docs
  run: terraform-docs markdown table ./modules/vpc > docs/vpc.md
```

## Links

- :material-github: **Repository:** `TODO: link your repo`

## What this shows

- :white_check_mark: Docs-as-code end to end — source → generated reference → CI
- :white_check_mark: Real AWS/Terraform hands-on work
- :white_check_mark: Automation instinct — quality gates instead of manual discipline
