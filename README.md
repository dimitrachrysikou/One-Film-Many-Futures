🎯 Επισκόπηση Project


This project involves the creation, curation, and documentation of a critical frame-level image dataset from the public-domain film *House on Haunted Hill (1959)*. The objective is to analyze visual motifs (objects, bodies, spaces, props) and their narrative functions, as well as to conduct a concise audit using a pre-trained Object Detection model (YOLOv8).

---

## 📁Folder and File Structure

```text
one_film_many_futures_groupXX/
│
├── README.md                  # Το παρόν αρχείο επισκόπησης
├── dataset_card.md            # Σύντομη τεκμηρίωση τύπου Dataset Card
├── datasheet_report.pdf       # Αναλυτική τεκμηρίωση (Datasheets for Datasets)
│
├── data/
│   ├── images/
│   │   ├── curated/           # Τελικά curated frames (τουλάχιστον 120 εικόνες)
│   │   └── audit_sample/      # Δείγμα 50 frames για το YOLO audit
│   ├── metadata.csv           # Μεταδεδομένα των τελικών curated frames
│   ├── annotations.csv        # Frame-level επισημάνσεις (human labels)
│   ├── curation_log.csv       # Audit trail επιλογής/απόρριψης όλων των raw frames
│   ├── double_annotation_log.csv # Καταγραφή double annotation (συμφωνίες/διαφωνίες)
│   └── yolo_audit_results.csv    # Αποτελέσματα και συγκρίσεις του YOLO audit
│
├── docs/
│   ├── source_rights_memo.md  # Τεκμηρίωση πηγής, περίληψη & Jurisdiction Note
│   ├── taxonomy.md            # Ταξινομία κατηγοριών (οπτικές & αφηγηματικές)
│   └── labeling_guidelines.md # Οδηγίες επισημείωσης για τους annotators
│
├── outputs/
│   └── yolo_annotated_examples/ # 10-20 ενδεικτικές εικόνες με YOLO detections
│
└── code/
    ├── run_yolo_audit.txt     # Η ακριβής εντολή εκτέλεσης του YOLO
    └── preprocessing_script.py # Scripts προεπεξεργασίας / curation
