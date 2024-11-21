# staticpub.distributed.press

Template repo for ActivityPub enabled static websites that use the Distributed Press SDK

## Instructions

To replace all instances of `staticpub.mauve.moe` with `yourdomain.com`, `mauve` with `username`, and `"Mauve"` with `"Your Name"`, you can use the following sed commands:

### For Linux Users:

```bash
find . -type f -exec sed -i 's/staticpub\.mauve\.moe/yourdomain\.com/g; s/mauve/username/g; s/"Mauve"/"Your Name"/g' {} +
```

### For macOS Users:

```bash
find . -type f -exec sed -i '' 's/staticpub\.mauve\.moe/yourdomain\.com/g; s/mauve/username/g; s/"Mauve"/"Your Name"/g' {} +
```

Make sure to update the `publicKeyPem` field in the following files with your actual public key from the `.dprc` configuration file:

- `about.jsonld`
- `about-ipns.jsonld`

### How to Find Your Public Key:

1. Open your `.dprc` file (generated during setup).
2. Copy the value of `"publicKeyPem"` (including the `BEGIN` and `END` lines).
3. Paste it into the `publicKeyPem` field in the JSON files mentioned above.

### Example:

```json
    "publicKey": {
      "@context": "https://w3id.org/security/v1",
      "@type": "Key",
      "id": "https://staticpub.mauve.moe/about.jsonld#main-key",
      "owner": "https://staticpub.mauve.moe/about.jsonld",
      "publicKeyPem": "-----BEGIN PUBLIC KEY-----\nYOUR_PUBLIC_KEY_HERE\n-----END PUBLIC KEY-----\n"
    }
```

Replace `YOUR_PUBLIC_KEY_HERE` with your actual public key from `.dprc`.

Learn more at https://docs.distributed.press/dp-cli/
