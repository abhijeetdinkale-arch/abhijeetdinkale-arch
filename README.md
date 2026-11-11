# ABHI DINKALE
`systems / local-first / ambient-compute`

```
  ____  ____   ___ _____ ___  _   _ 
 |  _ \|  _ \ / _ \_   _/ _ \| \ | |
 | |_) | |_) | | | || || | | |  \| |  [ clinical os ]
 |  __/|  _ <| |_| || || |_| | |\  |  [ status: build active ]
 |_|   |_| \_\\___/ |_| \___/|_| \_|  [ origin: local-first ]
```

> building local-first software that doesn't die when the hospital wi-fi drops.
> obsessed with ambient compute, sub-millisecond compose rendering, and sandboxed runtimes.

---

### // ACTIVE BUILDS

```
repo                   core stack               what it actually is
─────────────────────  ───────────────────────  ──────────────────────────────────────────────
proton                 kotlin / compose / fhir  doctor workstation that listens & writes notes
y3k-lockdown-browser   rust / pledge / sandbox  air-gapped exam runtime with JA3 anti-fingerprint
obsedian-research-os   python / hnsw / louvain  knowledge graph OS that clusters research notes
daily-selfie-app       kotlin / spring-physics  timelapse camera with zero-jank fluid physics
project-arc            python / agentic-copilot clinical diagnostic assistance & workflow engine
```

---

### // HOW PROTON WORKS (IN REVERSE)

Most clinical software is an enterprise web form from 2004 that doctors hate typing into.
Proton runs locally on the clinician's machine:

```
[room audio] ──> whisper acoustic ──> structured intent ──> fhir r4 bundle ──> encrypted local db
                      │                       │                    │
                 16kHz stream            vad filtered        hl7 compliant
                 on-device INT4          zero-latency        local sqlcipher
```

- **0ms network reliance**: All acoustic transcription runs on-device via LiteRT quantized models.
- **Zero-knowledge**: The patient conversation never leaves the exam room unencrypted.
- **Biometric signoff**: Cryptographic `CryptoObject` hardware token signature on encounter completion.

---

### // THE STACK (NO BUZZWORDS)

```kotlin
// what i actually touch every day:
val core = mapOf(
    "languages"   to listOf("Kotlin", "Rust", "TypeScript", "Python"),
    "mobile/ui"   to listOf("Jetpack Compose", "MVI", "Custom Layout Nodes", "Skiko"),
    "on-device"   to listOf("LiteRT / TF Lite", "Whisper Small INT4", "HNSW Indexing"),
    "security"    to listOf("Android KeyStore", "SQLCipher AES-256", "OAuth2 PKCE"),
    "storage"     to listOf("Room", "SQLite WAL", "HL7 FHIR R4 Bundles")
)
```

---

### // PRINCIPLES

1. **If it needs internet to show a button, it's broken.** Local-first by default.
2. **Speed is respect.** 60fps is a bug if the display runs at 120Hz. Zero recomposition overhead.
3. **No black-box data exhaust.** Patient data belongs in hardware-backed storage, not training corpora.

---

```
contact: github issue / pull request / x.com: @mysticgecko
gpg:     hardware-backed keystore
status:  compiling
```
