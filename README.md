# setup-gnatdoc

> GitHub Action to use gnatdoc

This GitHub Action will install [gnatdoc](https://github.com/AdaCore/gnatdoc)
(GNAT Documentation Generation Tool). It uses Alire and a custom alire index
to build the tool if it is not already in the cache.

## Usage

### Inputs

```yaml
- uses: reznikmm/setup-gnatdoc@v1
  with:
    # A directory to install GNATdoc.
    # Optional. Default is '.gnatdoc'
    install-prefix: .gnatdoc
```

### Example

```yaml
- uses: reznikmm/setup-gnatdoc@v1

- name: Build binari and doc
  run: gnatdoc -P test.gpr --output-dir output --backend html

- name: Archive output
  uses: actions/upload-artifact@v4
  with:
    name: output
    path: ./output
```
