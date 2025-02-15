# license_type

> Auto-generated documentation for [licensematrix.license_type](../../licensematrix/license_type.py) module.

Represent a license.

- [Licensematrix](../README.md#licensematrix-index) / [Modules](../README.md#licensematrix-modules) / [licensematrix](index.md#licensematrix) / license_type
    - [License](#license)
        - [License().\_\_repr\_\_](#license__repr__)
        - [License().\_\_str\_\_](#license__str__)
        - [License().isCopyleft](#licenseiscopyleft)
        - [License().isPermissive](#licenseispermissive)
        - [License().isPublicDomain](#licenseispublicdomain)
        - [License().isViral](#licenseisviral)
        - [License().isWeakCopyleft](#licenseisweakcopyleft)
        - [License().mergeBoth](#licensemergeboth)
        - [License().mergeIntoDest](#licensemergeintodest)
        - [License().naiveCompatDest](#licensenaivecompatdest)
        - [License().naiveCompatDestLinking](#licensenaivecompatdestlinking)
        - [License().naiveCompatSource](#licensenaivecompatsource)
        - [License().naiveCompatSourceLinking](#licensenaivecompatsourcelinking)
        - [License().termsCompatible](#licensetermscompatible)
    - [equal](#equal)
    - [getMostStrictType](#getmoststricttype)
    - [mergeSPDX](#mergespdx)

Source: represents an existing license
Dest: represents a new combined license (possibly for a combined work)

## License

[[find in source code]](../../licensematrix/license_type.py#L12)

```python
class License():
    def __init__(
        name: str = '',
        altNames: list[str] | None = None,
        tags: list[str] | None = None,
        must: list[str] | None = None,
        cannot: list[str] | None = None,
        can: list[str] | None = None,
        typeIn: str = '',
        spdx: str = '',
        fromDict: dict[(str, Any)] | None = None,
    ):
```

Represent a license.

Source: represents an existing license
Dest: represents a new combined license (possibly for a combined work)

### License().\_\_repr\_\_

[[find in source code]](../../licensematrix/license_type.py#L71)

```python
def __repr__() -> str:
```

Get the string representation.

### License().\_\_str\_\_

[[find in source code]](../../licensematrix/license_type.py#L75)

```python
def __str__() -> str:
```

To string.

### License().isCopyleft

[[find in source code]](../../licensematrix/license_type.py#L87)

```python
def isCopyleft():
```

Is the License Copyleft?

### License().isPermissive

[[find in source code]](../../licensematrix/license_type.py#L79)

```python
def isPermissive():
```

Is the License Permissive?

### License().isPublicDomain

[[find in source code]](../../licensematrix/license_type.py#L95)

```python
def isPublicDomain():
```

Is the License Public Domain?

### License().isViral

[[find in source code]](../../licensematrix/license_type.py#L91)

```python
def isViral():
```

Is the License Viral?

### License().isWeakCopyleft

[[find in source code]](../../licensematrix/license_type.py#L83)

```python
def isWeakCopyleft():
```

Is the License Weak Copyleft?

### License().mergeBoth

[[find in source code]](../../licensematrix/license_type.py#L99)

```python
def mergeBoth(rhs: License):
```

Combine two licenses into one super license.

Performs no checks on compatibility, this is up to the user.

#### Arguments

- `rhs` *License* - the other license to merge

#### Returns

- `License` - the new, combined license

### License().mergeIntoDest

[[find in source code]](../../licensematrix/license_type.py#L121)

```python
def mergeIntoDest(dest: License):
```

Combine two licenses into one super license, but preserve the...

destination name. Performs no checks on compatibility, this is up to the user.

#### Arguments

- `dest` *License* - the other license to merge

#### Returns

- `License` - the new, combined license

### License().naiveCompatDest

[[find in source code]](../../licensematrix/license_type.py#L225)

```python
def naiveCompatDest(dest: License) -> bool:
```

Check the source (self) is compatible with the destination license (rhs).

#### Arguments

- `dest` *License* - the destination license

#### Returns

- `bool` - are the licenses compatible?

### License().naiveCompatDestLinking

[[find in source code]](../../licensematrix/license_type.py#L205)

```python
def naiveCompatDestLinking(dest: License) -> bool:
```

Check the source (self) is compatible with the destination license (rhs).

For linking licenses

#### Arguments

- `dest` *License* - the destination license

#### Returns

- `bool` - are the licenses compatible?

### License().naiveCompatSource

[[find in source code]](../../licensematrix/license_type.py#L187)

```python
def naiveCompatSource(dest: License) -> bool:
```

Check the destination (rhs) is compatible with the source license (self).

#### Arguments

- `dest` *License* - the destination license

#### Returns

- `bool` - are the licenses compatible?

### License().naiveCompatSourceLinking

[[find in source code]](../../licensematrix/license_type.py#L167)

```python
def naiveCompatSourceLinking(dest: License) -> bool:
```

Check the destination (rhs) is compatible with the source license (self).

For linking licenses

#### Arguments

- `dest` *License* - the destination license

#### Returns

- `bool` - are the licenses compatible?

### License().termsCompatible

[[find in source code]](../../licensematrix/license_type.py#L143)

```python
def termsCompatible(dest: License) -> bool:
```

Check the destination terms (rhs) are compatible with the source license terms (self).

#### Arguments

- `dest` *License* - the destination license

#### Returns

- `bool` - are the license terms compatible?

## equal

[[find in source code]](../../licensematrix/license_type.py#L281)

```python
def equal(licenseA: License, licenseB: License) -> bool:
```

Are two licenses equal?

#### Arguments

- `licenseA` *License* - the first license
- `licenseB` *License* - the second license

#### Returns

- `bool` - equal?

#### See also

- [License](#license)

## getMostStrictType

[[find in source code]](../../licensematrix/license_type.py#L246)

```python
def getMostStrictType(typeA: str, typeB: str) -> str:
```

Return the most 'strict' type of license from the available types.

#### Arguments

- `typeA` *str* - type of the first license
- `typeB` *str* - type of the second license

#### Returns

- `str` - the most 'strict' type

## mergeSPDX

[[find in source code]](../../licensematrix/license_type.py#L264)

```python
def mergeSPDX(spdxA: str, spdxB: str) -> str:
```

Combine the spdx ids.

#### Arguments

- `spdxA` *str* - spdx of the first license
- `spdxB` *str* - spdx of the second license

#### Returns

- `str` - combined spdx
