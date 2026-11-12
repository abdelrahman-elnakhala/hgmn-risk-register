[README.md](https://github.com/user-attachments/files/34745842/README.md)
# HGMN Risk Register: 10 Risks, 5x5 Scoring

A risk register for a **fictional** Gulf media network, Horizon Gulf Media Network (HGMN). It scores 10 risks on a 5x5 likelihood-impact scale, shows inherent and residual ratings, records treatment decisions and owners, and maps each risk to ISO/IEC 27001:2022 Annex A controls and NIST CSF 2.0 categories.

> **Fictional company, simulated evidence.** HGMN, its systems, the risks, the scores and the owners are invented for portfolio purposes. Nothing here describes a real organisation or a real audit.

## What is in this repository

| Path | Contents |
|---|---|
| `HGMN_Risk_Register.xlsx` | The register (formula-driven), scoring scales, 5x5 heat maps and rating counts |
| `risk_register.csv` | The same register as plain text, for quick viewing on GitHub |
| `images/heat_map_inherent.png`, `images/heat_map_residual.png` | Heat maps before and after planned controls |
| `docs/methodology.md` | Scales, rating bands and scoring rules |
| `docs/executive_summary.md` | One-page summary for non-technical readers |

## Method in brief

- **Score = Likelihood (1-5) x Impact (1-5).** Impact uses the highest applicable dimension: broadcast continuity, source and journalist safety, editorial integrity, legal and regulatory, financial.
- **Bands:** Low 1-4, Medium 5-9, High 10-16, Critical 17-25.
- **Inherent** risk reflects existing controls today. **Residual** risk reflects the planned controls. For an *Accept* decision, residual equals inherent.
- Each risk has an owner (a role), a treatment (mitigate, transfer, accept or avoid), planned controls, and ISO 27001:2022 Annex A and NIST CSF 2.0 references.

Full details are in [`docs/methodology.md`](docs/methodology.md).

## Results

| Rating | Inherent | Residual |
|---|---|---|
| Low | 0 | 0 |
| Medium | 2 | 8 |
| High | 8 | 2 |
| Critical | 0 | 0 |

![Inherent heat map](images/heat_map_inherent.png)
![Residual heat map](images/heat_map_residual.png)

| ID | Asset | Risk scenario | Inherent | Treatment | Residual |
|---|---|---|---|---|---|
| R01 | S3 CMS, website and app | A former freelancer's active account is used to publish false content under the HGMN name. | 12 (High) | Mitigate | 8 (Medium) |
| R02 | S1 Broadcast playout | Ransomware on the broadcast network takes playout off-air for more than 4 hours. | 15 (High) | Mitigate | 8 (Medium) |
| R03 | S8 Source communication | A confidential journalist source identity is exposed through a compromised tool or an insider. | 15 (High) | Mitigate | 10 (High) |
| R04 | S4 Horizon+ streaming and CDN | A DDoS attack disrupts live streaming during a major event. | 12 (High) | Mitigate | 9 (Medium) |
| R05 | Official social media accounts | An official social media account is taken over through phishing and used to post false statements. | 16 (High) | Mitigate | 8 (Medium) |
| R06 | Journalist devices and field equipment | A journalist's phone or laptop is compromised by targeted spear-phishing or spyware. | 16 (High) | Mitigate | 12 (High) |
| R07 | S6 Subscriber database | A breach of subscriber personal data occurs and notification to individuals and the regulator is delayed. | 8 (Medium) | Mitigate | 6 (Medium) |
| R08 | Cloud and CDN suppliers | A supplier outage or compromise disrupts the website and streaming platform. | 12 (High) | Transfer | 8 (Medium) |
| R09 | Regional bureaus | Unauthorised physical access to a regional bureau leads to theft of equipment or footage. | 9 (Medium) | Accept | 9 (Medium) |
| R10 | All critical systems S1 to S8 | An intrusion goes undetected for days because there is no 24/7 monitoring and the incident response plan has never been tested. | 16 (High) | Mitigate | 9 (Medium) |

### Key observations

- Most risks start High because the simulated environment has real gaps: unreviewed contractor accounts, an untested playout restore, undefined source-data classification, and no 24/7 monitoring.
- After planned controls, 2 risks (R03, R06) remain High. Source-identity exposure (R03) stays High because the impact is Severe even when likelihood falls.
- R09 is a worked example of a formal **Accept** decision: it needs a named approver and a review date.

## How to use the workbook

1. Open `HGMN_Risk_Register.xlsx`. Edit only the blue cells (Likelihood and Impact, inherent and residual).
2. Scores, ratings, heat maps and counts recalculate automatically.
3. The band thresholds are editable on the `Scales` sheet.

## Reuse in other projects

- **NIST CSF 2.0 gap assessment:** the inherent scoring supports the risk assessment step.
- **ISO 27001 ISMS:** the register and treatment columns feed the risk assessment, risk treatment plan and Statement of Applicability.
- **Incident response governance:** R07 and R10 connect to breach notification and incident response testing.

## Limitations

- All data is simulated. Scores are the author's judgment, not measured values, and would need evidence and stakeholder workshops in a real engagement.
- The likelihood and impact scales are the author's own and are documented in `docs/methodology.md`.
- Annex A and CSF references should be confirmed against the published standards before reuse.
- This is a design exercise, not a certified assessment.

## What I would improve next

- Add a control-effectiveness column to derive residual scores from evidence.
- Link each risk to a test or monitoring metric.
- Run a short scoring workshop to calibrate likelihood and impact.

## Author and licence

Abdelrahman Elnakhala. Released under the MIT Licence (see `LICENSE`). Last updated 12 November 2026.
