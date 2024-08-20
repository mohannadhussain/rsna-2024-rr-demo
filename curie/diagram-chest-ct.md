# Team Curie
## Chest CT Flow Chart

```mermaid
flowchart TD
    Generator[Demo Generator] --> |1 DICOM| QveraIE[Qvera Interface Engine]

    QveraIE --> |2a ORM| EpicRadiant
    QveraIE --> |2b ORM| SmartReporting
    QveraIE --> |2c ORM| SiemensSyngo
    QveraIE --> |2d ORM| IRM
    QveraIE --> |2d DICOM| IRM
    QveraIE --> |2e DICOM| SiemensSyngo
    QveraIE --> |2f DICOM| Fovia
    QveraIE --> |2g DICOM| SiemensAIRC
    QveraIE --> |2h DICOM| HOPPR
    QveraIE --> |2i DICOM| ACRAssess
    QveraIE --> |2k DICOM| PocketHealth
    
    
    SiemensAIRC --> |3 AI Results DICOM SR| QveraAIO[Qvera AI Orchestrator]
    HOPPR --> |4 AI Results DICOM SR| QveraAIO
    
    QveraAIO --> |5a Worklist Prioritization| EpicRadiant
    QveraAIO --> |5b AI Results| Fovia
    QveraAIO --> |5c AI Results| IRM

    Fovia --> |6a DICOM Confirmed Results| SiemensSyngo
    Fovia --> |6b DICOM Confirmed Results| IRM
    Fovia --> |6c DICOM Confirmed Results| QveraIE
    Fovia --> |6d DICOM Confirmed Results| PocketHealth
    Fovia --> |6d FHIR Confirmed Results| ACRAssess
    Fovia --> |6e FHIR Confirmed Results| SmartReporting

    QveraIE --> |7 FHIRcast AI Result| EpicRadiant

    SmartReporting --> |8a MDM| SiemensSyngo
    SmartReporting --> |8b ORU| PocketHealth
    SmartReporting --> |8c FHIR DiagnosticReport| ACRAssess
    
```
