# Team Quimby
## Brain Scan 1 (Siemens AIRC)
 
```mermaid
flowchart LR
    Generator[Demo Generator] --> |1a DICOM| QveraIE[Qvera Interface Engine]
    Generator --> |1b DICOM| LaurelBridge
 
    QveraIE --> |2a ORM| EpicRadiant
    QveraIE --> |2b ORM| NuancePS
    QveraIE --> |2c ORM| Visage
 
    LaurelBridge --> |3a DICOM| Visage
    LaurelBridge --> |3b DICOM| SiemensAIRC
    LaurelBridge --> |3c DICOM| Fovia
    LaurelBridge --> |3d DICOM| ACRAssess
   
    SiemensAIRC --> |4a AI Results DICOM SR+SC| LaurelBridge
    SiemensAIRC --> |4b AI Results DICOM SR+SC| Fovia
 
    Visage --> |5 Launch| Fovia
 
    Fovia --> |6 Confirmed Results DICOM SR+SC| LaurelBridge
   
    LaurelBridge --> |7 Confirmed AI Results DICOM SR+SC| Visage
   
    LaurelBridge --> |8a AI Results ORU| NuancePS
    LaurelBridge --> |8b AI Results ORU| ACRAssess
 
    NuancePS --> |9a ORU| Visage
    NuancePS --> |9b ORU| LaurelBridge
    NuancePS --> |9c ORU| EpicRadiant
 
    LaurelBridge --> |10 ORU| ACRAssess
```
