# rw-mycelium

A docs middleman for managing internationalization. This is a sandbox repo.

## Usage

All source docs are maintained in source. Gitlocalize is used to sync source with respective target languages in `i18n` directory.

It is important that the target dir structure is a mirror of the source dir structure, and the Gitlocalize translations are configured accordingly.

### Adding a target language

To create a new target language directory, run this from the root, where `LANG_CODE` is a the [ISO 639-1 code](https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes) of the target language.

```
rsync -av -f"+ */" -f"- *" "./source/" "./i18n/<LANG_CODE>/
```
