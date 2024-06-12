# Team Ettinger
## Prostate Flow Chart

```mermaid
flowchart TD
    Generator[Demo Generator] --> |1 DICOM| InterlinxIE[Interlinx Interface Engine]

    InterlinxIE --> |2a ORM| EpicRadiant
    InterlinxIE --> |2b ORM| SmartReporting
    InterlinxIE --> |2c ORM| Paxera

    InterlinxIE --> |3a DICOM| Paxera
    InterlinxIE --> |3b DICOM| SiemensAIRC
    InterlinxIE --> |3c DICOM| Fovia
    InterlinxIE --> |3d DICOM| IBIS
    
    SiemensAIRC --> |4 AI Results Format??| InterlinxAIO[Interlinx AI Orchestrator]

    InterlinxAIO --> |5a Worklist Prioritization??| Paxera
    InterlinxAIO --> |5b AI Results| Fovia

    Fovia --> |6a Confirmed Results| Paxera
    Fovia --> |6b Confirmed Results| SmartReporting
    Fovia --> |6c FHIR Confirmed Results| ACRAssess

    SmartReporting --> |6a ORU| Paxera
    SmartReporting --> |6c FHIR DR| ACRAssess
```
