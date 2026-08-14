# Rollback Process

1. CD pipeline always runs pre-change backup.
2. If verify step fails, rollback playbook runs automatically.
3. Rollback re-applies latest backup for the target host.
4. Save config and re-run verification manually if needed.
5. Open incident PR with root-cause notes before next change.
