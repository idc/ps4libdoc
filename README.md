# PS4LibDoc
PS4 library documentation.

## See also
* [ps4_nid_resolver_ida](https://github.com/Thunder07/ps4_nid_resolver_ida), a plugin for IDA which makes use of ps4libdoc.

## JSON Format
Documentation is split across a file for each executable, to improve diffs.

```json
{
  "shared_object_name": "<name if is a shared library>",
  "shared_object_names": [
    "<imported shared object name>"
  ],
  "modules": [
    {
      "name": "<module name>",
      "version_major": 0,
      "version_minor": 0,
      "libraries": [
        {
          "name": "<library name>",
          "version": 0,
          "is_export": false,
          "symbols": [
            {
              "id": 9819116604689812748,
              "hex_id": "884482872EAD0D0C",
              "encoded_id": "iESChy6tDQw",
              "type": "<symbol type>",
              "name": "<symbol name>"
            }
          ]
        }
      ]
    }
  ]
}
```

`is_export` indicates if that library is exported, if false, it is imported.

* `type` when not present is `Function`. Can be `Function`, `Object`, `TLS`, or `Unknown11` (TBD).
* `name` is either not present or is `null` when the name for the symbol is unknown.
* `hex_id` and `encoded_id` are included for human convenience and are not used by tools.
