# Learning Folder Merge Manifest

This file records how `Learning Studio` and `Learning Atlas` were merged.

## Rules

- `Learning Atlas` is the final main folder and keeps its `.git` repository.
- Heavy third-party files keep original filenames.
- `.xlsx` and `.csv` files are preserved and never deleted.
- Older duplicate source systems are moved to `_Review Inbox/` instead of overwriting main versions.
- Target conflicts are resolved with suffixes such as `source-studio`, `older-source`, or `duplicate-candidate`.

## Move List

| Source | Target | Kind | Size | Note |
|---|---|---:|---:|---|
| `/Users/qiqichen/Desktop/Learning Atlas/Consumer Product Knowledge Atlas` | `/Users/qiqichen/Desktop/Learning Atlas/01 Product/Consumer Product Atlas` | dir | 149487 | main atlas version |
| `/Users/qiqichen/Desktop/Learning Atlas/AI PM Knowledge System` | `/Users/qiqichen/Desktop/Learning Atlas/02 AI PM/AI PM Knowledge System` | dir | 689661 | main atlas version |
| `/Users/qiqichen/Desktop/Learning Atlas/Vibe Coding Knowledge Vault` | `/Users/qiqichen/Desktop/Learning Atlas/03 Coding/Vibe Coding Knowledge Vault` | dir | 356501 | main atlas version |
| `/Users/qiqichen/Desktop/Learning Atlas/Git Project Workflow` | `/Users/qiqichen/Desktop/Learning Atlas/03 Coding/Git Project Workflow` | dir | 36253 | main atlas version |
| `/Users/qiqichen/Desktop/Learning Atlas/Website Learning Studio` | `/Users/qiqichen/Desktop/Learning Atlas/04 Website/Website Learning Studio` | dir | 115457 | main atlas version |
| `/Users/qiqichen/Desktop/Learning Atlas/Career Learning Archive` | `/Users/qiqichen/Desktop/Learning Atlas/05 Career/Career Learning Archive` | dir | 146853 | main atlas version |
| `/Users/qiqichen/Desktop/Learning Atlas/Muscle Gain Playbook` | `/Users/qiqichen/Desktop/Learning Atlas/08 Wellbeing/Muscle Gain Playbook` | dir | 69872 | main atlas version |
| `/Users/qiqichen/Desktop/Learning Atlas/Physiology` | `/Users/qiqichen/Desktop/Learning Atlas/08 Wellbeing/Physiology` | dir | 62571 | main atlas version |
| `/Users/qiqichen/Desktop/Learning Atlas/Inner Atlas` | `/Users/qiqichen/Desktop/Learning Atlas/09 Personal Atlas/Inner Atlas` | dir | 94336 | main atlas version |
| `/Users/qiqichen/Desktop/Learning Atlas/Visual Flow Study` | `/Users/qiqichen/Desktop/Learning Atlas/01 Product/Visual Flow Study` | dir | 25664 | main atlas version |
| `/Users/qiqichen/Desktop/Learning Atlas/Subscription Flow Knowledge System` | `/Users/qiqichen/Desktop/Learning Atlas/01 Product/Subscription Flow Knowledge System` | dir | 36395 | main atlas version |
| `/Users/qiqichen/Desktop/Learning Atlas/_manifest.md` | `/Users/qiqichen/Desktop/Learning Atlas/_System/merge_source_manifest_from_atlas.md` | file | 3482 | existing atlas manifest |
| `/Users/qiqichen/Desktop/Learning Atlas/docs.json` | `/Users/qiqichen/Desktop/Learning Atlas/_System/docs.json` | file | 31497 | Mintlify navigation config |
| `/Users/qiqichen/Desktop/Learning Studio/产品经理架构学习资料库` | `/Users/qiqichen/Desktop/Learning Atlas/01 Product/Product Architecture for PM` | dir | 187288 | studio product learning system |
| `/Users/qiqichen/Desktop/Learning Studio/Cosumer-Product-knowledge-atlas` | `/Users/qiqichen/Desktop/Learning Atlas/01 Product/Consumer Product Atlas - source-studio` | dir | 176191 | older studio source, spelling preserved in manifest |
| `/Users/qiqichen/Desktop/Learning Studio/subscription-flow-knowledge-system` | `/Users/qiqichen/Desktop/Learning Atlas/01 Product/Subscription Flow Knowledge System - source-studio` | dir | 37901 | older studio source |
| `/Users/qiqichen/Desktop/Learning Studio/推送与提醒知识包` | `/Users/qiqichen/Desktop/Learning Atlas/01 Product/Notification and Reminder Playbook` | dir | 33749 | studio product learning system |
| `/Users/qiqichen/Desktop/Learning Studio/用户动线学习` | `/Users/qiqichen/Desktop/Learning Atlas/01 Product/Visual Flow Study - source-studio` | dir | 901215 | studio visual flow source |
| `/Users/qiqichen/Desktop/Learning Studio/thinkingdata_event_mapping.md` | `/Users/qiqichen/Desktop/Learning Atlas/01 Product/Event Tracking/thinkingdata_event_mapping.md` | file | 2549 | event tracking note |
| `/Users/qiqichen/Desktop/Learning Studio/pm_event_tracking_learning_guide.md` | `/Users/qiqichen/Desktop/Learning Atlas/01 Product/Event Tracking/pm_event_tracking_learning_guide.md` | file | 21197 | event tracking guide |
| `/Users/qiqichen/Desktop/Learning Studio/AuraThemes埋点方案-数数_updated_v4.xlsx` | `/Users/qiqichen/Desktop/Learning Atlas/01 Product/Event Tracking/AuraThemes埋点方案-数数_updated_v4.xlsx` | file | 30849 | event tracking spreadsheet; preserve xlsx |
| `/Users/qiqichen/Desktop/Learning Studio/HT01_APP上线资料学习说明_小白版.md` | `/Users/qiqichen/Desktop/Learning Atlas/01 Product/Product Launch/HT01_APP上线资料学习说明_小白版.md` | file | 21516 | launch guide |
| `/Users/qiqichen/Desktop/Learning Studio/Vaults/AI_PM_Knowledge_System` | `/Users/qiqichen/Desktop/Learning Atlas/_Review Inbox/Older Vault Sources/AI_PM_Knowledge_System` | dir | 749946 | older vault source; do not overwrite atlas version |
| `/Users/qiqichen/Desktop/Learning Studio/Vaults/Vibe_Coding_Knowledge_Vault` | `/Users/qiqichen/Desktop/Learning Atlas/_Review Inbox/Older Vault Sources/Vibe_Coding_Knowledge_Vault` | dir | 381092 | older vault source; do not overwrite atlas version |
| `/Users/qiqichen/Desktop/Learning Studio/Vaults/Career_Learning_Archive` | `/Users/qiqichen/Desktop/Learning Atlas/_Review Inbox/Older Vault Sources/Career_Learning_Archive` | dir | 109572460 | older vault source; do not overwrite atlas version |
| `/Users/qiqichen/Desktop/Learning Studio/Vaults/Inner_Atlas` | `/Users/qiqichen/Desktop/Learning Atlas/_Review Inbox/Older Vault Sources/Inner_Atlas` | dir | 126782 | older vault source; do not overwrite atlas version |
| `/Users/qiqichen/Desktop/Learning Studio/Website Learning Studio` | `/Users/qiqichen/Desktop/Learning Atlas/_Review Inbox/Older Website Source/Website Learning Studio` | dir | 128926 | older website source; do not overwrite atlas version |
| `/Users/qiqichen/Desktop/Learning Studio/Courses/English_Study` | `/Users/qiqichen/Desktop/Learning Atlas/06 Courses/English Study` | dir | 6718128940 | course material |
| `/Users/qiqichen/Desktop/Learning Studio/Courses/VS_Code_Guide` | `/Users/qiqichen/Desktop/Learning Atlas/06 Courses/VS Code Guide` | dir | 14606616 | course material |
| `/Users/qiqichen/Desktop/Learning Studio/Courses/Web_Foundations_Practice` | `/Users/qiqichen/Desktop/Learning Atlas/06 Courses/Web Foundations Practice` | dir | 874 | course material |
| `/Users/qiqichen/Desktop/Learning Studio/Git，从零到项目的实战` | `/Users/qiqichen/Desktop/Learning Atlas/03 Coding/Git Project Workflow - source-studio` | dir | 36253 | older/studio Git source |
| `/Users/qiqichen/Desktop/Learning Studio/Libraries/Product_Manager_Library` | `/Users/qiqichen/Desktop/Learning Atlas/07 Reference Library/Product Manager Library` | dir | 4892407421 | large reference library |
| `/Users/qiqichen/Desktop/Learning Studio/Libraries/Product_Manager_Interview_Kit` | `/Users/qiqichen/Desktop/Learning Atlas/07 Reference Library/Product Manager Interview Kit` | dir | 5294106 | interview reference library |
| `/Users/qiqichen/Desktop/Learning Studio/Libraries/Reading_Room` | `/Users/qiqichen/Desktop/Learning Atlas/07 Reference Library/Reading Room` | dir | 2117110235 | large reading library |
| `/Users/qiqichen/Desktop/Learning Studio/Libraries/Web3_Product_Research` | `/Users/qiqichen/Desktop/Learning Atlas/07 Reference Library/Web3 Product Research` | dir | 59368 | web3 research library |
| `/Users/qiqichen/Desktop/Learning Studio/Wellbeing/Muscle_Gain_Playbook` | `/Users/qiqichen/Desktop/Learning Atlas/08 Wellbeing/Muscle Gain Playbook - source-studio` | dir | 70244 | older/studio wellbeing source |
| `/Users/qiqichen/Desktop/Learning Studio/Assets` | `/Users/qiqichen/Desktop/Learning Atlas/_Assets/Studio Assets` | dir | 297997 | visual assets |
| `/Users/qiqichen/Desktop/Learning Studio/Workspace Atlas` | `/Users/qiqichen/Desktop/Learning Atlas/_System/Workspace Atlas` | dir | 386005 | workspace maps |
| `/Users/qiqichen/Desktop/Learning Studio/Product Lexicon` | `/Users/qiqichen/Desktop/Learning Atlas/_System/Product Lexicon` | dir | 27712 | naming and terminology system |
| `/Users/qiqichen/Desktop/Learning Studio/Desktop Naming Glossary.html` | `/Users/qiqichen/Desktop/Learning Atlas/_System/Desktop Naming Glossary.html` | file | 1405 | system index |
| `/Users/qiqichen/Desktop/Learning Studio/README_Directory.md` | `/Users/qiqichen/Desktop/Learning Atlas/_System/README_Directory_from_Learning_Studio.md` | file | 2644 | previous studio directory readme |
| `/Users/qiqichen/Desktop/Learning Studio/knowledge_base_workflow_general.md` | `/Users/qiqichen/Desktop/Learning Atlas/_System/knowledge_base_workflow_general.md` | file | 14436 | system workflow note |
| `/Users/qiqichen/Desktop/Learning Studio/project_structure_bilingual_editorial_v4.html` | `/Users/qiqichen/Desktop/Learning Atlas/_System/project_structure_bilingual_editorial_v4.html` | file | 14146 | system index |
| `/Users/qiqichen/Desktop/Learning Studio/WEF_Future_of_Jobs_Report_2025.pdf` | `/Users/qiqichen/Desktop/Learning Atlas/05 Career/WEF_Future_of_Jobs_Report_2025.pdf` | file | 18604420 | career report |
