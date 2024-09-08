# Team Curie
## OB Ultrasound Flow Chart

```mermaid
flowchart TD
    Generator[Demo Generator] --> |1 DICOM| QveraIE[Qvera Interface Engine]

    QveraIE --> |2a ORM| EpicRadiant
    QveraIE --> |2b ORM| SmartReporting
    QveraIE --> |2c ORM| SiemensSyngo
    QveraIE --> |2d ORM| IRM

    QveraIE --> |2e DICOM| SiemensSyngo
    QveraIE --> |2f DICOM| Biotics
    QveraIE --> |2g DICOM| Fovia
    QveraIE --> |2h DICOM| ACRAssess
    QveraIE --> |2i DICOM| IRM
    
    Biotics --> |3a AI Results DICOM SR| QveraAIO[Qvera AI Orchestrator]

    QveraAIO --> |4a Notification?!?| EpicRadiant

    QveraAIO --> |5a DICOM Confirmed Results| SiemensSyngo
    QveraAIO --> |5b DICOM Confirmed Results| SmartReporting
    QveraAIO --> |5c DICOM Confirmed Results| IRM
    QveraAIO --> |5d FHIR Confirmed Results| ACRAssess
    
    SmartReporting --> |6a ORU| SiemensSyngo
    SmartReporting --> |6b FHIR DiagnosticReport| QveraAIO

    QveraAIO --> |7 FHIR DiagnosticReport| ACRAssess  
```
