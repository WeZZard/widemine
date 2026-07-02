# User / Image

## Fields
| Field | Purpose | Contents | Key | Summary |
|---|---|---|---|---|
| `source` | Container for the embedded image source used by the thumbnail and image detail view. | Required object; count 40; contains `data`, `media_type`, and `type`. | false | false |
| `source.data` | Embedded image payload rendered as the card thumbnail and used to derive the navigation size label. | Required string; count 40; max length 667412; base64 image data samples start with PNG `iVBOR...` or JPEG `/9j/...` prefixes. | true | true |
| `source.media_type` | Media type that tells the renderer how to decode and label the image. | Required string; count 40; max length 10; observed values include `image/png` and `image/jpeg`. | true | false |
| `source.type` | Source encoding marker that tells the renderer how to interpret `source.data`. | Required string; count 40; max length 6; observed value `base64`. | true | false |
| `type` | Raw content subtype marker that routes this user content block to image rendering. | Required constant string `image`; count 40. | false | false |

## Derived Car Form Content
| Field | Source Field | Contents |
|---|---|---|
| Image Data | `source.data` | Raw base64 image data. |
| Media Type | `source.media_type` | Raw media type value. |
| Source Type | `source.type` | Raw source type value. |

## Message Navigation Item Design
```text
+--------------------------------------------------------------------------------+
| User / Image                                                      14:32:07      |
| image/png | base64 | 667412 chars                                             |
+--------------------------------------------------------------------------------+
  category / subtype                                             spacer  time
  summary contents
```

Preview rules:
- Line 1 is always `User / Image`, flexible spacer, then the timestamp.
- Line 2 shows `source.media_type`, `source.type`, and a compact character-count label derived from `source.data`.
- Use `image` as the fallback summary when source fields are missing or unreadable.
- Do not show raw base64 in the navigation item.

## Message Card Design
```text
+------------------------------------------------------------------------------------------------+
| User / Image                                                      14:32:07 [Raw] [Copy JSON]   |
+------------------------------------------------------------------------------------------------+
| Content Form                                                                                   |
|                                                                                                |
|  Image                                                                                         |
|  +------------------------------------------------------------------------------------------+  |
|  | [thumbnail rendered from source.data when source.media_type is supported]                 |  |
|  |                                                                                          |  |
|  | image/png | base64 | 667412 chars                                                        |  |
|  +------------------------------------------------------------------------------------------+  |
|                                                                                                |
|  Image Details                                                                                 |
|  +--------------+---------------------------------------------------------------------------+  |
|  | Media Type   | image/png                                                                 |  |
|  | Source Type  | base64                                                                    |  |
|  | Content Type | image                                                                     |  |
|  | Data         | iVBORw0KGgoAAAANSUhEUg...                                               |  |
|  +--------------+---------------------------------------------------------------------------+  |
|                                                                                                |
|  Raw opens formatted raw JSON for this timeline item; Copy JSON copies the raw event. The     |
|  visible image is rendered from `source.data`, while the table keeps the raw source fields     |
|  available for inspection without expanding the full base64 payload by default.                |
+------------------------------------------------------------------------------------------------+
```
