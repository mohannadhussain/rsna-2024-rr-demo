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
    LaurelBridge --> |3d DICOM| ACRAssess
    
    Milvue --> |4a AI Results DICOM SR| Fovia    

    Visage --> |5 Launch| Fovia

    Fovia --> |6 Confirmed Results DICOM SR| LaurelBridge

    LaurelBridge --> |7a Confirmed Results DICOM SR| Visage
    LaurelBridge --> |7b Confirmed Results DICOM SR| Milvue
    
    Milvue --> |8a AI Report ORU| LaurelBridge
    
    LaurelBridge --> |9a AI Report ORU| ACRAssess
    LaurelBridge --> |9b AI Report ORU| NuancePS
    LaurelBridge --> |9c AI Report ORU| Visage

    NuancePS --> |10a Signed Report ORU| Visage
    NuancePS --> |10b Signed Report ORU| LaurelBridge
    NuancePS --> |10c Signed Report ORU| EpicRadiant

    LaurelBridge --> |11 Signed Report ORU| ACRAssess
```
