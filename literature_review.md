# Literature Review

## 1. Digital Forensic Investigation: From Evidence Acquisition to Incident Understanding

Digital forensic investigation is concerned with the identification, preservation, examination, analysis, interpretation, and communication of digital evidence in order to establish what occurred during or following an incident. Although evidence acquisition and artefact extraction remain fundamental forensic activities, contemporary investigations increasingly require investigators to interpret large collections of heterogeneous digital traces and transform them into defensible explanations of past activity.

Digital forensic investigations also operate within wider organisational incident response processes. NIST incident response guidance recognises that incident handling requires coordination between technical response teams and organisational functions such as management and legal departments [1]. More recent NIST guidance further positions incident response within organisational cybersecurity risk management and emphasises the requirements of internal and external stakeholders [2]. Consequently, forensic findings may contribute to technical remediation, legal assessment, regulatory reporting, risk management, business continuity, and organisational decision-making.

This wider organisational context is important because the production of technically accurate findings does not necessarily ensure that an incident will be understood or interpreted in the same way by everyone involved in responding to it. Different participants may have different responsibilities, expertise, information requirements, and priorities. Shreeve et al. investigate security decision-making across stakeholder groups and demonstrate the importance of considering organisational roles when examining security-related decisions [19]. Parkin, Kuhn, and Shaikh similarly investigate organisational cyber-risk perception among executive decision-makers using a scenario-based approach [20].

These studies indicate that cybersecurity incidents are not solely technical analysis problems. Investigation findings must ultimately support individuals and groups who may differ substantially in their responsibilities, technical expertise, and information requirements.

The challenge for digital forensics is therefore broader than acquiring and processing technically correct evidence. Investigators must determine which artefacts are relevant, establish relationships between fragmented observations, reconstruct meaningful activities, assess the strength of resulting conclusions, and communicate those conclusions in forms appropriate to their intended use.

The central problem addressed by this research is therefore not merely how to obtain more forensic evidence, but how to transform fragmented technical observations into defensible, understandable, and inspectable accounts of incident progression.

## 2. Forensic Tools, Timeline Analysis, and the Limits of Chronological Representation

Digital forensic investigations are supported by commercial, open-source, and research tools providing capabilities for evidence processing, artefact extraction, searching, filtering, timeline generation, annotation, visualisation, and reporting. Tools such as Autopsy, Magnet AXIOM, EnCase, and FTK support the examination of digital evidence. Plaso/log2timeline extracts timestamped events from numerous forensic artefacts to produce forensic timelines, while Timesketch supports searching, filtering, tagging, annotation, and collaborative timeline analysis.

These capabilities provide substantial support for forensic investigation. However, organising forensic events chronologically is not equivalent to explaining how an incident occurred. Timeline generation can identify when artefacts were created, modified, accessed, or recorded, but the resulting event collection may still require significant interpretation to determine which observations are relevant, how they relate to one another, and what higher-level activities they represent.

Research on forensic timeline visualisation has attempted to improve this analytical process. Olsson and Boldt developed CyberForensic TimeLab, which presents forensic evidence through an interactive temporal interface intended to assist investigators in identifying relevant periods and coherent groups of evidence [3]. Timeline2GUI similarly demonstrates the use of graphical mechanisms for exploring forensic timelines [4].

These systems establish that alternative representations can support the exploration of temporal evidence. Nevertheless, visual exploration of timestamped artefacts does not itself solve the reconstruction problem. Investigators must still move from low-level observations towards explanations of meaningful activities and incident progression.

The distinction between timeline generation, timeline analysis, and incident reconstruction is therefore fundamental to the proposed research. Chronological organisation provides an important analytical foundation, but a timeline alone does not establish which events form an activity, how multiple activities are connected, or what sequence of actions best explains the available evidence.

## 3. Automated Event Reconstruction: From Low-Level Events to Meaningful Activities

The limitations of chronological representation have motivated research into automated and semi-automated forensic event reconstruction.

Hargreaves and Patterson distinguish low-level forensic events from higher-level activities that are more meaningful to investigators [5]. Their automated timeline reconstruction approach demonstrates that patterns within low-level events can be used to recognise higher-level activities while preserving provenance to the underlying evidence.

This distinction is central to the proposed research. A forensic timeline may contain large numbers of artefact-level observations, while investigators and other users may need to understand a smaller number of meaningful actions describing how an incident progressed. Automated reconstruction therefore has the potential to reduce some of the interpretive effort associated with manually transforming low-level forensic events into coherent activity sequences.

Breitinger, Studiawan, and Hargreaves provide a systematisation of timeline-based event reconstruction and distinguish timeline generation, timeline analysis, and event reconstruction [6]. Their work demonstrates that reconstruction remains a distinct research problem involving the identification of relevant observations, relationships between evidence, inference of past activities, incomplete digital traces, and potentially competing explanations.

However, the production of higher-level reconstructed activities introduces additional challenges. Reconstruction approaches must determine which low-level events belong together, what relationships can defensibly be inferred, how reconstruction methods generalise across different incidents, and how the resulting conclusions remain connected to their evidential foundations.

Automated reconstruction should therefore not be treated merely as a mechanism for producing shorter timelines. Its value depends on whether the resulting incident representation is accurate, traceable, interpretable, and capable of supporting subsequent human reasoning.

## 4. Relationship Modelling and Graph-Based Forensic Reasoning

Incident reconstruction depends on identifying relationships between forensic observations. Events may be connected through temporal proximity, shared users, files, processes, systems, sessions, communications, destinations, or dependencies.

Research has explored formal and graph-based approaches for representing such relationships. Chabot et al. propose a formalised knowledge-representation model for advanced digital forensic timeline analysis that captures semantic relationships between forensic events [7]. Schelkoph, Peterson, and Okolica investigate property graphs as a mechanism for storing and traversing relationships between forensic entities and events [8].

Henseler and Hyde similarly examine technology-assisted analysis of timelines and connections in digital forensic investigations [9]. Their work is particularly relevant to the present research because it investigates relationship-based forensic analysis using the M57-Jean scenario, which is also intended as the primary case study for the proposed platform.

Collectively, these studies demonstrate that forensic evidence can be represented as a network of related entities, artefacts, events, and activities rather than as isolated chronological records. Graph representations may therefore provide an appropriate intermediate structure between normalised forensic events and higher-level incident reconstruction.

However, representing relationships does not automatically produce an understandable explanation of incident progression. Graph structures may assist investigators in traversing complex evidence relationships, but additional mechanisms are required to identify meaningful activity sequences, distinguish evidential strength, generate higher-level incident stages, and communicate those findings to users.

Graph-based modelling should therefore be considered an enabling mechanism for incident reconstruction rather than the final output of the proposed system.

## 5. Evidential Traceability, Uncertainty, and the Risk of Overstating Reconstruction

Automated reconstruction introduces an important forensic problem: a system may produce interpretations that extend beyond directly observed evidence.

Digital evidence may be incomplete, fragmented, duplicated, temporally inconsistent, or compatible with multiple explanations. Consequently, reconstructed incident sequences should not present all events and relationships with equal certainty.

Casey argues that error, uncertainty, and loss are inherent characteristics of digital evidence interpretation and discusses mechanisms for communicating the strength of forensic conclusions [10]. Overill similarly investigates uncertainty bounds associated with digital forensic evidence and hypotheses [11]. Horsman's Digital Evidence Certainty Descriptors provide a qualitative approach to expressing uncertainty in digital forensic conclusions [12].

The communication of forensic conclusions also raises broader questions concerning reporting practice. Sunde compares digital forensic opinion reporting with practices in other forensic science disciplines and highlights the importance of how forensic conclusions and their evidential strength are communicated [23]. Horsman's work on technical reporting further examines challenges associated with presenting digital forensic findings clearly and appropriately [22].

These issues become particularly important when reconstructed incidents are presented visually. A coherent visual sequence may create an impression of causal certainty even where some relationships are inferred, contested, or weakly supported. Visual reconstruction may therefore create a risk of overstating what the evidence establishes.

The proposed platform must address this problem by maintaining explicit links between reconstructed actions and supporting artefacts, allowing users to inspect the evidence underlying each conclusion, and distinguishing directly observed events from correlated relationships, inferred activities, and uncertain interpretations.

The purpose of visual explanation is therefore not to conceal complexity or eliminate evidential ambiguity. It is to make incident progression understandable while preserving the user's ability to examine how the reconstruction was derived.

## 6. Forensic Reporting, Stakeholder Information Needs, and Progressive Disclosure

The results of digital forensic investigations may be communicated through technical reports, investigative reports, evaluative reports, executive summaries, timelines, diagrams, presentations, dashboards, and verbal briefings.

The form and level of detail required depend on the purpose of the communication and its intended audience. Horsman examines different types of reports produced during digital forensic investigations and distinguishes reporting forms serving different investigative and evaluative purposes [21]. This work is relevant to the proposed research because it demonstrates that forensic communication is not a single uniform activity.

Technical investigators may require detailed access to artefacts, timestamps, event relationships, and methodological information. Other organisational participants may initially require a clear account of incident progression, affected systems or information, organisational impact, and the evidential basis of significant conclusions.

The UK National Cyber Security Centre emphasises the importance of clear and accessible communication during cybersecurity incidents and recognises the need to communicate with multiple audiences [13]. Research on stakeholder security decision-making and executive cyber-risk perception further supports the importance of considering differences in organisational roles and information requirements [19], [20].

However, supporting broader understanding should not require the removal of forensic depth. Excessive simplification can disconnect conclusions from evidence, conceal uncertainty, or prevent users from examining the basis of a reconstruction.

The proposed research addresses this tension through progressive disclosure. Users can initially receive a high-level representation of incident progression, then inspect reconstructed incident actions, and finally access detailed technical evidence and uncertainty information when required.

Progressive disclosure therefore provides a mechanism for supporting users with different information requirements without creating completely separate forensic representations for each stakeholder group. The same reconstructed incident remains available at multiple levels of technical detail.

## 7. Human Reasoning, Cybersecurity Expertise, and Incident Understanding

The way cybersecurity information is organised and represented can affect users' ability to develop an accurate understanding of an incident.

Cyber situational awareness concerns the ability to perceive relevant cybersecurity information, understand its significance, and develop an informed understanding of the current security situation. Franke and Brynielsson identify cyber situational awareness as a significant research challenge because cybersecurity environments involve distributed, heterogeneous, and dynamic sources of information [15].

The cognitive demands associated with interpreting forensic evidence are relevant to the proposed research because users may need to mentally integrate timestamps, entities, systems, artefacts, and relationships before they can understand incident progression. Representations that externalise temporal and relational structure may reduce some of this interpretive burden.

Cybersecurity expertise may also influence how users interpret the same information. Experienced forensic investigators may be familiar with technical artefacts, terminology, and investigative processes, while less-experienced users may require contextual explanation before they can understand the significance of the same observations.

Research on security decision-making across stakeholder groups and executive cyber-risk perception indicates that organisational roles and expertise are relevant to how cybersecurity information is interpreted and used [19], [20]. This supports the need to investigate whether alternative representations of forensic findings affect users differently according to their levels of cybersecurity expertise.

The proposed platform therefore does not assume that one simplified representation will be equally appropriate for every user. Instead, progressive disclosure allows users to move between high-level explanations, reconstructed activities, and supporting technical evidence.

This creates an empirical research question concerning whether evidence-linked visual reconstruction can improve incident understanding across different levels of cybersecurity expertise and whether the effects of the interface differ between less-experienced and more-experienced users.

## 8. Cyber Situational Awareness Visualisation and the Limits of Existing Research

Visual analytics combines computational processing with interactive visual representation to support human reasoning over complex information. This approach is particularly relevant to cybersecurity and digital forensics because investigations may involve large numbers of events, entities, systems, relationships, and temporal sequences.

Olsson and Boldt demonstrate the use of temporal visualisation to support exploration of forensic evidence [3]. Osborne and Thinyane similarly investigate visualisation as a mechanism for making complex forensic information easier to explore while maintaining access to the underlying evidence [14].

However, individual visualisation systems provide only a partial understanding of the wider state of cybersecurity visualisation research. Jiang et al. address this issue through a systematic literature review of 54 publications concerning visualisations designed to support cyber situational awareness [24]. Their review analyses the intended stakeholders, information types, data sources, visualisation techniques, levels of situational awareness supported, maturity of proposed systems, challenges, and current practices.

The findings are particularly relevant to the proposed research. Jiang et al. report that existing cyber situational awareness visualisation research predominantly focuses on operational-level personnel. Comparatively limited attention has been given to visualisations designed for managers, higher-level decision-makers, and non-expert users [24].

The review also identifies an imbalance in the types of information represented. Existing research predominantly focuses on threat information, while substantially less attention has been given to visualising incident impact, response plans, and information shared between teams [24].

These findings expose an important limitation in the existing cybersecurity visualisation literature. Although visualisation is widely investigated as a mechanism for helping technical users explore complex security information, comparatively less research examines how interactive visual representations can support broader organisational understanding of incident progression and consequences.

The findings of Jiang et al. are therefore closely aligned with the stakeholder focus of the proposed research. The proposed platform is designed for users with different levels of cybersecurity expertise and aims to provide understandable representations of reconstructed incident progression while maintaining access to technical evidence.

Nevertheless, the proposed research differs from general cyber situational awareness visualisation. It does not attempt to provide a real-time overview of an organisation's current cybersecurity state. Instead, it investigates the retrospective reconstruction and explanation of digital forensic incidents from collected evidence.

Jiang et al.'s findings therefore support the stakeholder and human-centred motivation for the proposed research, but they do not independently establish the complete research gap. The broader gap emerges from considering these findings alongside research on forensic event reconstruction, graph-based reasoning, evidential traceability, uncertainty representation, forensic reporting, and interactive visual explanation.

## 9. From Exploratory Visualisation to Interactive Visual Explanation

Most forensic visualisation systems are designed primarily to support exploration. Investigators search timelines, inspect graphs, filter events, examine artefacts, and manually construct an understanding of incident progression.

Narrative visualisation addresses a related but distinct problem: how complex information can be organised into an understandable sequence while preserving opportunities for exploration.

Segel and Heer distinguish between author-driven and reader-driven approaches to narrative visualisation [17]. This distinction is relevant to digital forensic investigation because an investigator may wish to guide users through an incident in a deliberate sequence while allowing them to inspect individual actions, technical details, and supporting evidence.

Interactive visual explanation therefore offers a possible mechanism for combining structured incident communication with evidence exploration.

The proposed platform extends this idea by generating visual explanations from reconstructed incident data rather than requiring investigators to manually create a separate narrative for each case. Reconstructed incident actions provide the structure for the visual replay, while progressive disclosure allows users to move between incident overview, reconstructed actions, and technical evidence.

However, applying narrative visualisation to forensic reconstruction introduces important risks. Organising evidence into a coherent story may encourage users to perceive causal relationships that are not fully supported, overlook alternative explanations, or place excessive trust in automated reconstruction.

Forensic visual storytelling therefore requires safeguards that are not necessarily central to general-purpose narrative visualisation. Reconstructed actions must remain linked to evidence, uncertainty must remain visible, and investigators must retain the ability to validate, correct, or reject automatically generated interpretations.

The proposed platform therefore adopts a human-in-the-loop approach. Automated processing assists with evidence filtering, event correlation, and reconstruction, while investigators remain responsible for validating the resulting incident representation and using the visual interface as an explanation mechanism.

## 10. Evaluation of Reconstruction and Human-Centred Forensic Interfaces

A forensic reconstruction platform should not be evaluated solely by demonstrating that the software functions.

The proposed system makes two distinct claims.

The first is technical: correlated forensic evidence can be transformed into a defensible reconstruction of meaningful incident activity.

The second is human-centred: presenting that reconstruction through an interactive, evidence-linked visual interface can improve incident understanding compared with conventional forensic timeline representations.

These claims require separate but complementary evaluations.

Technical evaluation should examine reconstruction quality. A reconstructed incident sequence can be compared with a documented or manually established incident sequence. Measures may include identification of significant events, reconstruction of relevant relationships, temporal ordering accuracy, false relationships, missing events, and evidential traceability.

Human-centred evaluation should compare the proposed visual reconstruction interface with a conventional forensic timeline representation. Measures may include incident comprehension, identification of significant incident stages, evidence identification, task completion time, event recall, usability, and perceived cognitive workload. NASA-TLX provides an established instrument for measuring subjective workload [18].

Cybersecurity expertise should also be recorded. Because the platform is intended to support users with different levels of cybersecurity expertise, the evaluation does not need to rely exclusively on experienced digital forensic practitioners. Participants may include computing students, cybersecurity students, technically experienced users, and, where available, practitioners.

This participant strategy is not merely a response to recruitment constraints. It is aligned with the research question. Expertise can be treated as a participant characteristic, allowing the evaluation to investigate whether the interface primarily benefits less-experienced users, provides advantages for more-experienced users, or affects groups differently.

The findings of Jiang et al. further strengthen the rationale for evaluating different expertise levels. Their systematic review identifies limited attention to managers, higher-level decision-makers, and non-expert users within existing cyber situational awareness visualisation research [24]. Evaluating the proposed platform across different levels of cybersecurity expertise can therefore contribute empirical evidence concerning the effectiveness and limitations of stakeholder-oriented visual incident explanation.

## 11. Synthesis and Research Gap

The reviewed literature demonstrates substantial progress in digital forensic evidence processing, timeline generation, event reconstruction, relationship modelling, uncertainty representation, forensic reporting, cyber situational awareness, cybersecurity visual analytics, and narrative visualisation.

Existing forensic tools provide sophisticated mechanisms for extracting, searching, filtering, organising, and exploring digital evidence. However, chronological organisation of forensic events does not itself provide a reconstruction of meaningful incident activity, and substantial interpretation may remain necessary to establish relationships between fragmented observations and develop defensible explanations of incident progression.

Research on automated event reconstruction and graph-based forensic reasoning demonstrates that higher-level activities and relationships can be derived from collections of low-level forensic events. These approaches provide important foundations for reducing manual interpretation and representing connections between entities, artefacts, events, and activities.

However, reconstructing an incident introduces challenges concerning evidential traceability and uncertainty. Digital forensic research demonstrates that conclusions may differ in evidential strength and that forensic interpretations should not be presented as equally certain. These challenges become particularly important when reconstructed findings are transformed into coherent visual representations that may appear more authoritative than the underlying evidence justifies.

Research on forensic reporting and organisational cybersecurity decision-making further demonstrates that forensic findings are used by participants with different responsibilities, expertise, and information requirements. Technical investigators may require detailed access to artefacts and relationships, while other stakeholders may require understandable accounts of incident progression and organisational impact.

Cybersecurity and digital forensic visualisation research demonstrates that interactive representations can support the exploration of complex temporal and relational information. Jiang et al.'s systematic review provides further evidence that existing cyber situational awareness visualisation research predominantly targets operational-level personnel and threat information, with comparatively limited attention to managers, higher-level decision-makers, non-expert users, incident impact, response planning, and information sharing between teams [24].

Narrative visualisation provides mechanisms for combining guided explanation with interactive exploration. However, visualisation and narrative presentation do not automatically guarantee improved incident understanding and may introduce risks of oversimplification, false causal coherence, or misplaced confidence.

Taken together, the literature reveals an underexplored intersection between automated forensic incident reconstruction, evidential traceability, uncertainty representation, stakeholder-oriented information presentation, progressive disclosure, and interactive visual explanation.

There remains scope to investigate systems that transform correlated forensic evidence into meaningful incident reconstructions and present those reconstructions through investigator-controlled visual narratives in which users can move between high-level explanations, reconstructed actions, uncertainty information, and supporting technical evidence.

Furthermore, limited empirical evidence establishes whether evidence-linked visual reconstructions improve incident comprehension, evidence interpretation, analysis efficiency, and cognitive workload compared with conventional forensic timeline representations, particularly across users with different levels of cybersecurity expertise.

This research addresses this gap through the design, implementation, and evaluation of a human-in-the-loop forensic investigation platform combining event correlation, incident reconstruction, evidential traceability, uncertainty representation, progressive disclosure, investigator validation, and interactive visual storytelling.

The research evaluates both the technical quality of the reconstructed incident sequence and the effectiveness of its visual representation. By examining reconstruction accuracy, evidential traceability, incident comprehension, evidence interpretation, analysis efficiency, cognitive workload, and differences associated with cybersecurity expertise, the study aims to determine whether evidence-linked visual reconstruction can provide an effective explanation layer between complex forensic evidence, forensic investigators, and the wider stakeholders who must understand incident findings.

## Expected Outcome

**An automated forensic investigation tool that reduces manual analysis effort and improves comprehension of incident findings through animated incident reconstruction and visual storytelling.**

The expected outcome of this research is a functional human-in-the-loop forensic investigation platform that transforms heterogeneous digital forensic evidence into a structured and evidence-linked reconstruction of incident progression. The platform will combine event correlation and incident reconstruction with interactive visual explanation, progressive disclosure of technical detail, explicit representation of uncertainty, and access to the forensic artefacts supporting each reconstructed action.

The system is expected to support users with different levels of cybersecurity expertise by providing multiple levels of incident representation. Users will be able to obtain a high-level overview of what occurred, explore a reconstructed sequence of meaningful incident actions, and inspect the technical evidence and uncertainty associated with individual conclusions.

The project is also expected to produce empirical evidence concerning whether interactive visual reconstruction improves incident comprehension, evidence interpretation, analysis efficiency, and perceived workload compared with conventional forensic timeline representations.

Designing the platform for users with varying levels of cybersecurity expertise provides an important methodological advantage. The evaluation is not dependent exclusively on recruiting experienced digital forensic practitioners. Participants can be recruited from groups with different levels of cybersecurity knowledge, including computing students, cybersecurity students, technically experienced users, and, where available, practitioners. Cybersecurity expertise can be measured and treated as a participant characteristic within the analysis.

This approach is aligned with the intended purpose of the platform because the research investigates whether progressive disclosure and evidence-linked visual explanation support incident understanding across different levels of expertise. Participant diversity therefore contributes directly to the research design rather than representing only a practical recruitment convenience.

The overall expected contribution is both technical and human-centred: a working framework for evidence-linked forensic incident reconstruction and interactive visual explanation, together with empirical findings concerning how such representations affect incident comprehension, evidence interpretation, analysis efficiency, cognitive workload, and users with different levels of cybersecurity expertise.

# References

[1] P. Cichonski, T. Millar, T. Grance, and K. Scarfone, *Computer Security Incident Handling Guide*, NIST Special Publication 800-61 Rev. 2, National Institute of Standards and Technology, 2012.

[2] A. Nelson, S. Rekhi, M. Souppaya, and K. Scarfone, *Incident Response Recommendations and Considerations for Cybersecurity Risk Management: A CSF 2.0 Community Profile*, NIST Special Publication 800-61 Rev. 3, National Institute of Standards and Technology, 2025.

[3] J. Olsson and M. Boldt, “Computer forensic timeline visualization tool,” *Digital Investigation*, vol. 6, pp. S78–S87, 2009.

[4] B. Debinski, A. Marrington, and I. Mohay, “A log2timeline CSV parser and training scenarios,” 2019.

[5] C. Hargreaves and J. Patterson, “An automated timeline reconstruction approach for digital forensic investigations,” *Digital Investigation*, vol. 9, pp. S69–S79, 2012.

[6] F. Breitinger, H. Studiawan, and C. Hargreaves, “SoK: Timeline based event reconstruction for digital forensics: Terminology, methodology, and current challenges,” *Forensic Science International: Digital Investigation*, vol. 53, Art. 301932, 2025.

[7] Y. Chabot, A. Bertaux, C. Nicolle, and M. T. Kechadi, “A complete formalized knowledge representation model for advanced digital forensics timeline analysis,” *Digital Investigation*, vol. 11, pp. S95–S105, 2014.

[8] D. J. Schelkoph, G. L. Peterson, and J. S. Okolica, “Digital forensics event graph reconstruction,” in *Advances in Digital Forensics XV*, IFIP Advances in Information and Communication Technology. Springer, 2019.

[9] H. Henseler and J. Hyde, “Technology assisted analysis of timeline and connections in digital forensic investigations,” in *Proc. Workshop on Artificial Intelligence and Legal Assistance (LegalAIIA@ICAIL)*, 2019.

[10] E. Casey, “Error, uncertainty, and loss in digital evidence,” *International Journal of Digital Evidence*, vol. 1, no. 2, 2002.

[11] R. Overill, “Uncertainty bounds for digital forensic evidence and hypotheses,” in *Proc. 8th International Conference on Cyber Warfare and Security*, 2013.

[12] G. Horsman, “Digital Evidence Certainty Descriptors (DECDs),” *Forensic Science International: Digital Investigation*, vol. 32, Art. 200896, 2020.

[13] UK National Cyber Security Centre, “Guidance on effective communications in a cyber incident,” NCSC, 2024.

[14] G. Osborne and M. Thinyane, “Visualizing information in digital forensics,” in *Advances in Digital Forensics VIII*, IFIP Advances in Information and Communication Technology, vol. 383. Springer, 2012.

[15] U. Franke and J. Brynielsson, “Cyber situational awareness — A systematic review of the literature,” *Computers & Security*, vol. 46, pp. 18–31, 2014.

[16] E. R. Tufte, *The Visual Display of Quantitative Information*, 2nd ed. Cheshire, CT, USA: Graphics Press, 2001.

[17] E. Segel and J. Heer, “Narrative visualization: Telling stories with data,” *IEEE Transactions on Visualization and Computer Graphics*, vol. 16, no. 6, pp. 1139–1148, 2010.

[18] S. G. Hart, “NASA-Task Load Index (NASA-TLX); 20 years later,” in *Proc. Human Factors and Ergonomics Society Annual Meeting*, vol. 50, no. 9, pp. 904–908, 2006.

[19] B. Shreeve, J. Hallett, M. Edwards, et al., “The best laid plans or lack thereof: security decision-making of different stakeholder groups,” *IEEE Transactions on Software Engineering*, vol. 48, no. 5, pp. 1515–1528, 2022.

[20] S. Parkin, K. Kuhn, and S. A. Shaikh, “Executive decision-makers: a scenario-based approach to assessing organizational cyber-risk perception,” *Journal of Cybersecurity*, vol. 9, no. 1, Art. tyad018, 2023.

[21] G. Horsman, “The different types of reports produced in digital forensic investigations,” *Science & Justice*, vol. 61, no. 5, pp. 627–634, 2021.

[22] G. Horsman, “Technical reporting in digital forensics,” *Journal of Forensic Sciences*, vol. 67, no. 6, pp. 2458–2468, 2022.

[23] N. Sunde, “What does a digital forensics opinion look like? A comparative study of digital forensics and forensic science reporting practices,” *Science & Justice*, vol. 61, no. 5, pp. 586–596, 2021.

[24] L. Jiang, A. Jayatilaka, M. Nasim, M. Grobler, M. Zahedi, and M. A. Babar, “Systematic Literature Review on Cyber Situational Awareness Visualizations,” arXiv:2112.10354, submitted 2021, revised 2022.
