# Compatibility

## Solution1: fully compatibility
All packages in its lifecycle should be compatible with each other.

With capacity negotiation.

Problem: develpment overhead

### Examples:
Micro services

Telecom

## Solution2: limited compatibility
Packages in its lifecysle can be compatible with each other in a limited range.

Ref: schema compatibility demo.

### compatibility matrix
Problem: hard to maintain

## Solution3: no compatibility
Packages is only compatible with one version of other packages.

### Always latest (where we are, it's not a solution)
Problem: need maintainance window (strong consistency), or retry (enventually consistency)

### Unified versioning

Pulumi: always use same version for Python packages and plugins

### Release aspect

#### Meta packages - with entity

Example: docker, helm chart, vv stability job

#### Release aspect - without entity

Git tags