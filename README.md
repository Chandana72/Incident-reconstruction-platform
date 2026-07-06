# Cyber Incident Replay: Interactive Visual Storytelling of Forensic Evidence for Improved Incident Understanding and Decision-Making

PROJECT SCOPE

The purpose of this project is to automate the reconstruction and display of digital forensic investigations using objects taken from a forensic dataset. The system will use evidence such as system logs, user activity, file system metadata, browser history, and authentication records to create a chronological timeline of occurrences.Instead of presenting investigators with raw logs or static timelines, the software will offer a hierarchical visual analysis. Users will first receive a high-level summary of the incident before selecting different stages to investigate the forensic evidence, which includes linked events, timestamps, and supporting artifacts.

The platform is designed to reduce the cognitive effort required to make sense of massive amounts of forensic data, while maintaining transparency by linking every visualized event to its original source of evidence. The system aims to enhance the efficiency of forensic analysis and communication of investigation findings by representing investigations as an interactive visual narrative, instead of a collection of disconnected log entries.

----------------------------------
RESEARCH QUESTION 

Can interactive visual forensic storytelling improve non-technical stakeholders' comprehension of cyber incidents and support more informed decision-making?

----------------------------------
DATASET

This project uses the **M57 Jean** forensic scenario from the **Digital Corpora** collection. The dataset represents a realistic digital forensic investigation involving a fictional employee's workstation and contains a variety of forensic artefacts, including Windows Event Logs, browser history, email data, file system metadata, registry information, user activity, and deleted files.

The M57 Jean scenario was selected because it is publicly available, well documented, and widely used for digital forensics education and research. Its realistic structure and diverse evidence make it well suited for reconstructing incident timelines and evaluating interactive forensic visualisation.

Dataset Sources:

- CFReDS Reference: https://cfreds.nist.gov/all/DigitalCorpora/2008M57Jean
- Digital Corpora Download: https://digitalcorpora.org/corpora/scenarios/m57-jean/

  Note: The dataset is not included in this repository due to its size and should be downloaded directly from Digital Corpora.

----------------------------------
USER STORIES

The platform is designed to transform complex forensic findings into understandable visual incident narratives for users with different levels of technical expertise.

Digital Forensic Investigator

  **As a** digital forensic investigator,

  **I want to** present investigation findings through an interactive visual incident replay,

  **So that** I can clearly communicate how the incident unfolded to both technical and non-technical stakeholders without relying solely   on raw forensic logs and static timelines.
  
---

Security Consultant
  
  **As a** security consultant,
  
  **I want to** review visual reconstructions of previous cyber incidents within a particular organisation,
  
  **So that** I can identify recurring attack patterns and security weaknesses, clearly explain the organisation's risk exposure, and recommend where future security improvements and investments should be prioritised.

---

Security Awareness Manager

**As a** security awareness manager,

**I want to** use visual incident stories based on realistic cyber incidents during employee training,

**So that** employees can understand how attacks such as phishing, social engineering, insider threats, and data exfiltration occur and learn how their actions can influence the progression of a security incident.

---

Cybersecurity Lecturer

**As a** cybersecurity lecturer,

**I want to** demonstrate cyber incidents and forensic investigations through interactive visual storytelling,

**So that** students can better understand incident progression, attacker and user actions, forensic evidence, and investigative reasoning than they would through static timelines, reports, or raw log files alone.

----------------------------------
LITERATURE REVIEW

----------------------------------
