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

User stories describe system requirements from the perspective of different users by identifying who will use the system, what they want to achieve, and why the capability is valuable.

1. Digital Forensic Investigator

*As a* digital forensic investigator,
*I want* to generate interactive visual stories of forensic incidents,
*So that* I can clearly communicate investigation findings to technical and non-technical stakeholders.

2. Security Consultant

*As a* security consultant,
*I want* to review visual stories of previous cyber incidents within a particular organisation,
*So that* I can explain recurring security weaknesses and recommend areas for future security improvement.

3. Security Awareness Manager

*As a* security awareness manager,
*I want* to generate simplified visual stories of previous cyber incidents,
*So that* I can use realistic incident scenarios to improve employee cybersecurity awareness.

4. Cybersecurity Educator

*As a* cybersecurity educator,
*I want* to generate high-level graphical summaries of historic forensic incidents,
*So that* I can share these with my students and discuss the case histories.

----------------------------------
LITERATURE REVIEW
