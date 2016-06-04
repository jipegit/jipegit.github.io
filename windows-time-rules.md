---
layout: default
permalink: /windows-time-rules
---

# Windows Time Rules

## $STDINFO

{:.table-bordered}
| File Rename          | Local File Move      | Volume File Move     | File Copy            | File Access                             | File Modify          | File Creation      | File Deletion        |
|----------------------|----------------------|----------------------|----------------------|-----------------------------------------|----------------------|--------------------|----------------------|
| Modified  | Modified  | Modified  | Modified  | Modified                     | <b>Modified </b>    | <b>Modified </b>  | Modified  |
| Access    | Access    | <b>Access </b>      | <b>Access </b>      | <b>Access </b> No Change on Vista/Win7 | Access    | <b>Access </b>    | Access    |
| Creation  | Creation  | Creation  | <b>Creation </b>    | Creation                     | Creation  | <b>Creation </b>  | Creation  |
| <b>Metadata d</b>   | <b>Metadata d</b>   | <b>Metadata d</b>   | <b>Metadata d</b>   | <b>Metadata d</b>                      | <b>Metadata d</b>   | <b>Metadata d</b> | Metadata  |

<b>Bold = modified</b>


## $FILENAME

{:.table-bordered}
| File Rename          | Local File Move      | Volume File Move   | File Copy          | File Access          | File Modify          | File Creation      | File Deletion        |
|----------------------|----------------------|--------------------|--------------------|----------------------|----------------------|--------------------|----------------------|
| Modified | <b>Modified</b>    | <b>Modified</b>  | <b>Modified</b>  | Modified | Access   | <b>Modified</b>  | Modified |
| Access  | Access   | <b>Access</b>    | <b>Access</b>    | Access  | Access  | <b>Access</b>    | Access  |
| Creation  | Creation  | <b>Creation</b>  | <b>Creation</b>  | Creation | Creation | <b>Creation</b>  | Creation  |
| Metadata  | <b>Metadata</b>   | <b>Metadata</b> | <b>Metadata</b> | Metadata  | Metadata   | <b>Metadata </b> | Metadata  |

<b>Bold = modified</b>

# Sources

* <https://digital-forensics.sans.org/media/poster-windows-forensics-2016.pdf>
