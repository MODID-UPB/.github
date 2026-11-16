# Contributing to MODID-UPB

These guidelines apply to all repositories in the MODID-UPB organization unless a repository provides its own `CONTRIBUTING.md`.

## Repository names
Use lowercase names with hyphens:
- `modid-<topic>` or `<software name>` for software, e.g., `modid-CPS-Checker` or `CPS-Checker`
- `<year>-<lead-PP-number>-<lead-author>-<working-title>` for paper sources, e.g., `2026-PP03-schlichtig-CPS-Checker`
- `dataset-<name>` for small datasets and data documentation, e.g., `dataset-empirical-CPS-study`
- `thesis-<PP-number>-<name>` for theses, e.g., `thesis-PP03-student`

## Repository settings
- Default branch: `main` contains the current or latest work.
- Add the topic `modid` to every repository, plus 3–8 topics describing its content (e.g. `static-analysis`, `java`).
- For released tools, enable **Discussions** so that user questions go there instead of the issue tracker.
- Reuse shared workflows from `MODID-UPB/actions` (once available) instead of copying them.

## Visibility
- New repositories are **private** by default.
- A repository is made public only after approval by the PIs. Ask an organization owner to change its visibility.

## Required files for public repositories
- `README.md`: purpose, installation, usage, and the funding acknowledgement
- `LICENSE`: chosen per artifact type, see [Licensing](#licensing). If a repository combines several artifacts (e.g. code and data), state in the `README.md` which license applies to which folder.
- `CITATION.cff`: copy the template from https://github.com/MODID-UPB/.github/blob/main/CITATION.cff and adapt it, or create one with https://citation-file-format.github.io/

`LICENSE` and `CITATION.cff` are **not** inherited from the organization. Every repository needs its own copy.

## Licensing
Publications, software and datasets are licensed **separately**, according to their type, even if they belong together (e.g. a paper with its tool and dataset).
This section gives general guidance. It is not legal advice; it summarizes the recommendations of PROvendis GmbH.

### Software
There is **no default license** for software in MODID.
Before the first public release, choose a license **together with your PI**. Check these questions first:
1. Could the software contain a patentable invention?
2. Is a spin-off or other commercial exploitation possible?
3. Does it contain code or depend on libraries from third parties? Their licenses must be compatible.
4. Did others contribute (e.g. students, external partners)? They hold rights to their contributions.
5. Was code generated with AI tools? See [AI-generated code](#ai-generated-code).

If the answer to 1 or 2 is **yes or unclear**, contact the patent office of Paderborn University **before** choosing a license and before publishing.
An invention that has been published can no longer be patented, and a published open-source release cannot be revoked.
If a spin-off is planned, the software parts for the business model, dependencies on third-party software and rights agreements with all developers (e.g. a Contributor License Agreement) need to be considered separately.

Several common licenses include an **explicit patent license**: whoever releases the software grants all users free, worldwide and irrevocable rights to the related patent claims.
For universities this matters if exploitable intellectual property is involved. Use these licenses only after the check above.

| License | Copyleft | Attribution / notices | Mark changes | Explicit patent license | Can be combined with |
|---|---|---|---|---|---|
| [Apache-2.0](https://www.apache.org/licenses/LICENSE-2.0) | none | keep copyright and license notices, pass on the `NOTICE` file (Section 4) | yes (Section 4(b)) | **yes** (Section 3) | GPL-3.0, AGPL-3.0 (the combined work is then under GPL/AGPL) |
| [GPL-2.0-only](https://www.gnu.org/licenses/old-licenses/gpl-2.0.html) | strong | keep copyright and license notices (Section 1) | yes (Section 2(a)) | no | **none of the other three** |
| [GPL-3.0](https://www.gnu.org/licenses/gpl-3.0.html) | strong | keep copyright and license notices (Section 4) | yes (Section 5(a)) | **yes** (Section 11) | Apache-2.0 code, AGPL-3.0 (Section 13) |
| [AGPL-3.0](https://www.gnu.org/licenses/agpl-3.0.html) | strong, also for use over a network (Section 13) | keep copyright and license notices (Section 4) | yes (Section 5(a)) | **yes** (Section 11) | Apache-2.0 code, GPL-3.0 (Section 13) |

All four licenses allow commercial use and exclude any warranty.
If you want copyleft, **GPL-2.0-only** is preferred, as it does not contain an explicit patent license.
Note that GPL-2.0-only code cannot be combined with code under Apache-2.0, GPL-3.0 or AGPL-3.0. Check your dependencies first (question 3 above).

### AI-generated code
AI-generated or AI-assisted code does not need a separate license, but its origin must be documented:
- Purely AI-generated code is not protected by copyright. Code developed with AI assistance can be, if there is sufficient human creative contribution.
- AI tools can reproduce protected third-party code (see the [GEMA ruling](https://ohn.haendlerbund.de/recht/urteile-entscheidungen/gema-siegt-ki-anbieter)). Review generated code before you publish it.
- Document in the `README.md` which AI tools were used, to what extent code was generated or adopted, and which parts were developed or revised by humans. A general statement is not sufficient. This is especially important if the software might later be licensed commercially.

### Publications, documentation and data
Publications, documentation and data are licensed under one of the [Creative Commons 4.0 licenses](https://creativecommons.org/share-your-work/cclicenses/). Common CC licenses are widely used in scientific publishing. For research data and metadata, CC0 1.0 is also an option.

The CC licenses are modular. Every license except CC0 requires attribution (**BY**): name the author, the license with a link, and indicate whether changes were made. Up to two modules can be added:
- **SA** (ShareAlike): adaptations must use the same license
- **NC** (NonCommercial): no commercial use
- **ND** (NoDerivatives): no adaptations may be shared (cannot be combined with SA)

**Options named by PROvendis GmbH ¹**

| License | Modules | Attribution | Indicate changes | Commercial use | Share adaptations | Share alike | Counts as open ([Open Definition](https://opendefinition.org/licenses/)) | Notes |
|---|---|---|---|---|---|---|---|---|
| [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) ¹ | BY | yes | yes | yes | yes | no | yes | generally suitable for open-access publications |
| [CC BY-ND 4.0](https://creativecommons.org/licenses/by-nd/4.0/) ¹ | BY, ND | yes | yes | yes | no | – | no | offered by publishers as a more restrictive option; choose depending on publication goals, publisher's conditions and funding requirements |
| [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/) ¹ | BY, NC, SA | yes | yes | no | yes | yes | no | offered by publishers as a more restrictive option; choose depending on publication goals, publisher's conditions and funding requirements |
| [CC0 1.0](https://creativecommons.org/publicdomain/zero/1.0/) ¹ | none (public domain dedication) | no | no | yes | yes | no | yes | additionally an option for research data and metadata |

¹ Named by PROvendis GmbH.

**Further licenses from the CC 4.0 toolkit**

| License | Modules | Attribution | Indicate changes | Commercial use | Share adaptations | Share alike | Counts as open ([Open Definition](https://opendefinition.org/licenses/)) | Notes |
|---|---|---|---|---|---|---|---|---|
| [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/) | BY, SA | yes | yes | yes | yes | yes | yes | common CC license |
| [CC BY-NC 4.0](https://creativecommons.org/licenses/by-nc/4.0/) | BY, NC | yes | yes | no | yes | no | no | restrictive variant; choose depending on publication goals, publisher's conditions and funding requirements |
| [CC BY-NC-ND 4.0](https://creativecommons.org/licenses/by-nc-nd/4.0/) | BY, NC, ND | yes | yes | no | no | – | no | restrictive variant; choose depending on publication goals, publisher's conditions and funding requirements |

For datasets: the CC 4.0 licenses also cover database rights (sui generis rights), so they are suitable for data as well as for text.

The more restrictive NC and ND variants can be chosen depending on the publication goals, the publisher's conditions and funding requirements.
For paper sources, check the publishing agreement before you make the repository public.

### Product liability
From 9 December 2026, the EU Product Liability Directive ([(EU) 2024/2853](https://eur-lex.europa.eu/eli/dir/2024/2853/oj)) also covers software.
Free and open-source software developed or supplied outside the course of a commercial activity is excluded (Article 2(2)). Publishing research software as open source therefore does not by itself make the university or its developers liable as a manufacturer.
This can change if the software is commercialized, offered as part of a paid service, integrated into a product of a spin-off, or if the university or a person acts as its manufacturer on the market. In these cases, contact us before.

### Contact
For questions about licensing, contact your PI, Michael Schlichtig (modid@hni.uni-paderborn.de), or the [patent office of Paderborn University (innovation2business.nrw)](https://www.uni-paderborn.de/forschung/patente/patentverbund).

## Never commit
- Personal data (e.g. study participants, names, e-mail addresses)
- Passwords, API keys, tokens or other credentials
- Confidential data from project partners
- Large raw data. Store it on Zenodo or RADAR and link to it from the repository.

If something sensitive was committed by accident, contact an organization owner immediately. Deleting the file in a new commit does **not** remove it from the history.

## Workflow
1. Create a branch for your change: `git switch -c <short-description>`.
2. Commit in small steps with meaningful messages.
3. Push the branch and open a pull request.
4. On protected branches (`main`), at least one review is required before merging.

## Releases and DOIs
Repositories connected to Zenodo receive a DOI for every GitHub release. Ask an owner to enable the connection for your repository ([tutorial](https://youtu.be/HZ6m8oxwvig?si=dArSWDiiFGqPixrD)).

## Questions
Ask in the MODID Teams channel "GitHub" or open an issue.
