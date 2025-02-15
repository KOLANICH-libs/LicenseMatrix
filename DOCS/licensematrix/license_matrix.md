# license_matrix

> Auto-generated documentation for [licensematrix.license_matrix](../../licensematrix/license_matrix.py) module.

Make a list of Licenses from a json file.

- [Licensematrix](../README.md#licensematrix-index) / [Modules](../README.md#licensematrix-modules) / [licensematrix](index.md#licensematrix) / license_matrix
    - [LicenseMatrix](#licensematrix)
        - [LicenseMatrix().buildLicenses](#licensematrixbuildlicenses)
        - [LicenseMatrix().closestSPDX](#licensematrixclosestspdx)
        - [LicenseMatrix().closestTitle](#licensematrixclosesttitle)
        - [LicenseMatrix().licenseFromAltName](#licensematrixlicensefromaltname)
        - [LicenseMatrix().licenseFromName](#licensematrixlicensefromname)
        - [LicenseMatrix().licenseFromSPDX](#licensematrixlicensefromspdx)
        - [LicenseMatrix().searchLicenses](#licensematrixsearchlicenses)

## LicenseMatrix

[[find in source code]](../../licensematrix/license_matrix.py#L19)

```python
class LicenseMatrix():
    def __init__():
```

Make a list of Licenses from a json file.

### LicenseMatrix().buildLicenses

[[find in source code]](../../licensematrix/license_matrix.py#L28)

```python
def buildLicenses(
    fileName: str = str(THISDIR / 'license_matrix.json'),
) -> list[License]:
```

Generate a list of licenses from a specified license_matrix...

Use license_matrix.json (part of the project) by default. Json format is:

```json
"MIT": {
 "name": "MIT License (Expat)",
 "altnames": [
  "mit-license",
  "mit",
  "mit license",
  "osi approved :: mit license",
  "License :: OSI Approved :: MIT License"
 ],
 "tags": [
  "Open Source",
  "OSI-Approved",
  "Permissive"
 ],
 "must": [
  "Include Copyright",
  "Include License"
 ],
 "cannot": [
  "Hold Liable"
 ],
 "can": [
  "Commercial Use",
  "Modify",
  "Distribute",
  "Sublicense",
  "Private Use"
 ],
 "type": "Permissive",
 "spdx": "MIT"
},
```

#### Arguments

- `fileName` *str, optional* - the file path to process. Defaults to THISDIR+"/license_matrix.json".

#### Returns

- `list[License]` - list of Licenses

### LicenseMatrix().closestSPDX

[[find in source code]](../../licensematrix/license_matrix.py#L143)

```python
def closestSPDX(spdx: str) -> License:
```

Guarantee a license from a spdx id (may be inaccurate).

#### Arguments

- `spdx` *str* - spdx id to lookup

#### Returns

- `License` - license

### LicenseMatrix().closestTitle

[[find in source code]](../../licensematrix/license_matrix.py#L157)

```python
def closestTitle(name: str) -> License:
```

Guarantee a license from a name (may be inaccurate).

#### Arguments

- `name` *str* - name to lookup

#### Returns

- `License` - license

### LicenseMatrix().licenseFromAltName

[[find in source code]](../../licensematrix/license_matrix.py#L108)

```python
def licenseFromAltName(altName: str) -> License | None:
```

Get the license from an altName.

#### Arguments

- `altName` *str* - altName to lookup

#### Returns

- `Optional[License]` - license

### LicenseMatrix().licenseFromName

[[find in source code]](../../licensematrix/license_matrix.py#L94)

```python
def licenseFromName(name: str) -> License | None:
```

Get the license from a name.

#### Arguments

- `name` *str* - name to lookup

#### Returns

- `Optional[License]` - license

### LicenseMatrix().licenseFromSPDX

[[find in source code]](../../licensematrix/license_matrix.py#L80)

```python
def licenseFromSPDX(spdx: str) -> License | None:
```

Get the license from a spdx id.

#### Arguments

- `spdx` *str* - spdx id to lookup

#### Returns

- `Optional[License]` - license

### LicenseMatrix().searchLicenses

[[find in source code]](../../licensematrix/license_matrix.py#L123)

```python
def searchLicenses(search: str) -> list[License]:
```

Get a list of candidate licenses from a search string.

#### Arguments

- `search` *str* - search string

#### Returns

- `list[License]` - list of licenses
