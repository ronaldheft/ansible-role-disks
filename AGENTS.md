# Agent guidance

This repository contains an Ansible role that discovers disks, partitions them, creates or resizes filesystems, and mounts them. Read `readme.md` for the role inputs when changing its public interface; inspect the affected task file for implementation.

Treat selected block devices and their filesystems as persistent user data. Before changing disk selection or lifecycle behavior, trace the resolved device path and the effects of `state`, `force`, `resizefs`, and `mount_state`. Validate behavior only with disposable virtual disks; run a playbook against real hosts or disks only after Ron explicitly authorizes that operation. Keep `no_log` on tasks that handle device identity facts.

The repository has no tracked tests or CI workflow. For documentation-only changes, inspect the rendered Markdown diff. For role changes, report the exact syntax or disposable-device validation performed; do not imply an apply succeeded when only syntax was checked.
