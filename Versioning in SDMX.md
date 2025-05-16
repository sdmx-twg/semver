
# Versioning in SDMX

In SDMX, maintainable artefacts contain a version number as part of their URN. These version numbers come in 2-digit and 3-digit (following semantic versioning) variants. Semantically-versioned artefacts allow for wildcard references. The wildcard references allow for easier data model maintenance and enhancements. It is highly recommended that agencies migrate to use semantic versioning as outlined in [Implementing semantic versioning in an existing SDMX enviroment](#implementing-semantic-versioning-in-an-existing-sdmx-enviroment)

**Note**: The guidance in this document differs from the existing annex on semantic versioning in the SDMX standard: Section 6 Technical Notes. These guidelines will likely supersede the annex as part of the SDMX 3.2.0 release.

## Motivation

In the world of data modelling there exists a dreaded place called “dependency hell.” The bigger your data model through organisational, national or international harmonisation grows and the more artefacts you integrate into your modelling, the more likely you are to find yourself, one day, in this pit of despair.

In systems with many dependencies, releasing new artefact versions can quickly become a nightmare. If the dependency specifications are too tight, you are in danger of version lock (the inability to upgrade a artefact without having to release new versions of every dependent artefact). If dependencies are specified too loosely, you will inevitably be bitten by version promiscuity (assuming compatibility with more future versions than is reasonable). Dependency hell is where you are when version lock and/or version promiscuity prevent you from easily and safely moving your data modelling forward.

As a very successful solution to the similar problem in software development, “Semantic Versioning" [semver.org](https://semver.org/) proposes a simple set of rules and requirements that dictate how version numbers are assigned and incremented. These rules make also perfect sense in the world of data modelling, and help to solve the “dependency hell” encountered with previous versions of SDMX. SDMX 3.0 and above applies thus the Semantic Versioning rules on all SDMX artefacts. Once you release an SDMX artefact, you communicate changes to it with specific increments to your version number. Consider a version format of X.Y.Z (Major.Minor.Patch). Property changes not affecting the artefact compatibility increment the patch version, backwards compatible artefact element additions/changes increment the minor version, and backwards incompatible artefact changes increment the major version.

**This SDMX 3.0 specification inherits the original [semver.org](https://semver.org/) 2.0.0 wording (license: [Creative Commons - CC BY 3.0](http://creativecommons.org/licenses/by/3.0/)) and applies it to SDMX artefacts.** Under this scheme, version numbers and the way they change convey meaning about the underlying data structures and what has been modified from one version to the next.

## SDMX 3.0 Semantic Versioning Specification

The key words “MUST”, “MUST NOT”, “REQUIRED”, “SHALL”, “SHALL NOT”, “SHOULD”, “SHOULD NOT”, “RECOMMENDED”, “MAY”, and “OPTIONAL” in this document are to be interpreted as described in [RFC 2119](http://tools.ietf.org/html/rfc2119).

1) All versionable SDMX artefacts MUST specify a version number.
1) A normal version number MUST take the form X.Y.Z where X, Y, and Z are non-negative integers, and MUST NOT contain leading zeroes. X is the major version, Y is the minor version, and Z is the patch version. Each element MUST increase numerically. For instance: 1.9.0 -> 1.10.0 -> 1.11.0.
1) Once a versioned artefact has been released, the contents of that version MUST NOT be modified. Any modifications MUST be released as a new version.
1) Major version zero (0.y.z) is for initial modelling. Anything MAY change at any time. The public artefact SHOULD NOT be considered stable.
1) Version 1.0.0 defines the public artefact. The way in which the version number is incremented after this release is dependent on this public artefact and how it changes.
1) Patch version Z (x.y.Z | x > 0) MUST be incremented if only backwards compatible property changes are introduced. A property change is defined as an internal change that does not affect the relationship to other artefacts. These are changes in the artefact's or artefact element's names, descriptions and annotations that MUST NOT alter their meaning.
1) Minor version Y (x.Y.z | x > 0) MUST be incremented if a new, backwards compatible element is introduced to the public artefact. These are additional items in ItemScheme artefacts. *MUST be incremented if any public artefact element is marked as deprecated.* It MAY be incremented if substantial new information is introduced within the artefact's properties. It MAY include patch level changes. Patch version MUST be reset to 0 when minor version is incremented.
1) Major version X (X.y.z | X > 0) MUST be incremented if any backwards incompatible changes are introduced to the public artefact. These often relate to deletions of items in ItemSchemes or to backwards incompatibility introduced due to changes in references to other artefacts. A major version change MAY also include minor and patch level changes. Patch and minor version MUST be reset to 0 when major version is incremented.

### Extensions

A mutable version, e.g. used for externally released or public drafts or as pre-release, must be denoted by appending an extension that consists of a hyphen and a series of dot separated identifiers immediately following the patch version (x.y.z-EXT). Identifiers must comprise only ASCII alphanumerics and hyphen [0-9A-Za-z-]. Identifiers must NOT be empty. Numeric identifiers must NOT include leading zeroes. However, to foster harmonisation and general comprehension it is generally recommended to use the standard extension "-draft". Examples of allowed extensions: 1.0.0-draft, 1.0.0-draft.1, 1.0.0-0.3.7, 1.0.0-x.7.z.92.

When making changes to an SDMX artefact with an extended version number then one is not required to increment the version if those changes are kept within the allowed scope of the version increment from the previous version (if that existed). Concretely, a version X.0.0-EXT will allow for any changes, a version X.Y.0-EXT will allow only for minor changes and a version X.Y.Z-EXT will allow only for any patch changes, as defined above. This is an important restriction of the general SemVar standard where "A pre-release version indicates that the version is unstable and might not satisfy the intended compatibility requirements as denoted by its associated normal version".

Precedence refers to how versions are compared to each other when ordered. Precedence must be calculated by separating the version into major, minor, patch and extension identifiers in that order. Precedence is determined by the first difference when comparing each of these identifiers from left to right as follows: major, minor, and patch versions are always compared numerically. Example: 1.0.0 < 2.0.0 < 2.1.0 < 2.1.1. When major, minor, and patch are equal, an extended version has lower precedence than a stable version. Example: 1.0.0-draft < 1.0.0. Precedence for two extended versions with the same major, minor, and patch version must be determined by comparing each dot separated identifier from left to right until a difference is found as follows: identifiers consisting of only digits are compared numerically and identifiers with letters or hyphens are compared lexically in ASCII sort order. Numeric identifiers always have lower precedence than non-numeric identifiers. A larger set of extension fields has a higher precedence than a smaller set, if all of the preceding identifiers are equal. Example: 1.0.0-draft < 1.0.0-draft.1 < 1.0.0-draft.prerelease < 1.0.0-prerelease < 1.0.0-prerelease.2 < 1.0.0-prerelease.11 < 1.0.0-rc.1 < 1.0.0.

Wildcarded references in a stable artefact implicitly target only future stable versions of the referenced artefacts within the defined wildcard scope.

* Example: The reference to "AGENCY_ID:CODELIST_ID(2.3+.1)" in an artefact "AGENCY_ID:DSD_ID(2.2.1)" resolves to artefact "AGENCY_ID:CODELIST_ID(2.4.3)" if that was currently the latest available stable version.
Wildcarded references in a version-extended artefact implicitly target future stable and version-extended versions of the referenced artefacts within the defined wildcard scope.
* Example: The reference to "AGENCY_ID:CODELIST_ID(2.3+.1)" in an artefact "AGENCY_ID:DSD_ID(2.2.1-draft)" resolves to artefact "AGENCY_ID:CODELIST_ID(2.5.0-draft)" if that was currently the latest available version.
References to specific version-extended artefacts MAY be used, but those cannot be combined with a wildcard.

**Note**: Semantic versioning in SDMX does not allow for build metadata to be included in the version number, for exmaple while 1.0.0-draft+exp.sha.5114f85 is a valid in the general SemVar standard but is not allowed in SDMX.

### Implementing semantic versioning in an existing SDMX enviroment

When migrating from 2-digit versioning to semantic versioning it is important to work my artefact type up the dependency tree. For example, Codelists -> ConceptScheme -> DataStructure -> Dataflow. This is because while non-versioned and 2-digit version SDMX structural artefacts can reference any other non-versioned or versioned SDMX structural artefacts. Semantically versioned artefacts must only reference other semantically versioned artefacts.

When migrating a particular artefact it is recomended to migrate only the lastest version of each major version number. This version number should be completed by adding the missing version parts with 0s to make the version number semantic versioning compliant.  For example.

| 2-digit version   | Semantic versioning   |
|:-----------------:|:---------------------:|
|1.0                | not migrated          |
|1.1                | not migrated          |
|1.2                | 1.2.0                 |
|2.0                | not migrated          |
|2.1                | 2.1.0                 |
|3.0                | 3.0.0                 |

This strategy ensures that the semantic versioned artefacts actually follows the semantic versioning guidelines as all there is only one artefact for each major version. This also ensure we don't have an elebrate mapping between semantic versioning numbes and 2-digit version numbers.

If an artefact following 2-digt versioning with "isFinal=false" needs to be migrated then a version extension should be added. For example, version 1.3 with isFinal=false becomes version 1.3.0-draft.

### Backus–Naur Form Grammar for Valid SDMX 3.0 Semantic Versions

```bnf
<valid semver> ::= <version core>
                 | <version core> "-" <pre-release>

<version core> ::= <major> "." <minor> "." <patch>

<major> ::= <numeric identifier>

<minor> ::= <numeric identifier>

<patch> ::= <numeric identifier>

<pre-release> ::= <dot-separated pre-release identifiers>

<dot-separated pre-release identifiers> ::= <pre-release identifier>
                                          | <pre-release identifier> "." <dot-separated pre-release identifiers>

<pre-release identifier> ::= <alphanumeric identifier>
                           | <numeric identifier>

<alphanumeric identifier> ::= <non-digit>
                            | <non-digit> <identifier characters>
                            | <identifier characters> <non-digit>
                            | <identifier characters> <non-digit> <identifier characters>

<numeric identifier> ::= "0"
                       | <positive digit>
                       | <positive digit> <digits>

<identifier characters> ::= <identifier character>
                          | <identifier character> <identifier characters>

<identifier character> ::= <digit>
                         | <non-digit>

<non-digit> ::= <letter>
              | "-"

<digits> ::= <digit>
           | <digit> <digits>

<digit> ::= "0"
          | <positive digit>

<positive digit> ::= "1" | "2" | "3" | "4" | "5" | "6" | "7" | "8" | "9"

<letter> ::= "A" | "B" | "C" | "D" | "E" | "F" | "G" | "H" | "I" | "J"
           | "K" | "L" | "M" | "N" | "O" | "P" | "Q" | "R" | "S" | "T"
           | "U" | "V" | "W" | "X" | "Y" | "Z" | "a" | "b" | "c" | "d"
           | "e" | "f" | "g" | "h" | "i" | "j" | "k" | "l" | "m" | "n"
           | "o" | "p" | "q" | "r" | "s" | "t" | "u" | "v" | "w" | "x"
           | "y" | "z"
```

## FAQ

**How should I deal with revisions in the 0.y.z initial modelling phase?**  
The simplest thing to do is start your initial modelling release at 0.1.0 and then increment the minor version for each subsequent release.

**How do I know when to release 1.0.0?**  
If your data model is being used in production, it should probably already be 1.0.0. If you have a stable artefact on which users have come to depend, you should be 1.0.0. If you’re worrying a lot about backwards compatibility, you should probably already be 1.0.0.

**Doesn’t this discourage rapid modelling and fast iteration?**  
Major version zero is all about rapid modelling. If you’re changing the artefact every day you should either still be in version 0.y.z or on the next (minor or) major version for a separate modelling.

**If even the tiniest backwards incompatible changes to the public artefact require a major version bump, won’t I end up at version 42.0.0 very rapidly?**  
This is a question of responsible modelling and foresight. Incompatible changes should not be introduced lightly to a data model that has a lot of dependencies. The cost that must be incurred to upgrade can be significant. Having to bump major versions to release incompatible changes means you’ll think through the impact of your changes, and evaluate the cost/benefit ratio involved.

**What do I do if I accidentally release a backwards incompatible change as a minor version?**  
As soon as you realise that you’ve broken the SDMX 3.0 Semantic Versioning specification, fix the problem and release a new minor version that corrects the problem and restores backwards compatibility. Even under this circumstance, it is unacceptable to modify versioned releases. If it’s appropriate, document the offending version and inform your users of the problem so that they are aware of the offending version.

**What are the rules for deleting a version? Does it mean I can re-release the same version with different content?**  
SDMX Semantic Versioning doesn't and cannot control such things. SDMX Semantic Versioning is about a contract between producers and consumers to which both adhere. Producers can freely delete (e.g. old outdated, unused) artefacts and upload new artefacts with new versions. However, a producer who deletes a stable artefact and then uploads a changed artefact with the same stable version, breaks the contract. And the clients will be unhappy because their consuming systems might get broken!
  
**What should I do if I update my own dependencies without changing the public artefact?**  
That would be considered compatible since it does not affect the public artefact. Artefacts that explicitly depend on the same dependencies as your artefact should have their own dependency specifications and the author will notice any conflicts. Determining whether the change is a patch level or minor level modification depends on whether you updated your dependencies in order to change a property or introduce new backwards compatible items. For the latter instance, one would obviously expect a minor level increment.

**What if I inadvertently alter the public artefact in a way that is not compliant with the version number change (i.e. the modification incorrectly introduces a major breaking change in a patch release)?**  
Use your best judgement. If you have a huge audience that will be drastically impacted by changing the behaviour back to what the public artefact intended, then it may be best to perform a major version release, even though the property change could strictly be considered a patch release. Remember, SDMX 3.0 Semantic Versioning is all about conveying meaning by how the version number changes. If these changes are important to your users, use the version number to inform them.

**How should I handle deprecating elements?**  
Deprecating existing elements is a normal part of data modelling and is often required to make forward progress or follow history (changing classifications, evolving reference areas). When you deprecate part of your public artefact, you should  issue a new minor release with the deprecation in place. Before you completely remove the functionality in a new major release there should be at least one minor release that contains the deprecation so that users can smoothly transition to the new artefact.

**Does SDMX 3.0 Semantic Versioning have a size limit on the version string?**  
No, but use good judgement. A 255 character version string is probably overkill, for example. Also, specific SDMX implementations may impose their own limits on the size of the string. Remember, it is generally recommended to use the standard extension "-draft".  

**Is “v1.2.3” a semantic version?**  
No, “v1.2.3” is not a semantic version. The semantic version is “1.2.3”.

**Is there a suggested regular expression (RegEx) to check an SDMX 3.0 Semantic Versioning string?**  
Please check the SDMX-ML and SDMX-JSON schemas.
