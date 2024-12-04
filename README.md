# staticpub.distributed.press

Template repo for ActivityPub enabled static websites that use the Distributed Press SDK

## Instructions

To replace all instances of `staticpub.distributed.press` with `yourdomain.com`, `dp` with `username`, and `"Distributed Press"` with `"Your Name"`, you can use the following sed commands:

### For Linux Users:

```bash
find . -type f -exec sed -i 's/staticpub\.distributed\.press/yourdomain\.com/g; s/dp/username/g; s/"Distributed Press"/"Your Name"/g' {} +
```

### For macOS Users:

```bash
find . -type f -exec sed -i '' 's/staticpub\.distributed\.press/yourdomain\.com/g; s/dp/username/g; s/"Distributed Press"/"Your Name"/g' {} +
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
      "id": "https://staticpub.distributed.press/about.jsonld#main-key",
      "owner": "https://staticpub.distributed.press/about.jsonld",
      "publicKeyPem": "-----BEGIN PUBLIC KEY-----\nYOUR_PUBLIC_KEY_HERE\n-----END PUBLIC KEY-----\n"
    }
```

Replace `YOUR_PUBLIC_KEY_HERE` with your actual public key from `.dprc`.

### Learn More
For detailed instructions on setting up the Distributed Press CLI, visit the [Distributed Press CLI documentation](https://docs.distributed.press/dp-cli/).
