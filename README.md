# PS4LibDoc
PS4 library documentation.

### JSON Format
```json
{
  "<library>": {
    "modules": {
      "<module>": {
        "exports": [
          {
            "id": 9819116604689812748,
            "hex_id": "884482872EAD0D0C",
            "encoded_id": "iESChy6tDQw",
            "name": "<export>"
          }
        ]
      }
    }
  }
}
```

`name` is either not present or is `null` when the name for the export is unknown.
`hex_id` and `encoded_id` are included for human convenience and are not used.

`exports` was chosen to be an array rather than an object since names must be strings, which would not cleanly work for `id`.