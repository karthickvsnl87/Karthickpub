# Cisco 9300 DevNetOps Lab

## Goal
Manage Cisco 9300 configuration through GitHub PR and CI/CD.

## Workflow
1. Create a feature branch.
2. Edit host vars or templates.
3. Open PR to main.
4. CI validates syntax and lint.
5. Merge to main.
6. CD runs backup, deploy, and verify.
7. If verify fails, rollback runs.

## Required GitHub Secrets
- SW_USER
- SW_PASS
- SW_ENABLE_PASS

## Local Validation
Run:
- ansible-galaxy collection install -r requirements.yml
- ansible-playbook playbooks/backup.yml
- ansible-playbook playbooks/deploy.yml
- ansible-playbook playbooks/verify.yml

## First Safe Test
1. Add VLAN 40 in host vars.
2. Raise PR.
3. Merge after CI passes.
4. Confirm on switch:
	show vlan brief | include 40
