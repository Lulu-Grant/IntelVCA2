# Documentation Scope and Boundaries

## 1. Who This Documentation Is For

This documentation is mainly for two groups:

- readers who are encountering Intel VCA2 for the first time and want to decide whether it is worth pursuing
- readers who already have the full official package and want a clearer structure before starting practical work

The goal is not to replace the package itself. The goal is to reorganize scattered materials into something easier to understand.

## 2. What This Documentation Solves

This repository mainly helps answer:

- what Intel VCA2 actually is
- why it is difficult to use
- what platform and preparation work are required
- how the host and nodes divide responsibilities
- how RAMDisk and BlockIO differ
- how node networking, SSH, and service deployment should be understood
- which use cases make sense and which do not

## 3. What Still Comes From the Official Package

Even though this repository is designed to be readable, the official package should remain the authority for:

- exact installation commands
- node-management commands
- image mount commands
- default accounts and passwords
- tool paths, script names, and service names
- version-to-version mapping details

The reason is not source trust. The reason is that package layout and command details can vary across versions.

## 4. Why the Repository Focuses on Curated Content

The public purpose of this repository is:

- to provide clear, structured, readable documentation

It is not meant to:

- dump every source file in raw form in front of the end reader

That keeps the front page cleaner and the reading path clearer.

## 5. Recommended Reading and Working Pattern

A practical sequence is:

1. start with [Intel VCA2 Quick Start](./QUICKSTART.en.md)
2. continue through the English documentation set
3. use the README package index to organize downloads
4. defer to the official package for the final execution details

That is usually more efficient than trying to reconstruct the full workflow directly from the package layout.

## 6. One-Sentence Summary

> This repository is a rewritten usage guide that helps readers understand and operationalize Intel VCA2, while the official package provides the final implementation details.
