---

## 📦 Supported Platforms

The build script automatically detects your platform and creates optimized binaries for multiple architectures:

### 🐧 Linux Distributions

| Binary                            | Target                     | Description                                                                                           |
| --------------------------------- | -------------------------- | ----------------------------------------------------------------------------------------------------- |
| `token-minter_x86_64-linux-musl`  | x86_64-unknown-linux-musl  | **Universal Linux** - Compatible with most distributions (Ubuntu, Debian, CentOS, Fedora, Arch, etc.) |
| `token-minter_aarch64-linux-musl` | aarch64-unknown-linux-musl | **ARM 64-bit** - For ARM-based systems (Raspberry Pi 4, ARM servers)                                  |
| `token-minter_x86_64-linux-glibc` | x86_64-unknown-linux-gnu   | **Modern Linux** - For systems with glibc (Ubuntu 20+, Debian 11+, etc.)                              |

# Our Discord

If you have any questions, please join our Discord: [https://discord.gg/9HNfg2MS4y](https://discord.gg/myaQG4dMYs)

# Buy me a coffee

Solana: FBhS1a57H6MnHAVcu3MntF1tj8MkGnrvo7nFWc49rgKE

# Solana Mint Address Generator

[![Rust](https://img.shields.io/badge/Rust-1.70+-orange.svg)](https://www.rust-lang.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Platform](https://img.shields.io/badge/Platform-Windows%20%7C%20Linux%20%7C%20macOS-blue.svg)](https://github.com/ReactOnAuth/Rust-Minter-Pump-Bonk)
[![Performance](https://img.shields.io/badge/Performance-1M%2B%20attempts%2Fs-green.svg)](https://github.com/ReactOnAuth/Rust-Minter-Pump-Bonk)
[![Output](https://img.shields.io/badge/Output-JSON%20%7C%20TXT-purple.svg)](https://github.com/ReactOnAuth/Rust-Minter-Pump-Bonk)

A lightning-fast Rust application designed to generate Solana mint addresses with specific suffix patterns for pump.fun and lets.bonk tokens. This generator leverages full CPU utilization across all cores and exports results to JSON or TXT formats.

## Key Features

- ⚡ **Maximum Performance**: Harnesses 100% CPU utilization across all available cores
- 🎯 **Precise Targeting**: Creates addresses ending with "pump" and "bonk" suffixes (case-sensitive matching)
- 🚀 **Dual Mode Optimization**: Combined suffix detection in "both" mode delivers 50% faster generation
- 💾 **Flexible Export**: Supports JSON and TXT output formats with automatic timestamping
- 🔧 **Universal Compatibility**: Runs seamlessly on Windows, Linux, and macOS
- 📈 **Live Performance Tracking**: Real-time monitoring with keys/second metrics
- 🎛️ **Output Customization**: Choose between structured JSON and simple TXT formats

## System Requirements

- **Rust** (stable release)
- **Git**

## Getting Started

### 1. Repository Setup

```bash
git clone https://github.com/wakeupwakeupwakeup/rust-minter-pump-bonk.git
cd rust-minter-pump-bonk
```

### Basic Syntax

```bash
sh ./run.sh [COMMAND] [OPTIONS]

Available Commands:
  pump    Generate pump.fun addresses (ending with "pump")
  bonk    Generate lets.bonk addresses (ending with "bonk")
  both    Generate both address types simultaneously

Available Options:
  -c, --count <COUNT>        Number of addresses to generate [default: 1]
  -f, --format <FORMAT>      Output format (json or txt) [default: json]
  -o, --output <OUTPUT>      Custom output filename (auto-generated if omitted)
  -h, --help                 Display help information
```

## Output Specifications

### JSON Format Structure

```json
[
  {
    "pub_key": "ABC123...pump",
    "private_key": "5KJvsngHeMpm884wtkJNzQGaCErckhHJBGFsvd3VyK5qMZXj3hS",
    "suffix_type": "pump",
    "created_at": "2024-01-15T10:30:00Z"
  }
]
```

### TXT Format Structure

```
# Solana Mint Addresses - Generated with suffix 'pump'
# Generated at: 2024-01-15T10:30:00Z
# Format: public_key,private_key,suffix_type

ABC123...pump,5KJvsngHeMpm884wtkJNzQGaCErckhHJBGFsvd3VyK5qMZXj3hS,pump
```

## Performance Benchmarks

### Expected Throughput (addresses/second):

- **2-core CPU**: ~200K attempts/second
- **4-core CPU**: ~400K attempts/second
- **8-core CPU**: ~800K attempts/second
- **16-core CPU**: ~1.6M attempts/second
- **32-core CPU**: ~3.2M attempts/second

### Performance Enhancements:

- **Dual Detection**: The "both" mode simultaneously checks for "pump" and "bonk" suffixes, achieving ~50% faster generation than sequential processing
- **Live Metrics**: Real-time keys/second display during generation for performance monitoring
- **Batch Optimization**: Efficient batch-level timing for precise performance measurement

### Performance Optimization Guidelines:

1. **Always use release builds** for optimal performance
2. **Run on dedicated hardware** for consistent performance
3. **Use SSD storage** for faster binary loading
4. **Minimize background processes** to maximize CPU availability

### Automatic File Naming

- `pump_addresses_20240115_103000.json`: PUMP addresses in JSON format
- `bonk_addresses_20240115_103000.txt`: BONK addresses in TXT format
- `my_addresses_pump.json`: Custom filename with suffix

### File Content Formats

- **JSON**: Structured data with comprehensive metadata
- **TXT**: CSV format with descriptive header comments

## Security Best Practices

### Production Deployment Considerations:

1. **Secure storage** for generated address files
2. **Regular backup** of generated files
3. **Encrypted storage** for sensitive data
4. **Rate limiting** for public deployments
5. **VPN usage** for remote server access

### Private Key Security Measures:

- Private keys are encoded in base58 format
- Keys are stored in plain text files
- Implement proper file permissions and access controls
- Consider file encryption for enhanced security
