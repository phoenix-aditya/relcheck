# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [0.1.3] - 2024-12-19

### Added
- **Context-aware CLI**: Smart resource detection and automatic namespace inference
- **Simplified commands**: Direct resource checking without complex flags
- **Smart defaults**: Automatic deep scanning for namespaces and clusters
- **Resource type detection**: Auto-detects Pod, Namespace, Service, Deployment types
- **Current namespace awareness**: Automatically uses current kubeconfig namespace

### Changed
- **CLI structure**: Main command now accepts targets directly (e.g., `relcheck all`, `relcheck .`)
- **Command simplification**: `relcheck my-pod` instead of `relcheck check-resource --resource-kind Pod --name my-pod --namespace default`
- **Default behavior**: `.` and `*` now check current namespace with deep scan
- **Context detection**: Automatically detects resource types and namespaces

### Examples
```bash
# New simplified commands:
relcheck all                    # Check everything (cluster + deep scan)
relcheck .                      # Check current namespace + all resources
relcheck cluster                # Check entire cluster
relcheck production             # Check 'production' namespace
relcheck my-pod                 # Check specific pod in current namespace

# With options:
relcheck all --verbose          # Show all checks
relcheck . --format json        # JSON output
relcheck cluster --deep         # Deep cluster scan
```

## [0.1.1] - 2024-12-19

### Added
- Enhanced CLI help system with comprehensive option descriptions
- Added `--version` flag to display tool version
- Improved command documentation with practical examples
- Professional README with PyPI installation instructions
- Comprehensive usage examples and extension guide

### Changed
- Updated CLI descriptions to be more user-friendly
- Enhanced help text for all command options
- Improved main command description explaining tool purpose

### Fixed
- Better error messages and usage guidance
- Consistent help text formatting

## [0.1.0] - 2024-12-19

### Added
- Initial release of relcheck CLI tool
- Kubernetes resource diagnostics framework
- Support for Pod, Namespace, and Cluster resource types
- Comprehensive health checks for various resource types
- Live cluster inspection via kubectl configuration
- Deep resource traversal with `--deep` flag
- Multiple output formats (table, JSON)
- Extensible check framework for custom diagnostics
- MCP integration ready for AI-powered solutions
- Dynamic check discovery system
