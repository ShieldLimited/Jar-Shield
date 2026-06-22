# JarShield

JarShield is an advanced Java security analysis tool designed to inspect, decompile, and analyze `.jar` files for potential vulnerabilities.

## Features

- **✓ JAR inspection:** Extracts classes, metadata, and files.
- **✓ Decompilation:** Leverages the CFR decompiler to read bytecodes into Java source.
- **✓ Security analysis:** Statically analyzes decompiled code for malicious patterns.
- **✓ Rule engine:** Easily extendable security rules mapping via Regex and heuristics.
- **✓ Risk scoring:** Calculates a severity-based risk score (SAFE, LOW, MEDIUM, HIGH, CRITICAL).
- **✓ HTML/JSON reports:** Exports detailed findings to standardized formats.
- **✓ JavaFX interface:** A clean, dark-themed UI to manage tasks easily.
- **✓ CLI support:** Run fully automated headless tests.

## Architecture

JarShield runs a modular pipeline:
`JarReader` -> `Decompiler` -> `Analyzer Engine` -> `Risk Engine` -> `Reporting` -> `GUI / CLI`

## Installation

Ensure you have **Java 21** installed.

Build the application using Maven:
```bash
mvn clean package
```

## Usage

### GUI Mode
Run the packaged JAR without any arguments:
```bash
java -jar target/JarShield-1.0-SNAPSHOT.jar
```
Or run directly with Maven:
```bash
mvn javafx:run
```

### CLI Mode
Run the packaged JAR with a path to the file you want to analyze:
```bash
java -jar target/JarShield-1.0-SNAPSHOT.jar path/to/sample.jar
```

## Configuration

You can override runtime configurations in `src/main/resources/config.properties`:
- `max.jar.size.mb`: Prevents out-of-memory errors on giant jars.
- `cache.enabled`: Uses SHA-256 caching so re-runs of identical jars avoid decompilation.
- `log.level`: Set output verbosity.
