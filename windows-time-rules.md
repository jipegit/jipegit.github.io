---
layout: default
permalink: /windows-time-rules
---

# Windows Time Rules

## $STDINFO

{:.table-bordered}
| File Rename          | Local File Move      | Volume File Move     | File Copy            | File Access                             | File Modify          | File Creation      | File Deletion        |
|----------------------|----------------------|----------------------|----------------------|-----------------------------------------|----------------------|--------------------|----------------------|
| Modified – No Change | Modified – No Change | Modified – No Change | Modified – No Change | Modified – No Change                    | <b>Modified – Change</b>    | <b>Modified – Change</b>  | Modified – No Change |
| Access – No Change   | Access – No Change   | <b>Access – Change</b>      | <b>Access – Change</b>      | <b>Access – Change</b> No Change on Vista/Win7 | Access – No Change   | <b>Access – Change</b>    | Access – No Change   |
| Creation – No Change | Creation – No Change | Creation – No Change | <b>Creation – Change</b>    | Creation – No Change                    | Creation – No Change | <b>Creation – Change</b>  | Creation – No Change |
| <b>Metadata – Changed</b>   | <b>Metadata – Changed</b>   | <b>Metadata – Changed</b>   | <b>Metadata – Changed</b>   | <b>Metadata – Changed</b>                      | <b>Metadata – Changed</b>   | <b>Metadata – Changed</b> | Metadata – No Change |

## $FILENAME

{:.table-bordered}
| File Rename          | Local File Move      | Volume File Move   | File Copy          | File Access          | File Modify          | File Creation      | File Deletion        |
|----------------------|----------------------|--------------------|--------------------|----------------------|----------------------|--------------------|----------------------|
| Modified – No Change | <b>Modified – Change</b>    | <b>Modified – Change</b>  | <b>Modified – Change</b>  | Modified – No Change | Access – No Change   | <b>Modified – Change</b>  | Modified – No Change |
| Access – No Change   | Access – No Change   | <b>Access – Change</b>    | <b>Access – Change</b>    | Access – No Change   | Access – No Change   | <b>Access – Change</b>    | Access – No Change   |
| Creation – No Change | Creation – No Change | <b>Creation – Change</b>  | <b>Creation – Change</b>  | Creation – No Change | Creation – No Change | <b>Creation – Change</b>  | Creation – No Change |
| Metadata – No Change | <b>Metadata – Changed</b>   | <b>Metadata – Changed</b> | <b>Metadata – Changed</b> | Metadata – No Change   | Metadata – No Change   | <b>Metadata – Changed</b> | Metadata – No Change |

## $FILENAME

{:.table-bordered}
| File Rename          | Local File Move      | Volume File Move   | File Copy          | File Access          | File Modify          | File Creation      | File Deletion        |
|----------------------|----------------------|--------------------|--------------------|----------------------|----------------------|--------------------|----------------------|
| Modified | <b>Modified</b>    | <b>Modified</b>  | <b>Modified</b>  | Modified | Access   | <b>Modified</b>  | Modified |
| Access  | Access   | <b>Access</b>    | <b>Access</b>    | Access  | Access  | <b>Access</b>    | Access  |
| Creation  | Creation  | <b>Creation</b>  | <b>Creation</b>  | Creation | Creation | <b>Creation</b>  | Creation  |
| Metadata  | <b>Metadata</b>   | <b>Metadata</b> | <b>Metadata</b> | Metadata  | Metadata   | <b>Metadata </b> | Metadata  |


# Source

* <https://digital-forensics.sans.org/media/poster-windows-forensics-2016.pdf>
