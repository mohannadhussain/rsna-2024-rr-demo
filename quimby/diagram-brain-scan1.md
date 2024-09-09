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
    LaurelBridge --> |3c DICOM| ACRAssess
   
    SiemensAIRC --> |4 AI Results DICOM SR+SC| LaurelBridge
 
    LaurelBridge --> |5 AI Results| Visage
   
    LaurelBridge --> |6a AI Results ORU| NuancePS
    LaurelBridge --> |6b AI Results ORU| ACRAssess
 
    NuancePS --> |7a ORU| Visage
    NuancePS --> |7b ORU| LaurelBridge
    NuancePS --> |7c ORU| EpicRadiant
 
    LaurelBridge --> |8 ORU| ACRAssess
```
