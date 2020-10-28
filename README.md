# rw-mycelium

A docs middleman for managing internationalization. This is a sandbox repo.

## Usage

All source docs are maintained in `source`. [Gitlocalize](https://gitlocalize.com/) is used to sync source docs with respective target languages in `i18n` directory.

It is important that the target dir structure is a mirror of the source dir structure, and the Gitlocalize translations are configured accordingly.

This allows builds of respective language repo sites to maintain the same path structure, only having to change the target language dir.

### Adding a target language

To create a new target language directory, run this from the root, where `LANG_CODE` is a the [ISO 639-1 code](https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes) of the target language.

```
# copy directory skeleton from source to i18n/<LANBG_CODE>/
rsync -av -f"+ */" -f"- *" "./source/" "./i18n/<LANG_CODE>/

# add .gitkeepers to empty dirs
find . -type d ! -path "*.git*" -empty -exec touch '{}'/.gitkeep \;

```
