# obsidian-network-mount-launcher

Mounts a network share (if needed) and opens an Obsidian vault.

Uses `osascript mount volume` for silent mounting—no credential dialog when credentials are saved in Keychain.

## Requirements

- `jq` - for URL encoding the vault path

## Usage

```bash
obsidian-network-mount-launcher <smb-path>
```

Example:
```bash
obsidian-network-mount-launcher "smb://server.local/files/notes/my-vault"
```

Or via env var:
```bash
SMB_PATH="smb://server.local/files/notes/my-vault" obsidian-network-mount-launcher
```

The script parses the SMB path to extract:
- `NETWORK_URL`: `smb://server.local/files` (for mounting)
- `MOUNT_POINT`: `/Volumes/files`
- `VAULT_PATH`: `/Volumes/files/notes/my-vault`

## Install

Using [bin](https://github.com/marcosnils/bin):

```bash
bin install djbender/obsidian-network-mount-launcher
```
