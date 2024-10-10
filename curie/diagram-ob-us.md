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

    QveraAIO --> |4a DICOM Confirmed Results| SiemensSyngo
    QveraAIO --> |4b DICOM Confirmed Results| IRM
    QveraAIO --> |4c FHIR Confirmed Results| SmartReporting
    QveraAIO --> |4d FHIR Confirmed Results| ACRAssess
    
    SmartReporting --> |5a ORU| SiemensSyngo
    SmartReporting --> |5b FHIR DiagnosticReport| QveraAIO

    QveraAIO --> |6 FHIR DiagnosticReport| ACRAssess  
```
