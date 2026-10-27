# DevOps Command Reference

A searchable, single-page reference for everyday DevOps and cloud work: the commands you need, copy-ready config files, and links to the official docs.

**Live site:** https://ramisalahhh.github.io/devops-command-reference/

## What's inside

| Area | Tools |
|---|---|
| Linux | Navigation, files and folders, text processing, permissions, users and groups, processes and systemd, packages, networking and SSH, storage, LVM and swap, Bash scripting |
| Source control | Git and GitHub |
| Containers | Docker, Docker Compose |
| Automation | Ansible (inventory, ansible.cfg, playbooks, roles, Vault) |
| CI/CD | Jenkins (Jenkinsfile), GitHub Actions (CI and deploy workflows) |
| Orchestration | Kubernetes (Pods, Deployments, Services, ConfigMaps, Secrets, PV/PVC, StatefulSets, DaemonSets, Jobs, CronJobs) |
| Monitoring | Prometheus, PromQL, Alertmanager, Node Exporter, Grafana |
| Web servers | Nginx (reverse proxy, load balancer), Apache (virtual hosts, .htaccess), Certbot |
| Cloud | AWS CLI (EC2, S3, ELB, Auto Scaling, IAM) |
| Infrastructure as Code | Terraform (variables, outputs, modules, S3 backend, count / for_each) |

Each tool has three parts:

- **Commands**, grouped by task, each with a short explanation and a copy button
- **Files**: ready-to-copy templates (Dockerfiles, docker-compose.yml, Ansible playbooks, Kubernetes manifests, Jenkinsfile, GitHub Actions workflows, prometheus.yml, Nginx/Apache configs, Terraform files)
- **Docs**: links to the official documentation

Press `/` on the site to search everything at once.

## Run it locally

It's one static HTML file with no build step:

```bash
git clone https://github.com/ramisalahhh/devops-command-reference.git
cd devops-command-reference/site
python3 -m http.server 8000      # then open http://localhost:8000
```

## How it's deployed

Every push to `main` runs [`.github/workflows/pages.yml`](.github/workflows/pages.yml), which checks the page and publishes the `site/` folder to GitHub Pages.

## Adding or fixing a command

All content lives in `site/index.html` as plain-text blocks, so no JavaScript changes are needed:

```text
<script type="text/plain" class="cmds" data-sec="docker">
## Group name
docker ps -a ⟶ List all containers, including stopped ones
</script>
```

- Commands: `## Group` starts a group; each line is `command ⟶ description`
- Files: `<script type="text/plain" class="file" data-sec="..." data-name="..." data-lang="yaml">`
- Docs: `Title ⟶ URL ⟶ short note`

Found a mistake or want a command added? [Open an issue](https://github.com/ramisalahhh/devops-command-reference/issues/new/choose) (there are templates for both) or send a pull request.
