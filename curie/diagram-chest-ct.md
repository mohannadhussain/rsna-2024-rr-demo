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
    QveraIE --> |2i DICOM| ACRAssess

    Fovia --> |3 DICOM| HOPPR

    Fovia --> |4a LLM Report request| HOPPR
    HOPPR --> |4b Report response JSON| Fovia
    SiemensAIRC --> |4c AI Results DICOM SR| QveraAIO[Qvera AI Orchestrator]
    
    QveraAIO --> |5a Worklist Prioritization| EpicRadiant
    QveraAIO --> |5b AI Results| Fovia
    QveraAIO --> |5c AI Results| IRM
    
    Fovia --> |6a DICOM Confirmed Results| SiemensSyngo
    Fovia --> |6b DICOM Confirmed Results| IRM
    Fovia --> |6c DICOM Confirmed Results| QveraAIO

    HOPPR --> |7 Chat iframe| Fovia

    QveraAIO --> |8a FHIR Confirmed Results| ACRAssess
    QveraAIO --> |8b FHIR Confirmed Results| SmartReporting

    QveraAIO --> |9 FHIRcast AI Result| EpicRadiant

    SmartReporting --> |10a MDM| SiemensSyngo
    SmartReporting --> |10b FHIR DiagnosticReport| QveraAIO

    QveraAIO --> |11 FHIR DiagnosticReport| ACRAssess  
```
