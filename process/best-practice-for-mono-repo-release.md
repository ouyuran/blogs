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

### Release aspect

Release aspect is a combination of components with specified version that pass center quality gating.

Question: when to do the test?

post-review | gate | releasing | released

👆
currently here

            👆 do the test here (A1 + B1 + C0, A1, B1 are newly built, C0 from legacy)
            
                       👆 (Retest if there is a new version of C)
                       For Python we should rebuild, because it's not possible to change the package version, due to hash check
                       For Docker image, we can simply download the one from gate pipeline re-tag and push it again
                       We should make the window of release pipeline as one.

#### Unified versioning

Pulumi: always use same version for Python packages and plugins

#### Meta packages - with entity

Example: docker, helm chart, vv stability job

#### Release aspect - without entity

Git tags

Release/1.0.1
New:
  A/1.0.1
  B/1.0.1
Legacy:
  C/1.0.0
