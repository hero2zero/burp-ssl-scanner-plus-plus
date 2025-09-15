# Burp SSL Scanner Plus Plus

A comprehensive SSL/TLS vulnerability scanner extension for Burp Suite built with the modern Montoya API.

## Quick Start

### Installation

1. Download `burp-ssl-scanner-plus-plus.1.0.3.jar` from the releases
2. In Burp Suite, go to **Extensions** → **Installed**
3. Click **Add** and select **Java** as extension type
4. Browse to `burp-ssl-scanner-plus-plus.1.0.0.jar`
5. Click **Next** to load the extension

### Usage

**Manual Scanning:**
1. Navigate to the **SSL Scanner** tab
2. Enter target hostname/URL
3. Click **Start scanning**
4. Review real-time results

**Context Menu:**
- Right-click any HTTP request → **Send URL to SSL Scanner**

**Active Scanning:**
- Automatically runs during Burp's active scans on HTTPS targets

## Features

### Vulnerability Detection
- ✅ **Heartbleed** (CVE-2014-0160)
- ✅ **POODLE** (CVE-2014-3566) 
- ✅ **SWEET32** (CVE-2016-2183)
- ✅ **DROWN** (CVE-2016-0800)
- ✅ **FREAK** (CVE-2015-0204)
- ✅ **BEAST** (CVE-2011-3389)
- ✅ Weak cipher detection
- ✅ Protocol version testing (SSLv2/v3, TLS 1.0-1.3)
- ✅ Cipher suite enumeration

### Integration
- 🔄 Active scanner integration
- 📋 Context menu integration  
- 💾 HTML export functionality
- 🎯 Sitemap reporting (Pro version)

## Requirements

- **Burp Suite Professional/Community** 2023.1+
- **Java Runtime** 11+

## Security Notice

⚠️ **For authorized security testing only**
- Use only on systems you own or have permission to test
- Designed for defensive security assessment
- Results should be used to improve security posture

## Project Info

- **Version:** 1.0.3
- **API:** Burp Suite Montoya API
- **Language:** Java
- **License:** MIT

## Support

For issues or questions:
1. Check Burp's Extensions → Output/Error tabs for logs
2. Verify Java 11+ compatibility
3. Ensure network connectivity to targets
4. Review firewall/proxy settings

---

*Built for professional penetration testing and security assessment*
