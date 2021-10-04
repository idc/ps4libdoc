# PS4LibDoc
PS4 library documentation.

## See also
* [ps4_nid_resolver_ida](https://github.com/Thunder07/ps4_nid_resolver_ida), a plugin for IDA which makes use of ps4libdoc.
* [ps4_module_loader](https://github.com/SocraticBliss/ps4_module_loader), a plugin for IDA which has its own list of symbols ([`aerolib.csv`](https://github.com/SocraticBliss/ps4_module_loader/blob/master/aerolib.csv)).

## Available versions
* [1.05](https://github.com/idc/ps4libdoc/tree/1.05)
* [1.06](https://github.com/idc/ps4libdoc/tree/1.06)
* [1.76](https://github.com/idc/ps4libdoc/tree/1.76)
* [2.00](https://github.com/idc/ps4libdoc/tree/2.00)
* [2.57](https://github.com/idc/ps4libdoc/tree/2.57)
* [3.00](https://github.com/idc/ps4libdoc/tree/3.00)
* [3.55](https://github.com/idc/ps4libdoc/tree/3.55)
* [3.70](https://github.com/idc/ps4libdoc/tree/3.70)
* [4.00](https://github.com/idc/ps4libdoc/tree/4.00)
* [4.05](https://github.com/idc/ps4libdoc/tree/4.05)
* [4.55](https://github.com/idc/ps4libdoc/tree/4.55)
* [4.74](https://github.com/idc/ps4libdoc/tree/4.74)
* [5.00](https://github.com/idc/ps4libdoc/tree/5.00)
* [5.05](https://github.com/idc/ps4libdoc/tree/5.05)
* [5.56](https://github.com/idc/ps4libdoc/tree/5.56)
* [6.72](https://github.com/idc/ps4libdoc/tree/6.72)
* [6.80 (beta 2)](https://github.com/idc/ps4libdoc/tree/6.80_beta2)
* [7.00](https://github.com/idc/ps4libdoc/tree/7.00)
* [7.55](https://github.com/idc/ps4libdoc/tree/7.55)
* [8.00](https://github.com/idc/ps4libdoc/tree/8.00)
* [8.52](https://github.com/idc/ps4libdoc/tree/8.52)
* [9.00](https://github.com/idc/ps4libdoc/tree/9.00)

## Other
* [misc](https://github.com/idc/ps4libdoc/tree/misc), for things that fall outside of system versions.
* [header](https://github.com/idc/ps4libdoc/tree/header), for a header using a macro name of `PS4LIBDOC_NAME` for all known symbol names.

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
