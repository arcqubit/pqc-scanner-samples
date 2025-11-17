# Contributing to PQC Scanner Samples

Thank you for your interest in contributing sample vulnerable applications to help test and demonstrate PQC Scanner!

## Table of Contents

- [Adding New Samples](#adding-new-samples)
- [Sample Requirements](#sample-requirements)
- [Documentation Standards](#documentation-standards)
- [Testing Guidelines](#testing-guidelines)
- [Pull Request Process](#pull-request-process)

---

## Adding New Samples

### Sample Criteria

New samples should:

1. **Be Realistic**: Represent real-world vulnerable code patterns
2. **Be Educational**: Clearly demonstrate specific vulnerabilities
3. **Be Multi-Vulnerability**: Include multiple vulnerability types
4. **Be Well-Documented**: Have comprehensive vulnerability documentation
5. **Be Tested**: Include test suite to verify the vulnerable code works

### Supported Languages

We accept samples in:
- JavaScript/TypeScript (Node.js, React, Angular, Vue)
- Python (Flask, Django, FastAPI)
- Java (Spring Boot, Jakarta EE)
- C/C++ (Embedded, system-level)
- Go
- Rust (with intentional unsafe usage)
- PHP
- Ruby
- Kotlin
- Swift

## Sample Requirements

### Directory Structure

```
your-sample-name/
├── README.md                  # Sample overview and documentation
├── VULNERABILITIES.md         # Detailed vulnerability documentation
├── src/                       # Source code
├── tests/                     # Test suite
├── .gitignore                 # Language-specific ignores
├── package.json               # NPM (if applicable)
├── requirements.txt           # Python (if applicable)
├── Cargo.toml                 # Rust (if applicable)
└── build files                # Language-specific build files
```

### README.md Template

```markdown
# Sample Name

Brief description of the application.

## Overview

- **Language**: [Language/Framework]
- **Vulnerabilities**: [Number] intentional vulnerabilities
- **Compliance Score**: [Score]/100
- **Use Case**: [Description]

## Vulnerabilities

Summary of vulnerability types included:
- RSA-1024: [count]
- ECDSA: [count]
- MD5: [count]
- etc.

## Running the Application

\`\`\`bash
# Installation instructions
# Run instructions
\`\`\`

## Scanning with PQC Scanner

\`\`\`bash
pqc-scanner scan src/
\`\`\`

### Expected Results

- **Total Vulnerabilities**: [number]
- **Critical**: [number]
- **High**: [number]
- **Medium**: [number]

## Architecture

Brief description of application architecture.

## License

MIT License - For testing and educational purposes only.
```

### VULNERABILITIES.md Template

```markdown
# Vulnerability Documentation: [Sample Name]

## Summary

- **Total Vulnerabilities**: [number]
- **Critical**: [number]
- **High**: [number]
- **Medium**: [number]
- **Low**: [number]

## Detailed Vulnerability List

### 1. [Vulnerability Name]

- **Type**: [e.g., Quantum-Vulnerable Algorithm]
- **Severity**: [Critical/High/Medium/Low]
- **Location**: `[file]:[line]`
- **Algorithm**: [e.g., RSA-1024]
- **Description**: Detailed description
- **Impact**: What could an attacker do?
- **Remediation**: How to fix it

\`\`\`[language]
// Vulnerable code snippet
\`\`\`

---

(Repeat for each vulnerability)
```

## Documentation Standards

### Vulnerability Documentation

Each vulnerability must include:

1. **Type Classification**:
   - Quantum-Vulnerable Algorithm (RSA, ECDSA, ECDH, DSA, DH)
   - Deprecated Hash (MD5, SHA-1)
   - Weak Cipher (DES, 3DES, RC4)
   - Configuration Issue
   - Random Number Generation
   - Key Management

2. **Severity Ratings**:
   - **Critical**: Easily exploitable, high impact
   - **High**: Exploitable with effort, significant impact
   - **Medium**: Requires specific conditions, moderate impact
   - **Low**: Limited exploitability or impact

3. **Code Location**: Exact file and line number

4. **Remediation**: Specific fix instructions

### Code Comments

Mark vulnerable code with comments:

```javascript
// VULNERABILITY: RSA-1024 - Quantum-vulnerable key size
const key = crypto.generateKeyPairSync('rsa', { modulusLength: 1024 });
```

```python
# VULNERABILITY: MD5 - Deprecated hash function
hash = hashlib.md5(data).hexdigest()
```

## Testing Guidelines

### Test Requirements

Each sample must include:

1. **Functional Tests**: Verify the application works
2. **Vulnerability Tests**: Confirm vulnerabilities are present
3. **Scanner Tests**: Verify PQC Scanner detects all vulnerabilities

### Test Example

```javascript
// tests/vulnerabilities.test.js
describe('Vulnerability Detection', () => {
  it('should use RSA-1024', () => {
    // Verify vulnerable code uses RSA-1024
    const keySize = getKeySize();
    expect(keySize).toBe(1024);
  });
});
```

## Pull Request Process

### 1. Fork and Clone

```bash
git clone https://github.com/YOUR_USERNAME/pqc-scanner-samples.git
cd pqc-scanner-samples
git checkout -b add-sample-your-sample-name
```

### 2. Add Your Sample

```bash
mkdir your-sample-name
# Create files following the structure above
```

### 3. Document Thoroughly

- Complete README.md
- Complete VULNERABILITIES.md
- Add inline code comments
- Update root README.md with sample entry

### 4. Test Locally

```bash
# Install PQC Scanner
# Scan your sample
pqc-scanner scan your-sample-name/src/

# Verify all vulnerabilities detected
# Run functional tests
cd your-sample-name && npm test  # or equivalent
```

### 5. Submit Pull Request

```bash
git add your-sample-name/
git commit -m "feat: Add [YourSampleName] vulnerable application

- Language: [language]
- Vulnerabilities: [count]
- Use case: [description]"

git push origin add-sample-your-sample-name
```

Then create a pull request with:
- Clear title: "Add [Sample Name] vulnerable application"
- Comprehensive description
- Vulnerability summary
- Test results

### PR Checklist

- [ ] README.md complete
- [ ] VULNERABILITIES.md complete
- [ ] Code has inline vulnerability comments
- [ ] Tests included and passing
- [ ] No node_modules or build artifacts committed
- [ ] .gitignore properly configured
- [ ] Scanned with PQC Scanner
- [ ] All expected vulnerabilities detected
- [ ] Root README.md updated with new sample

## Code Review

Maintainers will review for:

1. **Realism**: Does it represent real-world vulnerable code?
2. **Educational Value**: Are vulnerabilities clear and well-documented?
3. **Accuracy**: Are vulnerability descriptions accurate?
4. **Completeness**: Is documentation comprehensive?
5. **Testing**: Are tests adequate?
6. **Scanner Detection**: Does PQC Scanner detect all vulnerabilities?

## Questions?

- Open a [GitHub Discussion](https://github.com/arcqubit/pqc-scanner-samples/discussions)
- Reference the main [PQC Scanner repository](https://github.com/arcqubit/pqc-scanner)

**Thank you for contributing!**
