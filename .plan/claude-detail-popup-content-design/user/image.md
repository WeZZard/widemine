# Detail Popup Content Design - User / Image

## Fields

| Field | Raw Path | Purpose | Contents | Key |
| --- | --- | --- | --- | --- |
| Data | `source.data` | Supplies the image payload that becomes the user-visible image in Content. | Required base64 string; observed in 40 messages; max observed length 667,412 characters. | true |
| Media Type | `source.media_type` | Identifies how to decode and render the image payload. | Required string; observed values are `image/png` and `image/jpeg`; max observed length 10 characters. | true |
| Type | `source.type` | Identifies the source encoding used with the image payload. | Required string; observed value is `base64`; max observed length 6 characters. | true |
| Type | `type` | Routes the message shape and is already represented outside Content by the popup titlebar badges. | Required string; observed value is `image`; max observed length 5 characters. | false |

## Derived Form Content

| Form Field | Raw Path | Value Source | Rendering |
| --- | --- | --- | --- |
| Data | `source.data` | Read from `source.data` and combine with `source.media_type` and `source.type` for decoding. | Render as an image preview when decodable; do not display the raw encoded string in Content. |
| Media Type | `source.media_type` | Read directly from `source.media_type`. | Render as compact selectable text next to the preview details. |
| Type | `source.type` | Read directly from `source.type`. | Render as compact selectable text next to the preview details. |

## Card Design

```text
+--------------------------------------------------------------------------+
| [User] [Image]                                                 [pin] [x] |
+--------------------------------------------------------------------------+
|                         Content | Metadata | Raw                         |
+--------------------------------------------------------------------------+
| Data                                                                     |
| +----------------------------------------------------------------------+ |
| | <decoded image preview from source.data>                             | |
| | No raw base64 displayed in Content                                   | |
| +----------------------------------------------------------------------+ |
| Media Type               <value from source.media_type>                  |
| Type                     <value from source.type>                        |
+--------------------------------------------------------------------------+
```
