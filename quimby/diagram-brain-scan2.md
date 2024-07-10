# Team Quimby
## Brain Scan 2 (Icometrix)

```mermaid
flowchart TD
    Generator[Demo Generator] --> |1a DICOM| QveraIE[Qvera Interface Engine]
    Generator --> |1b DICOM| LaurelBridge

    QveraIE --> |2a ORM| EpicRadiant
    QveraIE --> |2b ORM| NuancePS
    QveraIE --> |2c ORM| Visage

    LaurelBridge --> |3a DICOM| Visage
    LaurelBridge --> |3b DICOM| Icometrix
    LaurelBridge --> |3c DICOM| Fovia
    LaurelBridge --> |3d DICOM| ACRAssess
    
    Icometrix --> |4a AI Results DICOM SR+SC| Fovia
    Icometrix --> |4b AI Results DICOM SR+SC| ACRAssess

    Visage --> |5 Launch| Fovia

    Fovia --> |6 Confirmed Results DICOM SR| Icometrix

    Icometrix --> |7 Recalculated Scores DICOM SR+SC| LaurelBridge

    LaurelBridge --> |8a ORU Confirmed Results| Visage
    LaurelBridge --> |8b ORU Confirmed Results| NuancePS
    LaurelBridge --> |8c ORU Confirmed Results| EpicRadiant
    LaurelBridge --> |8d ORU Confirmed Results| ACRAssess

    NuancePS --> |8a ORU| Visage
    NuancePS --> |8b ORU| ACRAssess
    NuancePS --> |8c ORU| EpicRadiant
```
