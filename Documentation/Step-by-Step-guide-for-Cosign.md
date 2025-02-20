# Cosign: Securely Sign and Verify Container Images

Cosign is a tool from **Sigstore** used for signing and verifying container images, ensuring integrity and authenticity.

## 1️⃣ Install Cosign
### For Linux/macOS
```bash
curl -LO https://github.com/sigstore/cosign/releases/latest/download/cosign-linux-amd64
chmod +x cosign-linux-amd64
sudo mv cosign-linux-amd64 /usr/local/bin/cosign
```
Verify installation:
```bash
cosign version
```

## 2️⃣ Generate a Key Pair (Optional)
Cosign can sign images with a **key pair** (public & private keys) or **keyless** signing. To generate keys:
```bash
cosign generate-key-pair
```
This creates:
- **cosign.key** (private key)
- **cosign.pub** (public key)

## 3️⃣ Sign a Docker Image
```bash
cosign sign --key cosign.key cloud-project:v6.2
```
For **keyless signing** (if you have GitHub OIDC or Fulcio enabled):
```bash
cosign sign cloud-project:v6.2
```
You'll be prompted to authenticate.

## 4️⃣ Verify a Signed Image
To ensure the image is signed and trusted:
```bash
cosign verify --key cosign.pub cloud-project:v6.2
```
For keyless verification:
```bash
cosign verify cloud-project:v6.2
```

## 5️⃣ Attach SBOM (Software Bill of Materials)
To generate and attach an SBOM to your image:
```bash
cosign attest --key cosign.key --predicate sbom.json cloud-project:v6.2
```

## 6️⃣ Integrate Cosign in CI/CD Pipeline
To automate image signing in **Jenkins, GitHub Actions, or GitLab CI**, you can add:
```yaml
steps:
  - name: Sign Image
    run: cosign sign cloud-project:v6.2
  - name: Verify Image
    run: cosign verify cloud-project:v6.2
```

### 🚀 Start Securing Your Container Images with Cosign Today! 🚀

