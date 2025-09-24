<div align="center">

# Autonomous Bank Statement Parser Agent

[![Python](https://img.shields.io/badge/Python-3.9%2B-blue?style=flat-square&logo=python)](https://www.python.org/)  
[![Gemini](https://img.shields.io/badge/Gemini-1.5--flash-orange?style=flat-square&logo=google)](https://ai.google.dev/)  
[![License](https://img.shields.io/badge/License-MIT-lightgrey?style=flat-square)](LICENSE)  
[![Build Status](https://img.shields.io/badge/Build-Passing-brightgreen?style=flat-square&logo=github-actions)](https://github.com/d-kavinraja/ai-agent-challenge/actions)  
[![Coverage](https://img.shields.io/badge/Coverage-95%25-brightgreen?style=flat-square&logo=codecov)](https://codecov.io/gh/d-kavinraja/ai-agent-challenge)  
[![Code Style](https://img.shields.io/badge/Code%20Style-Black-black?style=flat-square&logo=python)](https://github.com/psf/black)  

**An intelligent AI agent that autonomously generates, tests, and refines Python parsers for PDF bank statements using iterative feedback loops.**

[Quick Start](#quick-start) • [Documentation](#documentation) • [Contributing](#contributing) • [Community](#community)

</div>

---

## Overview

The **Autonomous Bank Statement Parser Agent** is designed to tackle the **Agent-as-Coder Challenge** by automatically generating Python parsers for PDF bank statements. It validates parser outputs against expected CSV data and improves parsing accuracy through iterative feedback loops.

### Key Features

| Feature | Description |
|---------|-------------|
| **Autonomous Code Generation** | Generates custom Python parsers using Gemini 1.5 Flash |
| **Iterative Refinement** | Enhances parser quality via feedback-driven loops |
| **Test-Driven Development** | Validates outputs against ground truth CSVs |
| **Extensible Architecture** | Easily adaptable for multiple banks |
| **High Accuracy** | Achieves up to 100% parsing accuracy |
| **Simple CLI Interface** | Command-line execution with minimal setup |

### Architecture

The agent follows a **generate-test-refine** cycle:

```mermaid
graph TD
    A[Initialize Agent] --> B[Generate Parser Code]
    B --> C[Load & Execute Parser]
    C --> D[Compare with Expected CSV]
    D --> E{Score > Previous Best?}
    E -->|Yes| F[Save as Best Parser]
    E -->|No| G[Keep Previous Best]
    F --> H{Max Attempts Reached?}
    G --> H
    H -->|No| I[Generate Feedback]
    H -->|Yes| J[Complete - Return Best Parser]
    I --> B
    
    style A fill:#e1f5fe
    style F fill:#c8e6c9
    style J fill:#fff3e0

Technology Stack

Core Technologies:

Python 3.9+

Google Gemini 1.5 Flash

Dynamic Module Loading

Processing & Testing:

pdfplumber (PDF extraction)

pandas (Data manipulation)

DataFrame comparison (parser testing)

Quick Start
Prerequisites