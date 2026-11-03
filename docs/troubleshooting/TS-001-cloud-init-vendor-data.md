# TS-001: cloud-init failed on first boot

**Date:** 3/11/2026
**Symptom:** New VM booted and accepted SSH, but `cloud-init status` showed `error` and the guest agent was missing.
**Investigation:** `cloud-init status --long`, then read the vendor-data file and the Proxmox snippet.
**Root cause:** The YAML snippet had missing spaces after list dashes and a misspelled `systemctl` subcommand.
**Fix:** Rewrote the snippet, destroyed the failed clone, re-cloned from the template.
**Verification:** `cloud-init status` = done, agent active, IP visible in Proxmox.
**Lesson:** YAML needs a space after `-`. The template stores a pointer to the snippet, so fixing the file fixed every future clone.