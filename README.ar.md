# لغة البرمجة ض (Dhaad Programming Language)

> **النسخة الحالية: v0.1.0 — مرحلة الإثبات (Proof of Concept)**
> 
> لغة برمجة موحدة تهدف إلى دمج الذكاء الاصطناعي، الحوسبة الكمومية، الأمن السيبراني، 
> والقطاعات المنظمة في منصة واحدة متحققة شكلياً.

[![Build Status](https://img.shields.io/badge/build-passing-brightgreen)](https://github.com/dhaad-org/dhaad-stage0/actions)
[![Tests](https://img.shields.io/badge/tests-6%2C351%20passing-brightgreen)](https://github.com/dhaad-org/dhaad-stage0)
[![Assertions](https://img.shields.io/badge/assertions-1%2C068%2C809-blue)](https://github.com/dhaad-org/dhaad-stage0)
[![Patent](https://img.shields.io/badge/patent-SA--1020266164-orange)](docs/PATENT.md)
[![License](https://img.shields.io/badge/license-DMEOL--2.0--Universal-purple)](LICENSE)

---

## 📋 جدول المحتويات

- [ما هي لغة ض؟](#ما-هي-لغة-ض)
- [الحالة الحالية](#الحالة-الحالية)
- [الملكية الفكرية](#الملكية-الفكرية)
- [البناء السريع](#البناء-السريع)
- [أمثلة عملية](#أمثلة-عملية)
- [البنية المعمارية](#البنية-المعمارية)
- [الأرقام الفعلية](#الأرقام-الفعلية)
- [خارطة الطريق](#خارطة-الطريق)
- [المساهمة](#المساهمة)
- [الترخيص](#الترخيص)
- [التواصل](#التواصل)

---

## ما هي لغة ض؟

**لغة ض (Dhaad)** هي محاولة لبناء **منصة برمجية موحدة** تحل مشكلة التشتت التقني 
التي تواجهها الشركات والدول:

- **15+ لغة ومنصة** لكل مجال (Python للذكاء الاصطناعي، Q# للكم، Solidity للبلوكشين، ...)
- **نماذج أمان متضاربة** بين اللغات
- **غياب التحقق الشكلي** في معظم اللغات الإنتاجية
- **صعوبة الامتثال التنظيمي** في القطاعات المنظمة (صحة، مال، دفاع)

**رؤية ض**: لغة واحدة، نموذج أمان واحد، نظام تحقق واحد، عبر 116 نظاماً 
موزعة على 26 طبقة.

> ⚠️ **ملاحظة صريحة**: هذه **مرحلة الإثبات (Stage 0)**. اللغة لا تزال في 
> بداياتها. نبحث عن **متبنين أوائل** و**مؤسسين مشاركين** لتحويل هذه 
> المواصفة إلى منتج إنتاجي.

---

## الحالة الحالية

### ما تم إنجازه فعلياً (BUILD-VERIFIED)

| المكوّن                            | الحالة | الدليل                                 |
| --------------------------------- | ------ | -------------------------------------- |
| **المترجم الأساسي**               | ✅ يعمل | `dhaad.exe` يُبنى وينجح في 6,351 اختبار |
| **المُحلّل اللغوي (Lexer)**         | ✅ يعمل | 592 رمزاً، 447 كلمة مفتاحية، 110 عوامل  |
| **المُحلّل النحوي (Parser)**        | ✅ يعمل | 740 عقدة AST في 17 فئة                 |
| **التحليل الدلالي**               | ✅ يعمل | خط أنابيب من 8 مراحل                   |
| **الشجرة الدلالية الموحدة (UST)** | ✅ يعمل | 40 قدرة UDNS v8.0                      |
| **توليد الكود (LLVM 21)**         | ✅ يعمل | 139 مكتبة LLVM مدمجة                   |
| **مدير الحزم (dpm)**              | ✅ يعمل | مُحلّل PubGrub لتضارب الإصدارات          |
| **خادم اللغة (LSP 3.17)**         | ✅ يعمل | 26 طريقة مخصصة + 35 طريقة قياسية       |
| **المُنسّق (dhaad-fmt)**            | ✅ يعمل | خط أنابيب 8 مراحل                      |
| **مولّد الوثائق (dhaad-doc)**      | ✅ يعمل | 8 أنواع وثائق                          |
| **REPL التفاعلي**                 | ✅ يعمل | 15 أمراً                                |
| **التحقق الشكلي**                 | ⚠️ جزئي | 8 وحدات Lean 4 (من أصل 10 مخطط لها)    |
| **مكتبة قياسية (dhaad-std)**      | ⚠️ جزئي | 18 وحدة (من أصل 50+ مخطط لها)          |
| **الاختبار العشوائي (Fuzzing)**   | ⚠️ جزئي | 3 أهداف (يتطلب Clang للتفعيل)          |

### ما لم ينجز بعد (بصراحة)

- ❌ **لا مستخدمين خارجيين** حتى الآن
- ❌ **لا فريق هندسي** (مؤسس واحد حالياً)
- ❌ **لا شركاء صناعيون** أو أكاديميون رسميون
- ❌ **لا شهادات تنظيمية** (ISO, DO-178C, ...) — مخطط لها للسنوات القادمة
- ❌ **64 نظاماً** من أصل 116 مؤجّل إلى Stage 2

---

## الملكية الفكرية

هذا المشروع **مسجل رسمياً** في الهيئة السعودية للملكية الفكرية (SAIP):

| النوع            | الرقم           | الحالة        | التاريخ                   |
| ---------------- | --------------- | ------------- | ------------------------- |
| **براءة اختراع** | SA-1020266164   | ✅ مُودعة       | 1448/01/10هـ (2026-07-10) |
| **حقوق المؤلف**  | SA-261295185201 | ✅ مُكتملة      | 2020-07-26                |
| **علامة تجارية** | SA-1267997      | ⏳ قيد التسجيل | -                         |

📎 الوثائق الكاملة في [`docs/ip/`](docs/ip/).

**المالك**: Hassan Ali Mohammed Ahmed Shoukr  
**المؤسسة**: Dhaad Organization

---

## البناء السريع

### المتطلبات

| المكوّن     | الإصدار | ملاحظات                      |
| ---------- | ------- | ---------------------------- |
| **CMake**  | 4.0+    |                              |
| **MSVC**   | 19.44+  | Windows (Visual Studio 2022) |
| **Clang**  | 18+     | Linux/macOS + Fuzzing        |
| **GCC**    | 14+     | Linux                        |
| **Python** | 3.10+   | لمولّدات الكود                |
| **LLVM**   | 21.1.1  | يُنصح بتحميله من llvm.org     |
| **vcpkg**  | latest  | للاعتماديات الخارجية         |

### بناء Windows (MSVC)

```powershell
# 1. استنساخ المستودع
git clone https://github.com/dhaad-org/dhaad-stage0.git
cd dhaad-stage0

# 2. إعداد vcpkg (إن لم يكن مثبتاً)
git clone https://github.com/microsoft/vcpkg.git C:/vcpkg
C:/vcpkg/bootstrap-vcpkg.bat
C:/vcpkg/vcpkg install nlohmann-json fmt doctest

# 3. توليد ملفات البناء
cmake -B build/release -G "Visual Studio 17 2022" -A x64

# 4. البناء
cmake --build build/release --config Release

# 5. تشغيل الاختبارات
.\build\release\Release\dhaad_test_runner.exe
```

### بناء Linux/macOS

```bash
# 1. استنساخ
git clone https://github.com/dhaad-org/dhaad-stage0.git
cd dhaad-stage0

# 2. الاعتماديات (Ubuntu)
sudo apt install cmake ninja-build clang-18 libllvm21-dev \
                 nlohmann-json3-dev libfmt-dev doctest-dev

# 3. البناء
cmake -B build/release -G Ninja \
      -DCMAKE_BUILD_TYPE=Release \
      -DCMAKE_CXX_COMPILER=clang++-18
cmake --build build/release

# 4. الاختبارات
./build/release/dhaad_test_runner
```

### الناتج المتوقع

```
[doctest] test cases:    6351 |    6351 passed | 0 failed
[doctest] assertions: 1068809 | 1068809 passed | 0 failed
[doctest] Status: SUCCESS!
```

---

## أمثلة عملية

### مثال 1: Hello World

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

**التشغيل**:
```bash
dhaad hello.dh -o hello.o
dhaad hello.dh --format ll      # عرض LLVM IR
```

### مثال 2: دالة رياضية

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

### مثال 3: وضع Certified

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

📚 **أمثلة أكثر** في [`examples/`](examples/).

---

## البنية المعمارية

### الطبقات السبع (Phase 0)

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

### خط الأنابيب الكامل (Phases 0-7)

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

## الأرقام الفعلية

**هذه الأرقام مُستخرجة من سجل البناء الفعلي** (MSVC 19.44, Windows 10):

| المقياس                      | العدد         | ملاحظات         |
| ---------------------------- | ------------- | --------------- |
| **حالات الاختبار**           | **6,351**     | ✅ جميعها تنجح   |
| **التأكيدات (Assertions)**   | **1,068,809** | ✅ جميعها تنجح   |
| **الرموز (Tokens)**          | **592**       | ✅ مُتحقق منها    |
| **الكلمات المفتاحية**        | **447**       | ✅ مُتحقق منها    |
| **العوامل (Operators)**      | **110**       | ✅ مُتحقق منها    |
| **أنواع العقد (Node Kinds)** | **740**       | ✅ 17 فئة        |
| **المعالجات (Handlers)**     | **221**       | ✅ 20 فئة        |
| **القوائم (Constraints)**    | **137**       | ✅ 30 فئة        |
| **الأوضاع (Modes)**          | **148**       | ✅ 21 قسماً       |
| **رموز الأخطاء**             | **1,277**     | ✅ 28 فئة        |
| **مكتبات مبنية**             | **27**        | ✅ ZERO warnings |
| **ملفات تنفيذية**            | **7**         | ✅ تعمل          |
| **مكتبات LLVM**              | **139**       | ✅ LLVM 21.1.1   |
| **تحذيرات المترجم**          | **0**         | ✅ تحت /W4 /WX   |

> 📊 **ملاحظة شفافية**: الأرقام المذكورة في بعض الوثائق القديمة 
> (مثل "3,616,209 تأكيد") كانت **مبالغاً فيها**. الأرقام أعلاه هي 
> **الأرقام الفعلية من سجل البناء الأخير**.

---

## خارطة الطريق

### Stage 0 — الإثبات (2026) ✅

- [x] المترجم الأساسي (Phases 0-5)
- [x] مدير الحزم (Phase 6)
- [x] خادم اللغة (Phase 7)
- [x] التحقق الشكلي الأساسي (Phase 8)
- [x] الملكية الفكرية مسجلة

### Stage 1 — الاستضافة الذاتية (2027) 🎯

- [ ] المترجم يترجم نفسه (Self-Hosting)
- [ ] 10+ مطورين خارجيين
- [ ] 100+ نجمة GitHub
- [ ] مكتبة قياسية كاملة (50+ وحدة)
- [ ] أول شهادة تنظيمية (HIPAA أو PCI-DSS)

### Stage 2 — التوسع (2028-2029)

- [ ] إكمال 116 نظاماً
- [ ] 1,000+ مطور
- [ ] 10 شركات تدفع
- [ ] شهادات ISO 26262, DO-178C
- [ ] تكامل كمومي كامل

### Stage 3 — النضج (2030+)

- [ ] 10,000+ مطور
- [ ] $10M+ ARR
- [ ] شهادات تنظيمية كاملة
- [ ] تبني حكومي

📎 **التفاصيل الكاملة** في [`docs/roadmap/`](docs/roadmap/).

---

## المساهمة

نرحّب بالمساهمات! لكن هذه **مرحلة مبكرة**، ونبحث تحديداً عن:

### 🎯 ما نبحث عنه

1. **مؤسسون مشاركون** (Co-founders):
   - CTO بخبرة في بناء المترجمات
   - Chief Scientist في نظرية الأنواع أو التحقق الشكلي
   - Head of Community

2. **مساهمون تقنيون**:
   - مطورو C++20 بخبرة في المترجمات
   - خبراء Lean 4 / Coq
   - مطورو TypeScript (VS Code extension)

3. **متبنون أوائل** (Early Adopters):
   - باحثون في الجامعات
   - فرق هندسية في شركات ناشئة
   - مطورون مستقلون

### 📝 كيف تساهم

```bash
# 1. Fork المستودع
git clone https://github.com/YOUR_USERNAME/dhaad-stage0.git

# 2. إنشاء فرع
git checkout -b feature/my-contribution

# 3. البناء والاختبار
cmake -B build -G "Visual Studio 17 2022"
cmake --build build --config Release
./build/Release/dhaad_test_runner.exe

# 4. الالتزام
git commit -m "Add: my contribution"

# 5. Push وفتح Pull Request
git push origin feature/my-contribution
```

📎 **الدليل الكامل** في [`CONTRIBUTING.md`](CONTRIBUTING.md).

---

## الترخيص

هذا المشروع مرخّص تحت **DMEOL-2.0-Universal (Perpetual Ethical Edition)**.

| الفئة                      | السعر       | الشروط      |
| -------------------------- | ----------- | ----------- |
| **أفراد وتعليم**           | مجاني       | Attribution |
| **مفتوح المصدر**           | مجاني       | Attribution |
| **Startup** (< $10M)       | $500/سنة    | Attribution |
| **Professional** (< $100M) | $5,000/سنة  | Attribution |
| **Enterprise** (>= $100M)  | $50,000/سنة | Negotiated  |
| **Government**             | تفاوضي      | Negotiated  |

📎 **النص الكامل** في [`LICENSE`](LICENSE) و [`docs/licensing/`](docs/licensing/).

---

## التواصل

- **GitHub Issues**: [github.com/dhaad-organization/dhaad-stage0/issues](https://github.com/dhaad-org/dhaad-stage0/issues)
- **GitHub Discussions**: [github.com/dhaad-organization/dhaad-stage0/discussions](https://github.com/dhaad-org/dhaad-stage0/discussions)
- **البريد الإلكتروني**: contact@dhaad.org
- **الموقع الرسمي**: [dhaad.org](https://dhaad.org) (قيد الإنشاء)

---

## شكر وتقدير

- **MSVC 19.44** — للبناء Windows
- **LLVM 21.1.1** — للـ backend
- **vcpkg** — لإدارة الاعتماديات
- **doctest** — لإطار الاختبار
- **Lean 4** — للتحقق الشكلي

---

## حالة المشروع

**الحالة**: 🟡 **مرحلة الإثبات (Proof of Concept)**

- ✅ المترجم يعمل
- ✅ الاختبارات تنجح
- ✅ الملكية الفكرية مسجلة
- ⚠️ لا مستخدمين خارجيين بعد
- ⚠️ لا فريق بعد
- ⚠️ 64 نظاماً مؤجّل

**ندعو المؤسسين والمتبنين الأوائل للانضمام.**

---

<div align="center">

**© 2024-2026 Dhaad Organization. جميع الحقوق محفوظة.**

صُنع بـ 🖤 في المملكة العربية السعودية

[براءة اختراع SA-1020266164](docs/PATENT.md) · [حقوق المؤلف SA-261295185201](docs/COPYRIGHT.md) · [علامة تجارية SA-1267997](docs/TRADEMARK.md)

</div>
```
