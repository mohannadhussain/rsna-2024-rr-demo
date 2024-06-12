# Team Quimby
## Fall Radiograph Flow Chart

```mermaid
flowchart TD
    Generator[Demo Generator] --> |1a DICOM| QveraIE[Qvera Interface Engine]
    Generator --> |1b DICOM| LaurelBridge

    QveraIE --> |2a ORM| EpicRadiant
    QveraIE --> |2b ORM| NuancePS
    QveraIE --> |2c ORM| Visage

    LaurelBridge --> |3a DICOM| Visage
    LaurelBridge --> |3b DICOM| Milvue
    LaurelBridge --> |3c DICOM| Fovia
    
    Milvue --> |4 AI Results Format??| LaurelBridge

    LaurelBridge --> |5a Worklist Prioritization??| Visage
    LaurelBridge --> |5b AI Results| Fovia

    Fovia --> |6a Confirmed Results| Visage
    Fovia --> |6b Confirmed Results| NuancePS
    Fovia --> |6c FHIR Confirmed Results| ACRAssess

    NuancePS --> |6a ORU| Visage
    NuancePS --> |6c ORU| ACRAssess
```
