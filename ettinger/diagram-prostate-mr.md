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

    InterlinxIE --> |5 FHIR Observation - PSA Value| HAPI_FHIR

    InterlinxIE --> |6a DICOM| Paxera
    InterlinxIE --> |6b DICOM| SiemensAIRC
    InterlinxIE --> |6c DICOM| Fovia
    InterlinxIE --> |6d DICOM| IBIS
    InterlinxIE --> |6e DICOM| ACRAssess

    Fovia --> |7 Query for PSA Value| HAPI_FHIR
    
    SiemensAIRC --> |8 AI Results DICOM SR| Fovia

    Paxera --> |9 Launch| Fovia

    Fovia --> |10 Confirmed Results DICOM SR| InterlinxAIO[Interlinx AI Orchestrator]

    InterlinxAIO --> |11 Confirmed Results DICOM SR| Paxera
    
    InterlinxAIO --> |12a Confirmed Results FHIR| SmartReporting
    InterlinxAIO --> |12b Confirmed Results FHIR| ACRAssess

    Paxera --> |13 Launch| SmartReporting

    SmartReporting --> |14a ORU| Paxera
    SmartReporting --> |14b FHIR DiagnosticReport| ACRAssess
```
