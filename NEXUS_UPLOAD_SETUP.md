# Nexus Upload Setup

Do not commit real Nexus API keys to this repository.

## 1. Add GitHub Actions secrets

Open repository secrets:

```text
https://github.com/dzjadzka/bannerlord-titles-ru/settings/secrets/actions
```

Add these repository secrets:

```text
API_KEY
FILE_GROUP_ID
```

`API_KEY` is your new Nexus Mods API key.

`FILE_GROUP_ID` is available only after the Nexus page has at least one uploaded file.

## 2. Where to find file_group_id

1. Open the Nexus page:
   ```text
   https://www.nexusmods.com/mountandblade2bannerlord/mods/11224
   ```
2. Upload the first file manually:
   ```text
   TitlesRU-v1.0.2-ru1.zip
   ```
3. Go to the public-facing `Files` tab or `Manage Files`.
4. Open `API Info` for the uploaded file or file group.
5. Copy the `file_group_id` value.
6. Add it to GitHub Actions secrets as `FILE_GROUP_ID`.

## 3. Enable automatic upload

After both secrets exist, run the `Release` workflow manually with:

```text
upload_to_nexus = true
```

The workflow will rebuild the ZIP files, update the GitHub Release, and upload the standalone ZIP to Nexus Mods.
