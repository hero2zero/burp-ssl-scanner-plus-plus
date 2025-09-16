# Changelog

All notable changes to the SSL Scanner++ extension will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.0.4] - 2025-09-16

### Changed
- **API Compliance**: Updated to conform with latest Burp Suite Extension API standards
- **Java Runtime**: Upgraded from Java 11 to Java 21 for better performance and modern language features
- **Montoya API**: Updated from 2023.12.1 to 2025.5 for latest Burp Suite compatibility
- **Dependency Management**: Set Montoya API dependency scope to `provided` following BApp Store requirements

### Added
- **Resource Cleanup**: Implemented proper `terminate()` method for clean extension unloading
- **Thread Safety**: Added background scan cancellation during extension termination
- **Extension State**: Added extension unload tracking to prevent operations on terminated extension

### Fixed
- **Memory Leaks**: Proper cleanup of references and background tasks during extension unload
- **Thread Management**: Ensures CompletableFuture scan tasks are properly cancelled when extension is unloaded
- **Resource Management**: Prevents hanging threads when Burp Suite is closed or extension is reloaded

### Technical Details
- Added `terminate()` override in BurpExtender class for proper shutdown handling
- Added `cancelAnyRunningScan()` method to SSLScannerTab for graceful scan termination
- Updated Maven configuration for Java 21 compatibility
- Enhanced dependency management following Burp Suite extension best practices

## [1.0.3] - 2025-09-15

### Fixed
- **Critical**: Fixed compatibility issue with Burp Suite Professional 2025.9.1 where scan results were not appearing in the Target tab's Issues pane
- Fixed AuditIssue creation to properly associate issues with HttpRequestResponse objects
- Removed deprecated direct sitemap access that was causing issues to not display properly
- Enhanced issue reporting mechanism to use Burp's standard audit result system

### Changed
- Updated SSLIssue class to accept and include HttpRequestResponse objects for proper issue association
- Modified ScanResult class to use proper audit issue reporting instead of direct sitemap manipulation
- Enhanced SSLScannerCheck to pass original request/response context to ensure issues are properly linked
- Improved logging for better debugging of issue creation and reporting

### Technical Details
- Added HttpRequestResponse parameter support throughout the scanning chain
- Updated AuditIssue.auditIssue() method calls to include proper request/response context
- Replaced `api.siteMap().add()` calls with standard scanner result reporting
- Added constructor overloads to SSLIssue class for backward compatibility

## [1.0.2] - Previous Release

### Added
- Advanced SSL/TLS vulnerability detection
- Support for multiple vulnerability checks (Heartbleed, POODLE, SWEET32, DROWN, FREAK, BEAST, etc.)
- Integration with Burp Suite's active scanner
- Custom UI tab for manual scanning
- Context menu integration for right-click scanning
- Comprehensive cipher suite analysis
- Progress tracking and cancellation support

### Features
- Automatic detection of deprecated SSL/TLS protocols (SSLv2, SSLv3, TLS 1.0, TLS 1.1)
- Vulnerability scanning for major SSL/TLS security issues
- Weak cipher detection and analysis
- Integration with Burp's Target tab for issue management
- Real-time scan progress and status updates
- Detailed vulnerability reporting with severity levels