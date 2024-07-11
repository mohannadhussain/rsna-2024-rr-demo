# Team Curie
## OB Ultrasound Flow Chart

```mermaid
flowchart TD
    Generator[Demo Generator] --> |1 DICOM| QveraIE[Qvera Interface Engine]

    QveraIE --> |2a ORM| EpicRadiant
    QveraIE --> |2b ORM| SmartReporting
    QveraIE --> |2c ORM| SiemensSyngo
    QveraIE --> |2d DICOM| SiemensSyngo
    QveraIE --> |2e DICOM| Biotics
    QveraIE --> |2f DICOM| Fovia
    QveraIE --> |2g DICOM| ACRAssess
    
    Biotics --> |3 AI Results Format??| QveraAIO[Qvera AI Orchestrator]

    QveraAIO --> |4a Worklist Prioritization| SiemensSyngo
    QveraAIO --> |4b AI Results| Fovia

    Fovia --> |5a Confirmed Results| SiemensSyngo
    Fovia --> |5b Confirmed Results| SmartReporting
    Fovia --> |5c FHIRConfirmed Results| ACRAssess

    SmartReporting --> |6a ORU| SiemensSyngo
    SmartReporting --> |6b ORU| PocketHealth
    SmartReporting --> |6c FHIR DR| ACRAssess
```
