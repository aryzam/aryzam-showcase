# AryZam: Post-Quantum Cryptography Risk Assessment

**Find the cryptography that quantum computers will break, and know what your regulators expect you to do about it.**

AryZam helps European organisations prepare for the post-quantum transition. It scans cloud environments for quantum-vulnerable cryptography, scores the risk, and maps every finding to the regulatory frameworks that apply to them: **DORA**, **NIS2** and Spain's **ENS** (Esquema Nacional de Seguridad).

> This repository is a public overview of the product. The scanner source code is private.
> 🌐 [aryzam.com](https://aryzam.com) · 📄 White paper available on the website

---

## The problem

Data encrypted today with RSA or ECC can be harvested now and decrypted later, once a cryptographically relevant quantum computer exists (*"harvest now, decrypt later"*). Regulators are starting to expect organisations to know where this cryptography lives and to plan their migration, but most mid-market companies have no inventory to start from.

## What AryZam does

| Step | What happens |
|---|---|
| **1. Discover** | Read-only scan of cloud cryptographic assets (AWS Certificate Manager and KMS), using a least-privilege IAM policy. |
| **2. Inventory** | Builds a Cryptographic Bill of Materials (**CBOM**) and exports it in **CycloneDX 1.6** format. |
| **3. Score** | Estimates quantum exposure per asset, based on data lifetime, migration time and expected Q-Day (Mosca's inequality), including *harvest-now-decrypt-later* risk. |
| **4. Map** | Translates each technical finding into the specific regulatory requirements it affects under DORA, NIS2 and ENS. |
| **5. Report** | Produces an executive PDF report for leadership and compliance teams, with prioritised remediation. |

## Architecture

AryZam separates **technical risk** from **regulatory meaning**:

- **Layer 1: Risk engine.** Quantum risk modelling (Mosca's inequality, HNDL exposure, Q-Day horizons).
- **Layer 2: Regulatory translation.** Maps findings to framework controls. For ENS this includes controls such as `mp.com.2`, `mp.info.3`, `op.exp.11`, `op.pl.1` and `op.pl.2`, aligned with the CCN-STIC guidance chain (807, 825, 892).

A CI gate can fail a pipeline when new quantum-vulnerable cryptography is introduced.

## Status

- Scanner **v0.4.0**, with **80 automated tests** passing
- Validated against a live AWS sandbox (ACM / KMS)
- DORA / NIS2 / ENS compliance mapping and executive PDF reporting in place

## Who it's for

European mid-market organisations, particularly in financial services and public-sector supply chains, that need to demonstrate post-quantum readiness under DORA, NIS2 or ENS.

## Team

- **Ariadna Gómez-Zambrano**: Co-founder & CTO · ECE @ Princeton University
  

## Contact

Interested in a pilot assessment or a demo? Get in touch through [aryzam.com](https://aryzam.com).
