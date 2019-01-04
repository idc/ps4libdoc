# PS4LibDoc
PS4 library documentation.

## See also
* [ps4_nid_resolver_ida](https://github.com/Thunder07/ps4_nid_resolver_ida), a plugin for IDA which makes use of ps4libdoc.

## Available versions
* [1.06](https://github.com/idc/ps4libdoc/tree/1.06)
* [1.76](https://github.com/idc/ps4libdoc/tree/1.76)
* [2.57](https://github.com/idc/ps4libdoc/tree/2.57)
* [3.55](https://github.com/idc/ps4libdoc/tree/3.55)
* [3.70](https://github.com/idc/ps4libdoc/tree/3.70)
* [4.05](https://github.com/idc/ps4libdoc/tree/4.05)
* [4.55](https://github.com/idc/ps4libdoc/tree/4.55)

And [misc](https://github.com/idc/ps4libdoc/tree/misc), for things that fall outside of system versions.

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
