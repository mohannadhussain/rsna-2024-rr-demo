# Team Ettinger
## Prostate Flow Chart

```mermaid
flowchart TD
    Generator[Demo Generator] --> |1a DICOM| InterlinxIE[Interlinx Interface Engine]
    Generator[Demo Generator] --> |1b DICOM|Enlitic

    InterlinxIE --> |2 ORM| Enlitic
    Enlitic --> |3a ORM| InterlinxIE
    Enlitic --> |3b DICOM| InterlinxIE

    InterlinxIE --> |4a ORM| SmartReporting
    InterlinxIE --> |4b ORM| Paxera

    InterlinxIE --> |5a DICOM| Paxera
    InterlinxIE --> |5b DICOM| SiemensAIRC
    InterlinxIE --> |5c DICOM| Fovia
    InterlinxIE --> |5d DICOM| IBIS
    InterlinxIE --> |5e DICOM| ACRAssess
    
    SiemensAIRC --> |6 AI Results Format??| Fovia

    Fovia --> |7 Confirmed results| InterlinxAIO[Interlinx AI Orchestrator]

    InterlinxAIO --> |8a Confirmed Results| Paxera
    InterlinxAIO --> |8b Confirmed Results| SmartReporting
    InterlinxAIO --> |8c FHIR Confirmed Results| ACRAssess

    SmartReporting --> |9a ORU| Paxera
    SmartReporting --> |9b FHIR DR| ACRAssess
```
