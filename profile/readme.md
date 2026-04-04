<p align="center">
  <img src="assets/logo.png" width="80" alt="GLOFICA DLT" />
</p>

<h1 align="center">GLOFICA DLT</h1>

**The Sovereign & Institutional Financial AI-Backbone**

[![Build](https://img.shields.io/badge/build-passing-brightgreen)]()
[![Tests](https://img.shields.io/badge/tests-82%2F82-brightgreen)]()
[![C++](https://img.shields.io/badge/C%2B%2B-20-blue)]()
[![License](https://img.shields.io/badge/license-proprietary-red)]()

**GLOFICA** is a **Post-Quantum DLT ecosystem** for the next generation of global and institutional finance. Built entirely in C++20 with zero external runtime dependencies — 199 source files, 35,000+ lines of production code.

---

## Architecture

```
┌─────────────────────────────────────────────────────────────────┐
│                        GLOFICA NODE                             │
├─────────────┬──────────────┬──────────────┬─────────────────────┤
│  Cortex IA  │  FlashDAG    │    Ledger    │   P2P / Network     │
│  (AI Agent  │  Consensus   │   (State +   │   (TLS 1.3 +       │
│   Kernel)   │  (Narwhal++) │   Xook Tree) │    Dilithium)       │
├─────────────┼──────────────┼──────────────┼─────────────────────┤
│ • STARK/FRI │ • DAG-based  │ • Xook JMT   │ • Post-quantum      │
│ • Neural    │ • HotStuff   │ • Parallel   │   handshake         │
│   AIR       │ • Mysticeti  │   execution  │ • Gossip protocol   │
│ • Goldilocks│ • 10K+ TPS   │ • Snapshots  │ • Certificate-based │
│   Field     │ • < 800ms    │ • MVCC       │   authentication    │
└─────────────┴──────────────┴──────────────┴─────────────────────┘
        │                │               │
        ▼                ▼               ▼
┌─────────────┬──────────────┬────────────────────────────────────┐
│  Quantum-   │  Cognitive   │        Common / Crypto             │
│  Safe PQC   │  VM (DSA)    │                                    │
├─────────────┼──────────────┼────────────────────────────────────┤
│ • Dilithium3│ • ISO 20022  │ • Blake3-512 (quantum-safe hash)   │
│ • Kyber768  │ • CBDC ops   │ • Goldilocks field arithmetic      │
│ • Blake3-512│ • Smart      │ • NTT/INTT polynomial transforms   │
│ • CRYSTALS  │   contracts  │ • Deterministic serialization      │
└─────────────┴──────────────┴────────────────────────────────────┘
```

---

## Core Pillars

### 1. 🧠 Cortex IA — Sovereign AI Engine
The world's first **on-chain AI verification kernel**. Instead of trusting AI outputs, GLOFICA mathematically **proves** they're correct using STARK zero-knowledge proofs.

| Component | Purpose | Status |
|---|---|---|
| `CortexKernel` | On-chain intent → action verifier | ✅ Integrated |
| `StarkProver` | Off-chain ZK proof generation | ✅ Complete |
| `StarkVerifier` | On-chain proof verification (O(log²N)) | ✅ Complete |
| `FRI Protocol` | Polynomial commitment via XookCommitTree | ✅ Complete |
| `NeuralAIR` | Algebraic Intermediate Representation for neural nets | ✅ Complete |
| `Goldilocks Field` | 64-bit prime field (p = 2⁶⁴ - 2³² + 1) | ✅ Complete |
| `Polynomial` | NTT/INTT, interpolation, arithmetic | ✅ Complete |
| `ReasoningEngine` | Chain-of-thought parsing (DeepSeek R1) | ✅ Complete |

**Security**: Forgery probability < 2⁻¹²⁸. An attacker cannot produce a valid proof without running the exact model on the exact input.

### 2. ⚡ FlashDAG Consensus (Narwhal++ / Mysticeti)
DAG-based consensus achieving **10,000+ TPS** with sub-800ms finality.

- **Narwhal++ Mempool**: Worker batches, certificate voting, Byzantine slashing
- **HotStuff/Mysticeti**: Pipelined BFT with chained QCs
- **Deterministic Execution**: Parallel transaction processing with conflict graphs

### 3. 🛡️ Post-Quantum Cryptography
Every cryptographic primitive is quantum-resistant:

- **Signatures**: CRYSTALS-Dilithium3 (NIST PQC standard)
- **Key Exchange**: Kyber768 (NIST KEM standard)  
- **Hashing**: Blake3-512 (64-byte, 512-bit quantum-safe)
- **Merkle Trees**: Xook JMT with POPCNT-accelerated SparseBitmap

### 4. 🌐 Institutional Compliance
- **ISO 20022** native VM processing
- **GENIUS Act** compliance framework
- **CBDC** operations: mint, burn, freeze, unfreeze, recover
- **DSA** (Digital Settlement Assets): 1:1 settlement finality

---

## Project Structure

```
glofica/
├── src/
│   ├── cortex/          # AI Engine — STARK proofs, neural layers, reasoning
│   │   ├── fri.hpp/cpp              # FRI protocol + XookCommitTree
│   │   ├── stark_prover.hpp/cpp     # Off-chain STARK proof generation
│   │   ├── stark_verifier.hpp/cpp   # On-chain STARK verification
│   │   ├── stark_proof.hpp          # Proof structures + NeuralAIR
│   │   ├── cortex_kernel.hpp/cpp    # Intent → Action verification kernel
│   │   ├── goldilocks.hpp/cpp       # Goldilocks prime field
│   │   ├── polynomial.hpp/cpp       # NTT, interpolation, arithmetic
│   │   ├── neural_layer.hpp/cpp     # Quantized neural network layers
│   │   └── reasoning_engine.hpp/cpp # Chain-of-thought parser
│   ├── consensus/       # FlashDAG, HotStuff, Mysticeti
│   │   └── flash_dag/narwhal/       # Narwhal++ mempool + voting
│   ├── ledger/          # Blockchain, state, mempool, transactions
│   ├── xook/            # Xook Jellyfish Merkle Tree (state commitment)
│   ├── vm/              # Cognitive VM (DSA + ISO 20022 opcodes)
│   ├── common/          # Blake3 hash, bytes, serialization
│   ├── p2p/             # TLS 1.3 networking + gossip
│   ├── identity/        # Fractal ID + PQC identity
│   └── main.cpp         # Node entry point
├── tests/
│   ├── test_cortex.cpp  # 82 tests — Cortex + STARK + FRI
│   └── consensus/       # Narwhal adapter + stress tests
├── docs/
│   └── GLOFICA_White_Paper.md
└── CMakeLists.txt
```

**Codebase**: 199 source files · 35,000+ lines of C++20

---

## Build from Source

### Prerequisites
- **CMake** ≥ 3.20
- **MSVC** ≥ 17.0 (Visual Studio 2022) or **GCC** ≥ 12 / **Clang** ≥ 15
- **C++20** support required

### Build
```powershell
# Configure
cmake -B build -DCMAKE_BUILD_TYPE=Release

# Build all targets
cmake --build build --config Release

# Run tests
./build/Release/test_cortex.exe
```

### Launch Cluster (SimNet)
```powershell
.\launch_stable.ps1
```

---

## Test Status

```
============================================
  CORTEX IA — Agentic VM Test Suite
  GLOFICA Sovereign AI Engine
============================================

  Results: 82 passed, 0 failed

============================================
```

### Test Coverage
| Module | Tests | Status |
|---|---|---|
| Goldilocks Field | 15 | ✅ |
| Polynomial/NTT | 8 | ✅ |
| XookCommitTree | 3 | ✅ |
| NeuralAIR Constraints | 5 | ✅ |
| FRI Protocol | 2 | ✅ |
| STARK Prover/Verifier | 4 | ✅ |
| CortexKernel (Legacy) | 12 | ✅ |
| CortexKernel + STARK | 3 | ✅ |
| Reasoning Engine | 10 | ✅ |
| Narwhal Consensus | 20+ | ✅ |

---

## Institutional Benchmarking

| Core Capability | GLOFICA | BIS (mBridge) | Canton / Onyx | Hyperledger / Corda |
| :--- | :--- | :--- | :--- | :--- |
| ⚡ **Settlement Finality** | ✅ **Immediate (< 800ms)** | ⏳ Variable (Multi-hop) | ❌ 3 - 5 Seconds | ❌ System Dependent |
| 🧠 **Sovereign AI Cortex** | ✅ **NATIVE** | ❌ NONE | ❌ NONE | ❌ NONE |
| 🛡️ **Quantum Security** | ✅ **NATIVE** | ⏳ Planned | ❌ NONE | ❌ NONE |
| 🏦 **ISO 20022 Native VM** | ✅ **NATIVE** | ✅ Native Support | 🧩 Partial | 🧩 Plugin-based |
| ⚖️ **GENIUS Act Compliance** | ✅ **NATIVE** | ❌ NONE | ❌ NONE | ❌ NONE |
| 🏛️ **Sovereignty Model** | ✅ **Full (Independent)** | 🏢 Centralized / Shared | 🤝 Consortium-led | 🔗 Private Subnets |
| ⚙️ **Hardware Acceleration** | ✅ **POPCNT / Bare Metal** | ☁️ Traditional Cloud | 🗄️ Standard VM | 🗄️ Standard VM |
| 🔐 **STARK ZK-Proofs** | ✅ **NATIVE** | ❌ NONE | ❌ NONE | ❌ NONE |

---

## Roadmap 2026-2027

- **Phase 01: The Foundation** ✅ (XOOK, PQC, 10K TPS, Cluster Stability)
- **Phase 02: Chimera Scale** ✅ (FlashDAG, Narwhal++, Mysticeti, Deterministic Executor)
- **Phase 03: Cortex Intelligence** ✅ (STARK/FRI Proofs, NeuralAIR, CortexKernel Integration)
- **Phase 04: Global Interconnect** 🔄 (ISO 20022 Native, Universal Liquidity Bridge, TEE Integration)

---

**Built for Sovereignty. Optimized for Intelligence. Proven at Scale.**

*Copyright © 2026 GLOFICA — G | MALAVE Inc. All rights reserved.*

