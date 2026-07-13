# Cyber Incident Replay: Interactive Visual Storytelling of Forensic Evidence for Improved Incident Understanding and Decision-Making

PROJECT SCOPE

The purpose of this project is to automate the reconstruction and display of digital forensic investigations using objects taken from a forensic dataset. The system will use evidence such as system logs, user activity, file system metadata, browser history, and authentication records to create a chronological timeline of occurrences.Instead of presenting investigators with raw logs or static timelines, the software will offer a hierarchical visual analysis. Users will first receive a high-level summary of the incident before selecting different stages to investigate the forensic evidence, which includes linked events, timestamps, and supporting artifacts.

The platform is designed to reduce the cognitive effort required to make sense of massive amounts of forensic data, while maintaining transparency by linking every visualized event to its original source of evidence. The system aims to enhance the efficiency of forensic analysis and communication of investigation findings by representing investigations as an interactive visual narrative, instead of a collection of disconnected log entries.

----------------------------------
RESEARCH QUESTION 

Can interactive visual forensic storytelling improve non-technical stakeholders' comprehension of cyber incidents and support more informed decision-making?

----------------------------------
EXPECTED OUTCOME

An automated forensic investigation tool that reduces manual analysis effort and improves comprehension of incident findings through animated incident reconstruction and visual storytelling. The system is expected to provide different levels of incident representation so that users can obtain an accessible overview of what occurred, explore the reconstructed sequence of incident actions, and inspect the underlying technical evidence when greater detail is required. Rather than replacing forensic investigators or independently communicating forensic conclusions, the platform will operate as an investigator-controlled explanation and decision-support layer between complex forensic evidence and the stakeholders who must understand and respond to the incident.

A further expected outcome is empirical evidence concerning whether interactive visual representations of reconstructed forensic incidents improve incident comprehension, identification of significant incident stages, evidential understanding, analysis efficiency, and the ability to make informed incident-related judgements when compared with conventional forensic timeline representations. The research will also investigate whether these effects differ according to users' levels of cybersecurity expertise.

Designing the platform for users with varying levels of cybersecurity expertise provides an important methodological advantage for the evaluation. Cybersecurity expertise can be measured and treated as an experimental variable rather than imposed as a strict participant eligibility requirement.

The overall expected contribution is therefore both technical and human-centred: a working framework for evidence-linked forensic incident reconstruction and interactive visual explanation, together with empirical findings concerning how such representations affect incident understanding, evidence interpretation, analysis efficiency, and informed judgement across users with different levels of cybersecurity expertise.

-----------------------------
SYSTEM PIPELINE

Forensic Dataset → Evidence Extraction → Event Normalisation → Event Correlation → Timeline Reconstruction → Visual Incident Replay → Dashboard 

------------------------------
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

   As a digital forensic investigator,

   I want to present complex forensic findings through interactive visual stories,

   So that I can improve non-technical stakeholders’ comprehension of cyber incidents and support more informed decision-making.

2. Security Consultant

   As a security consultant,

   I want to review visual reconstructions of previous cyber incidents within a particular organisation,

   So that I can identify recurring attack patterns, explain security weaknesses, and recommend where the organisation should prioritise future security investments.

3. Security Awareness Manager

   As a security awareness manager,

   I want to use visual incident stories based on realistic cyber incidents that have occurred within a particular organisation during employee training,

   So that employees can understand how attacks such as phishing, social engineering, insider threats, and data exfiltration occur, and learn how their actions can influence the progression of a security incident.

4. Cybersecurity Educator

   As a cybersecurity educator,

   I want to use interactive visual stories of historical forensic incidents,

   So that students can better understand incident progression, forensic evidence, and investigative reasoning through realistic case-based learning.

----------------------------------
LITERATURE REVIEW (Summary)

Digital forensic investigations generate large volumes of heterogeneous evidence from sources such as file systems, emails, application artefacts, system logs, and user activity. Existing forensic tools provide effective mechanisms for extracting, searching, filtering, and organising this evidence. However, investigators must still interpret fragmented technical observations and determine how they relate to meaningful activities and incident progression. The challenge is therefore not only obtaining forensic evidence, but transforming low-level observations into a defensible and understandable account of what occurred.

1. Timeline Analysis and Automated Incident Reconstruction

Forensic timelines organise digital evidence chronologically and provide an important foundation for understanding activity across multiple evidence sources. However, chronological organisation alone does not explain which events are significant, how events relate to one another, or what higher-level activities they represent. Large forensic timelines may still require substantial manual interpretation before investigators can establish a coherent account of an incident.

Research on automated event reconstruction attempts to address this problem by identifying relationships between low-level forensic events and transforming them into meaningful activities. Temporal relationships, shared entities, files, users, systems, communications, and other contextual information can be used to correlate events and reconstruct incident progression.

Graph-based representations further support this process by modelling forensic evidence as connected entities, events, artefacts, and activities rather than isolated timeline entries. These approaches provide important foundations for reducing manual analysis effort. However, identifying relationships and reconstructing higher-level activities does not automatically produce an explanation that is understandable to wider incident-response stakeholders.

2. Evidential Traceability, Uncertainty, and Investigator Control

Automated incident reconstruction introduces the risk of presenting inferred relationships as established facts. Digital evidence may be incomplete, fragmented, duplicated, or compatible with multiple explanations. Consequently, reconstructed incident sequences should distinguish between directly observed evidence, correlated events, inferred activities, and uncertain conclusions.

Any automated reconstruction system must therefore preserve evidential traceability. Users should be able to inspect the artefacts supporting each reconstructed action and understand how the system reached its conclusions.

This becomes particularly important when forensic findings are presented visually. A coherent incident animation or narrative may appear authoritative even when some relationships remain uncertain. The proposed platform therefore adopts a human-in-the-loop approach in which automated processing supports evidence filtering, event correlation, and reconstruction, while investigators retain responsibility for validating, correcting, or rejecting reconstructed incident actions.

3. Stakeholder Understanding and Different Levels of Cybersecurity Expertise

Digital forensic findings are used by people with different organisational responsibilities, technical backgrounds, and information requirements. Investigators may require access to detailed artefacts, timestamps, and relationships, while managers, legal teams, incident coordinators, and other stakeholders may initially require a clear explanation of what happened, how the incident progressed, and which conclusions are supported by evidence.

Existing research on cybersecurity decision-making and forensic reporting demonstrates that cybersecurity information is interpreted and used differently across stakeholder groups. Research on cyber situational awareness visualisations also indicates that existing visualisation systems predominantly target operational-level cybersecurity personnel, with comparatively less attention given to managers, higher-level decision-makers, and users with limited cybersecurity expertise.

Supporting wider stakeholder understanding should not require removing technical detail or producing separate systems for every audience. Progressive disclosure provides an alternative approach. Users can initially view a high-level incident overview, explore reconstructed incident actions when greater detail is required, and inspect the supporting forensic evidence and uncertainty associated with individual conclusions.

This allows the same incident reconstruction to support users with different levels of cybersecurity expertise while preserving access to technical depth.

4. Visual Analytics and Interactive Incident Explanation

Visual analytics can help users understand complex temporal and relational information by externalising patterns, sequences, and relationships that would otherwise need to be mentally reconstructed from technical data.

Existing forensic visualisation systems support timeline exploration, filtering, evidence inspection, and relationship analysis. However, most systems primarily support investigators who must manually explore the evidence and construct their own understanding of incident progression.

Interactive visual explanation addresses a different problem: communicating reconstructed incident progression through a structured sequence while allowing users to explore individual actions and supporting evidence.The proposed platform uses reconstructed incident actions to generate an animated visual replay of an incident. Users can move between a high-level incident overview, meaningful incident stages, reconstructed actions, uncertainty information, and supporting technical evidence.

Visual storytelling is therefore not treated as a decorative interface feature. It acts as an explanation layer between complex forensic evidence and the people who must understand the findings. Because visual narratives can oversimplify evidence or create false impressions of certainty, evidential traceability, visible uncertainty, and investigator validation remain essential components of the system.

5. Current Communication of Forensic Incident Findings

Forensic incident findings are commonly communicated through technical reports, executive summaries, presentations, timelines, and incident briefings. Research on digital forensic reporting distinguishes between different reporting formats depending on their purpose and intended audience, while also highlighting the difficulty of communicating complex technical findings clearly without weakening their evidential meaning.

Studies of cybersecurity decision-making further show that stakeholders approach incidents from different organisational perspectives and have different information requirements. Consequently, a single technical representation of forensic findings may not adequately support investigators, executives, legal teams, and other participants involved in understanding and responding to an incident.

Overall, existing approaches support different reporting and communication needs, but communicating forensic incidents to users with varying levels of cybersecurity expertise still depends heavily on manual explanation by technical specialists. The challenge remains to make incident findings understandable to wider stakeholders while preserving access to supporting evidence and sufficient technical depth for forensic scrutiny.

------------------------------
RESEARCH GAP

Existing research has made substantial progress in digital forensic timeline analysis, automated event reconstruction, graph-based relationship modelling, uncertainty representation, forensic reporting, and cybersecurity visualisation. These contributions provide important methods for extracting and organising forensic evidence, identifying relationships between low-level events, reconstructing higher-level activities, and supporting the exploration of complex security information.

However, a disconnect remains between the reconstruction of forensic incidents and the communication of reconstructed findings. Timeline and visual analytics systems primarily support investigators in exploring technical evidence, while automated reconstruction and graph-based approaches focus on identifying activities and relationships within forensic data. Although these approaches can reduce aspects of manual analysis, their outputs are not necessarily designed to provide understandable, evidence-linked explanations of incident progression for users with different levels of cybersecurity expertise. 

This research addresses the identified gap through the design, implementation, and evaluation of a human-in-the-loop forensic investigation platform that transforms heterogeneous forensic evidence into a structured, evidence-linked reconstruction of incident progression and communicates the resulting findings through interactive visual storytelling. By integrating event correlation and incident reconstruction with evidential traceability, investigator validation, and progressive disclosure, the platform aims to reduce the manual effort required to interpret fragmented forensic evidence while enabling users to move between accessible incident overviews, reconstructed actions, and the technical evidence supporting individual conclusions. The overall expected contribution is therefore both technical and human-centred: advancing an integrated approach to forensic incident reconstruction while providing and empirically evaluating an interactive visual explanation framework designed to improve the comprehension and interpretation of incident findings across users with different levels of cybersecurity expertise.

------------------------------------
ARCHITECTURE OUTLINE
┌───────────────────────────────────────────────────────┐
│                       HEADER                          │
├──────────────┬────────────────────────────────────────┤
│              │                                        │
│   TIMELINE   │             STAGE FLOW                 │
│              │                                        │
│              ├────────────────────────────────────────┤
│              │                                        │
│              │             NETWORK FLOW               │
│              │                                        │
│              ├───────────────────┬────────────────────┤
│              │                   │                    │
│              │   EVENT DETAILS   │      EVIDENCE      │
│              │                   │                    │
└──────────────┴───────────────────┴────────────────────┘
