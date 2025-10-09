# STIGWE

The Security Technical Implementation Guide (STIG) Weakness Enumerations (WE), STIGWE, is a comprehensive mapping repository that provides bidirectional relationships between Common Weakness Enumeration (CWE) IDs and Security Technical Implementation Guide (STIG) IDs. This project aims to help security professionals and developers correlate security weaknesses with specific security implementation guidelines.

## Overview

This repository contains a comprehensive database of CWE-to-STIG mappings and STIG-to-CWE mappings, providing extensive cross-referencing capabilities between the two major security frameworks. These mappings enable organizations to:

- Translate security vulnerabilities identified in code scans (CWE) to actionable security configurations (STIG)
- Map security configuration requirements (STIG) to potential security weaknesses they address (CWE)
- Enhance compliance and security assessment workflows
- Bridge the gap between development security practices and operational security configurations

## Structure

The repository contains YAML files that define mappings between CWE and STIG IDs. Each mapping can specify a default (most relevant) relationship in either direction:

- **CWE → STIG**: Maps CWE IDs to relevant STIG IDs, with the ability to mark the most applicable STIG
- **STIG → CWE**: Maps STIG IDs to relevant CWE IDs, with the ability to mark the most applicable CWE

## File Format

The mappings are stored in YAML format in the `mappings.yaml` file. The structure follows this format:

```yaml
stig_to_cwe:
  SV-222387:
    cwe_ids:
      - id: "CWE-799"
        default: true

cwe_to_stig:
  CWE-2:
    stig_ids:
      - id: "SV-222515"
        default: true
```

### Fields Explanation

- **`stig_to_cwe`**: Maps STIG IDs to their related CWE IDs
  - Each STIG ID contains a list of CWE IDs
  - The `default` field indicates the most relevant CWE for that STIG

- **`cwe_to_stig`**: Maps CWE IDs to their related STIG IDs
  - Each CWE ID contains a list of STIG IDs
  - The `default` field indicates the most relevant STIG for that CWE

## Data Sources

The mappings in this repository are derived from:
- **stigmap.csv**: Contains STIG-to-CWE mappings
- **cwemap.csv**: Contains CWE-to-STIG mappings

These source files provide the foundational data that is processed and structured into the YAML format for easier consumption by various security tools and frameworks.

## Usage

The YAML files can be parsed using any YAML parser in your preferred programming language. The structure allows for:

1. **Finding all related STIG IDs for a given CWE**
2. **Finding all related CWE IDs for a given STIG**
3. **Identifying the most relevant (default) mapping in either direction**
4. **Bulk processing for security assessment automation**

### Example Use Cases

- **Security Scanning Integration**: Map CWE findings from SAST/DAST tools to relevant STIG controls
- **Compliance Mapping**: Cross-reference STIG requirements with potential security weaknesses
- **Risk Assessment**: Understand what security weaknesses are addressed by specific STIG controls
- **Security Tool Development**: Build applications that bridge development and operations security practices

## Contributing

Contributions are welcome! Please feel free to submit pull requests with:
- New mappings or corrections to existing ones
- Updates to source CSV files
- Documentation improvements
- Tool integrations or example code

When contributing, please ensure that:
- Mappings are accurate and well-researched
- Source data is properly attributed
- Changes are tested and documented

## License

This project is licensed under the Creative Commons Attribution 4.0 International License (CC BY 4.0) - see the [LICENSE](LICENSE) file for details.
