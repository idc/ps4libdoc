# PS4LibDoc
PS4 library documentation.

### JSON Format
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
      "libraries": [
        {
          "name": "<library name>",
          "is_export": false,
          "symbols": [
            {
              "id": 9819116604689812748,
              "hex_id": "884482872EAD0D0C",
              "encoded_id": "iESChy6tDQw",
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

`name` is either not present or is `null` when the name for the symbol is unknown.
`hex_id` and `encoded_id` are included for human convenience and are not used by tools.