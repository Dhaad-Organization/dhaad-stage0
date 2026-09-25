# Dhaad Programming Language (لغة البرمجة ض/ضاد)

> **Current Version: v0.1.0 — Proof of Concept**
>
> A unified programming language aiming to consolidate AI, Quantum Computing, 
> Cybersecurity, and regulated industries into a single formally-verified platform.

[![Build Status](https://img.shields.io/badge/build-passing-brightgreen)](https://github.com/dhaad-org/dhaad-stage0/actions)
[![Tests](https://img.shields.io/badge/tests-6%2C351%20passing-brightgreen)](https://github.com/dhaad-org/dhaad-stage0)
[![Assertions](https://img.shields.io/badge/assertions-1%2C068%2C809-blue)](https://github.com/dhaad-org/dhaad-stage0)
[![Patent](https://img.shields.io/badge/patent-SA--1020266164-orange)](docs/PATENT.md)
[![License](https://img.shields.io/badge/license-DMEOL--2.0--Universal-purple)](LICENSE)

---

## 📋 Table of Contents

- [What is Dhaad?](#what-is-dhaad)
- [Current Status](#current-status)
- [Intellectual Property](#intellectual-property)
- [Quick Start](#quick-start)
- [Examples](#examples)
- [Architecture](#architecture)
- [Verified Numbers](#verified-numbers)
- [Roadmap](#roadmap)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

---

## What is Dhaad?

**Dhaad** is an attempt to build a **unified programming platform** that solves 
the technical fragmentation problem faced by enterprises and nations:

- **15+ languages and platforms** per domain (Python for AI, Q# for Quantum, 
  Solidity for Blockchain, ...)
- **Conflicting security models** across languages
- **Absence of formal verification** in most production languages
- **Regulatory compliance difficulty** in regulated sectors (healthcare, 
  finance, defense)

**Dhaad's vision**: one language, one security model, one verification system, 
across 116 systems distributed over 26 layers.

> ⚠️ **Honest disclaimer**: This is **Stage 0 (Proof of Concept)**. The language 
> is still in its infancy. We are seeking **early adopters** and 
> **co-founders** to transform this specification into a production-grade product.

---

## Current Status

### What Has Been Actually Built (BUILD-VERIFIED)

| Component                        | Status    | Evidence                                |
| -------------------------------- | --------- | --------------------------------------- |
| **Core Compiler**                | ✅ Working | `dhaad.exe` builds & passes 6,351 tests |
| **Lexer**                        | ✅ Working | 592 tokens, 447 keywords, 110 operators |
| **Parser**                       | ✅ Working | 740 AST nodes in 17 categories          |
| **Semantic Analysis**            | ✅ Working | 8-pass pipeline                         |
| **Unified Semantic Tree (UST)**  | ✅ Working | 40 UDNS v8.0 capabilities               |
| **Code Generation (LLVM 21)**    | ✅ Working | 139 LLVM libraries integrated           |
| **Package Manager (dpm)**        | ✅ Working | PubGrub SAT resolver                    |
| **Language Server (LSP 3.17)**   | ✅ Working | 26 custom + 35 standard methods         |
| **Code Formatter (dhaad-fmt)**   | ✅ Working | 8-pass pipeline                         |
| **Doc Generator (dhaad-doc)**    | ✅ Working | 8 document types                        |
| **Interactive REPL**             | ✅ Working | 15 commands                             |
| **Formal Verification**          | ⚠️ Partial | 8 Lean 4 modules (of 10 planned)        |
| **Standard Library (dhaad-std)** | ⚠️ Partial | 18 modules (of 50+ planned)             |
| **Fuzzing**                      | ⚠️ Partial | 3 targets (requires Clang)              |

### What Is NOT Yet Done (Honestly)

- ❌ **No external users** yet
- ❌ **No engineering team** (single founder currently)
- ❌ **No industrial or academic partners** formally
- ❌ **No regulatory certifications** (ISO, DO-178C, ...) — planned for future years
- ❌ **64 of 116 systems** deferred to Stage 2

---

## Intellectual Property

This project is **officially registered** with the Saudi Authority for 
Intellectual Property (SAIP):

| Type          | Number          | Status     | Date                       |
| ------------- | --------------- | ---------- | -------------------------- |
| **Patent**    | SA-1020266164   | ✅ Filed    | 1448/01/10 AH (2026-07-10) |
| **Copyright** | SA-261295185201 | ✅ Complete | 2020-07-26                 |
| **Trademark** | SA-1267997      | ⏳ Pending  | -                          |

📎 Full documentation in [`docs/ip/`](docs/ip/).

**Owner**: Hassan Ali Mohammed Ahmed Shoukr  
**Organization**: Dhaad Organization

---

## Quick Start

### Prerequisites

| Component  | Version | Notes                        |
| ---------- | ------- | ---------------------------- |
| **CMake**  | 4.0+    |                              |
| **MSVC**   | 19.44+  | Windows (Visual Studio 2022) |
| **Clang**  | 18+     | Linux/macOS + Fuzzing        |
| **GCC**    | 14+     | Linux                        |
| **Python** | 3.10+   | For code generators          |
| **LLVM**   | 21.1.1  | Download from llvm.org       |
| **vcpkg**  | latest  | For external dependencies    |

### Windows Build (MSVC)

```powershell
# 1. Clone repository
git clone https://github.com/dhaad-org/dhaad-stage0.git
cd dhaad-stage0

# 2. Setup vcpkg (if not installed)
git clone https://github.com/microsoft/vcpkg.git C:/vcpkg
C:/vcpkg/bootstrap-vcpkg.bat
C:/vcpkg/vcpkg install nlohmann-json fmt doctest

# 3. Generate build files
cmake -B build/release -G "Visual Studio 17 2022" -A x64

# 4. Build
cmake --build build/release --config Release

# 5. Run tests
.\build\release\Release\dhaad_test_runner.exe
```

### Linux/macOS Build

```bash
# 1. Clone
git clone https://github.com/dhaad-org/dhaad-stage0.git
cd dhaad-stage0

# 2. Dependencies (Ubuntu)
sudo apt install cmake ninja-build clang-18 libllvm21-dev \
                 nlohmann-json3-dev libfmt-dev doctest-dev

# 3. Build
cmake -B build/release -G Ninja \
      -DCMAKE_BUILD_TYPE=Release \
      -DCMAKE_CXX_COMPILER=clang++-18
cmake --build build/release

# 4. Test
./build/release/dhaad_test_runner
```

### Expected Output

```
[doctest] test cases:    6351 |    6351 passed | 0 failed
[doctest] assertions: 1068809 | 1068809 passed | 0 failed
[doctest] Status: SUCCESS!
```

---

## Examples

### Example 1: Hello World

```dhaad
#~> FILE: hello.dh
#~> LICENSE: DMEOL-2.0-Universal

dDh HelloWorld =
  fDh main(): Int32 =
    println("Hello, Dhaad!")
    return 0
  =>
    .return
```

**Run**:
```bash
dhaad hello.dh -o hello.o
dhaad hello.dh --format ll      # Show LLVM IR
```

### Example 2: Math Function

```dhaad
dDh Fibonacci =
  fDh fib(n: Int32): Int32 =
    constraints: { require: n >= 0 }
    =
      if n <= 1 then n
      else fib(n - 1) + fib(n - 2)
    =>
      .return
      .check
```

### Example 3: Certified Mode

```dhaad
dDh CriticalSystem =
  [mode: { rigor: certified, verification: formal }]
  fDh compute(x: Int32): Int32 =
    constraints: {
      require: x > 0,
      ensure: result > x
    }
    =
      x * 2
    =>
      .return
      .prove
```

📚 **More examples** in [`examples/`](examples/).

---

## Architecture

### Seven Tiers (Phase 0)

```
┌─────────────────────────────────────────────────────────────┐
│  Tier 7: Tests & Verification                              │
├─────────────────────────────────────────────────────────────┤
│  Tier 6: UDOHS, AST & Visualization                        │
├─────────────────────────────────────────────────────────────┤
│  Tier 5: Generated Files (BUILD-TIME)                      │
│          NodeKinds.inc · TokenKinds.gen.h · UnicodeTables  │
├─────────────────────────────────────────────────────────────┤
│  Tier 4: Third-Level Dependencies                          │
│          SourceManager · BlockSystem · ThreadPool          │
├─────────────────────────────────────────────────────────────┤
│  Tier 3: Second-Level Dependencies                         │
│          StringPool · SymbolTable · FileSystem · Grid      │
├─────────────────────────────────────────────────────────────┤
│  Tier 2: Error Recovery & Diagnostics Base                 │
│          Diagnostic · ErrorRecovery · DiagnosticsBase      │
├─────────────────────────────────────────────────────────────┤
│  Tier 1: First-Level Dependencies                          │
│          Arena · StringPool · SmallVector · ArrayRef       │
├─────────────────────────────────────────────────────────────┤
│  Tier 0: Absolute Foundation                               │
│          Math · Symbol · SourceLocation · Result · Option  │
└─────────────────────────────────────────────────────────────┘
```

### Full Pipeline (Phases 0-7)

```
Source.dh
  │
  ▼
┌──────────┐   ┌──────────┐   ┌──────────┐   ┌──────────┐
│  Lexer   │──▶│  Parser  │──▶│ Semantic │──▶│   UST    │
│ (Phase 1)│   │ (Phase 2)│   │ (Phase 3)│   │ (Phase 4)│
└──────────┘   └──────────┘   └──────────┘   └──────────┘
                                                    │
                                                    ▼
                              ┌──────────┐   ┌──────────┐
                              │  LLVM 21 │◀──│ CodeGen  │
                              │ Backend  │   │ (Phase 5)│
                              └──────────┘   └──────────┘
                                                    │
                                                    ▼
                                              Binary (.o/.exe)
```

---

## Verified Numbers

**These numbers are extracted from the actual build log** 
(MSVC 19.44, Windows 10):

| Metric                | Count         | Notes           |
| --------------------- | ------------- | --------------- |
| **Test Cases**        | **6,351**     | ✅ All passing   |
| **Assertions**        | **1,068,809** | ✅ All passing   |
| **Tokens**            | **592**       | ✅ Verified      |
| **Keywords**          | **447**       | ✅ Verified      |
| **Operators**         | **110**       | ✅ Verified      |
| **Node Kinds**        | **740**       | ✅ 17 categories |
| **Handlers**          | **221**       | ✅ 20 categories |
| **Constraints**       | **137**       | ✅ 30 categories |
| **Modes**             | **148**       | ✅ 21 sections   |
| **Error Codes**       | **1,277**     | ✅ 28 categories |
| **Libraries Built**   | **27**        | ✅ ZERO warnings |
| **Executables**       | **7**         | ✅ Working       |
| **LLVM Libraries**    | **139**       | ✅ LLVM 21.1.1   |
| **Compiler Warnings** | **0**         | ✅ Under /W4 /WX |

> 📊 **Transparency Note**: Numbers mentioned in some older documents 
> (e.g., "3,616,209 assertions") were **exaggerated**. The numbers above 
> are the **actual numbers from the latest build log**.

---

## Roadmap

### Stage 0 — Proof of Concept (2026) ✅

- [x] Core compiler (Phases 0-5)
- [x] Package manager (Phase 6)
- [x] Language server (Phase 7)
- [x] Basic formal verification (Phase 8)
- [x] IP registered

### Stage 1 — Self-Hosting (2027) 🎯

- [ ] Compiler compiles itself (Self-Hosting)
- [ ] 10+ external developers
- [ ] 100+ GitHub stars
- [ ] Complete standard library (50+ modules)
- [ ] First regulatory certification (HIPAA or PCI-DSS)

### Stage 2 — Expansion (2028-2029)

- [ ] Complete all 116 systems
- [ ] 1,000+ developers
- [ ] 10 paying companies
- [ ] ISO 26262, DO-178C certifications
- [ ] Full quantum integration

### Stage 3 — Maturity (2030+)

- [ ] 10,000+ developers
- [ ] $10M+ ARR
- [ ] Full regulatory certifications
- [ ] Government adoption

📎 **Full details** in [`docs/roadmap/`](docs/roadmap/).

---

## Contributing

We welcome contributions! But this is an **early stage**, and we are 
specifically looking for:

### 🎯 What We Need

1. **Co-founders**:
   - CTO with compiler engineering experience
   - Chief Scientist in type theory or formal verification
   - Head of Community

2. **Technical Contributors**:
   - C++20 developers with compiler experience
   - Lean 4 / Coq experts
   - TypeScript developers (VS Code extension)

3. **Early Adopters**:
   - University researchers
   - Startup engineering teams
   - Independent developers

### 📝 How to Contribute

```bash
# 1. Fork the repository
git clone https://github.com/YOUR_USERNAME/dhaad-stage0.git

# 2. Create a branch
git checkout -b feature/my-contribution

# 3. Build and test
cmake -B build -G "Visual Studio 17 2022"
cmake --build build --config Release
./build/Release/dhaad_test_runner.exe

# 4. Commit
git commit -m "Add: my contribution"

# 5. Push and open a Pull Request
git push origin feature/my-contribution
```

📎 **Full guide** in [`CONTRIBUTING.md`](CONTRIBUTING.md).

---

## License

This project is licensed under **DMEOL-2.0-Universal (Perpetual Ethical Edition)**.

| Category                   | Price        | Terms       |
| -------------------------- | ------------ | ----------- |
| **Individual & Education** | Free         | Attribution |
| **Open Source**            | Free         | Attribution |
| **Startup** (< $10M)       | $500/year    | Attribution |
| **Professional** (< $100M) | $5,000/year  | Attribution |
| **Enterprise** (>= $100M)  | $50,000/year | Negotiated  |
| **Government**             | Negotiated   | Negotiated  |

📎 **Full text** in [`LICENSE`](LICENSE) and [`docs/licensing/`](docs/licensing/).

---

## Contact

- **GitHub Issues**: [github.com/dhaad-Organization/dhaad-stage0/issues](https://github.com/dhaad-org/dhaad-stage0/issues)
- **GitHub Discussions**: [github.com/dhaad-Organization/dhaad-stage0/discussions](https://github.com/dhaad-org/dhaad-stage0/discussions)
- **Email**: contact@dhaad.org
- **Website**: [dhaad.org](https://dhaad.org) (under construction)

---

## Acknowledgments

- **MSVC 19.44** — Windows build
- **LLVM 21.1.1** — Backend
- **vcpkg** — Dependency management
- **doctest** — Testing framework
- **Lean 4** — Formal verification

---

## Project Status

**Status**: 🟡 **Proof of Concept**

- ✅ Compiler works
- ✅ Tests pass
- ✅ IP registered
- ⚠️ No external users yet
- ⚠️ No team yet
- ⚠️ 64 systems deferred

**We invite co-founders and early adopters to join.**

---

<div align="center">

**© 2024-2026 Dhaad Organization. All Rights Reserved.**

Made with 🖤 in the Kingdom of Saudi Arabia

[Patent SA-1020266164](docs/PATENT.md) · [Copyright SA-261295185201](docs/COPYRIGHT.md) · [Trademark SA-1267997](docs/TRADEMARK.md)

</div>
```
