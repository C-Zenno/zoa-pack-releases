# Verification Instructions

## Bundle: phase1-pack-factory-v1.1-dist1

### 1. Verify Checksums

```bash
sha256sum -c SHA256SUMS.txt
```

Or on Windows (PowerShell):

```powershell
Get-Content SHA256SUMS.txt | ForEach-Object {
    $parts = $_ -split '  '
    $expected = $parts[0]
    $file = $parts[1]
    $actual = (Get-FileHash $file -Algorithm SHA256).Hash
    if ($actual -eq $expected) { "OK: $file" } else { "FAIL: $file" }
}
```

### 2. Extract and Run Demo

```bash
unzip bundle.zip -d bundle/
cd bundle/
python tools/demo/demo_phase1.py
```

Or on Windows:

```powershell
Expand-Archive bundle.zip -DestinationPath bundle
cd bundle
python tools/demo/demo_phase1.py
```

### 3. Review License

See `LICENSE.txt` (OEL-1.0 — Observer Evaluation License)

---

*Observational artifact only. Non-authoritative. No action implied.*
