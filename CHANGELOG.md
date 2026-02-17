# Changelog

All notable changes to the Folium project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/), and this project adheres to [Semantic Versioning](https://semver.org/).

## [v0.5.0] — 2026-02-17

### Added
- CI/CD pipeline with GitHub Actions ([#38](https://github.com/gpradofe/pdfGenerator/pull/38))
- Comprehensive error handling and validation ([#36](https://github.com/gpradofe/pdfGenerator/pull/36))
- Template gallery with pre-built designs ([#35](https://github.com/gpradofe/pdfGenerator/pull/35))

## [v0.4.0] — 2026-02-10

### Added
- WebAssembly (WASM) compilation target for browser-side PDF generation ([#30](https://github.com/gpradofe/pdfGenerator/pull/30))
- Performance benchmarks suite — Folium vs Puppeteer, WeasyPrint & iText ([#29](https://github.com/gpradofe/pdfGenerator/pull/29))

## [v0.3.0] — 2026-02-03

### Added
- End-to-end test suite for PDF output validation ([#27](https://github.com/gpradofe/pdfGenerator/pull/27))
- Production hardening — graceful shutdown, health checks, logging ([#26](https://github.com/gpradofe/pdfGenerator/pull/26))

## [v0.2.0] — 2026-01-27

### Added
- Docker support with multi-stage builds ([#25](https://github.com/gpradofe/pdfGenerator/pull/25))
- REST API with JSON template input
- Basic template engine with variable interpolation

## [v0.1.0] — 2026-01-20

### Added
- Initial Rust PDF engine with core rendering pipeline
- JSON-to-PDF conversion with layout primitives (text, images, tables)
- Sub-100ms generation for typical documents
- CLI interface for local PDF generation
