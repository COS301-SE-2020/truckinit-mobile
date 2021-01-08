# Coding & Workflow Standards

A significant portion of developing pwoerful applications, and doing so as an effective team, is to follow well-defined guidelines when developing code and collaborating across any platform. Hence, we have defined standards for all members of the mobile development team to follow when producing code and using our project management tools.

- [Coding & Workflow Standards](#coding-workflow-standards)
	- [Implementation Standards](#implementation-standards)
		- [Code-Writing and -Formatting Practices](#code-writing-and-formatting-practices)
		- [Mobile Architecture](#mobile-architecture)
	- [Project Management Tools](#project-management-tools)
		- [Issue Tracking](#issue-tracking)
		- [Branch & Commit Control](#branch-commit-control)

---

## Implementation Standards
During the course of our development of the mobile app, we will be following a set of guidelines to control the style and structure of our libraries and classes. These standards are subject to continuous change.

### Code-Writing and -Formatting Practices
Part of the motivation for selecting Dart & Flutter as our framework for the mobile apps was that is has a strong basis of extremely detailed conventions for writing and formatting code, and performs extremely powerful optimisation during its cross-compilation. As such, all code should adhere to the [Effective Dart](https://dart.dev/guides/language/effective-dart/style) and [Flutter Formatting](https://flutter.dev/docs/development/tools/formatting) guidelines.

### Mobile Architecture

The layout of the mobile app(s)' internal libraries should respect the following system to enable pipelining of data and elimination of errors in data composition and typing (made extremely easy thanks to [Dart's optional duck-typing](https://dart.dev/guides/language/type-system)).

_(please see next page)_

.\
.\
.\
.\
.

<br/>
<br/>
<br/>
<br/>
<br/>

```
     ┌───────────┐        ╔═══════════════════╗
     │RESTful API│        ║        KEY        ║
     └─────⇑─────┘        ╟───────────────────╢
           ║              ║ ⇑  calls methods  ║
           ║              ║ ↑  uses as object ║
     ┌─────╨──────┐       ╚═══════════════════╝
     │HTTP Handler│
     └─────⇑──────┘       ┌───────────┐
           ║              │JSON Mapper│
           ║              └────⇑──────┘
           ║                   ║
  ┌────────╨───────────┐     ┌─╨──┐
  │Endpoint Controllers├────→│DTOs│
  └────────⇑───────────┘     └─↑──┘
           ║                   │
┌──────────╨───────────┐   ┌───┴────┐
│Internal Data Managers├──→│Entities│
└──────────⇑─────────⇑─┘   └─⇑──────┘
           ║         ╚═══════╝
      ┌────╨────┐    
      │Providers│
      └────╥────┘
           ║
      ┌────⇓─────┐
      │Flutter UI│
      └──────────┘
```

- **RESTful API** - The remote API provides access to all centralised activity in the Truckin-IT ecosystem. For more information, see the documentation provided by the [API development team][gitlab-api-home].

- **HTTP Handler** - All interaction with the API is channelled through this internal gateway, which automatically handles required RESTful methods and conversion between semi-structured internal data in the form of key-value sets (Maps) and transmittable JSON strings.

- **Endpoint Controllers** - These interfaces describe every endpoint on the API using the strict internal standards of Dart. Those endpoints are targeted using the HTTP Handler and the structures needed to interact with them are defined with DTOs.

- **DTOs** - Any collection of structured data needed to communicate with the API is described with a DTO (Data Transfer Object), a simple, immutable object composed only of primitive values and other DTOs. All API messages can be composed of these, allowing for constant strictness and ease-of-use for all internal classes. These DTOs manage their own conversion to- and from JSON-encoded text using the centralised JSON Mapper (composed of generated code thanks to Google's `json_serializable` library).

- **Internal Data Managers** - While the endpoint controllers represent strict 1:1 versions of API endpoints, the internal managers offer developer-friendly methods, state flags and information caches, masking the complexities of dealing with disassociated API endpoints. As part of this proess, a manager makes use of an entity's internal methods to interpret and procduce DTOs.

- **Entities** - Much like the Internal Data Managers, Entities are objects that represent significant elements in the conceptual model of the Truckin-IT system (e.g. user profiles or companies and their assets). These offer convenience methods to shortcut some manager actions, and organic linking to other related entities to once again shield developers further along the pipeline from the lack of natural connections between structures. These entities can consume existing DTOs and generate new ones for use when interacting wtih Endpoint Controllers.

- **Providers** - This layer marks the core of all decisions and behaviour in the apps. Providers collect data from Data Managers and stream information from the returned Entities to the Flutter UI; then they call upon the Managers when actions are taken in the UI, collecting the returned data and repeating the cycle. The use of a Provider ↔ View architecture is extremely favourable versus direct interaction between controllers and view elements by allowing for a singular, non-complex master layer to control all actions taken above and below it.

- **Flutter UI** - The final View layer served to the app user. This layer contains little to no logic, containing only styling and layout information. Preferably even non-static content (such as body copy or images) should be controlled by the Provider layer.

---

## Project Management Tools

### Issue Tracking
Project Management is centered in the GitLab [Issue Tracker][gitlab-mobile-issues] and [Wiki][gitlab-mobile-wiki]. The Wiki tracks and categorises user stories, while issues are created to manage the implementation of those stories' implementations and dependencies.

Each issue is linked to a Milestone (see above) and assigned a label which categorises it into a [Board][gitlab-mobile-boards] for backlog and active task tracking. Task assignment is integrated into the issue tracker, with new issues being created and assigned at the start of each sprint (Thursday to Thursday).

### Branch & Commit Control
The popular [GitFlow](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow) branch-control system has been adopted along with a some parts of the [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0-beta.2/) commit-naming standard. Branch protection rules and strict naming standards have been configured on the [active GitLab repository](https://gitlab.com/team-enigma/mobile/) as described below (rules are not on the GitHub mirror repository).

**GitFlow** adoption was straight-forward.
- The `master` branch may only be updated via reviewed merge requests from `development`. All automated unit- and integration tests in the pipeline are required to pass before commits can be accepted.
- The `development` branch may only be updated via merge requests from `feature/fix-*` branches. Pipeline tests are run for each commit but are not required to pass as dependencies or unit tests may still need implementation.
- Feature branches, named `feature-<description>` are the only branches in which active changes are allowed. Developers may update and break these branches as they wish during development, then initiate a merge request into the `development` branch once they are satisfied with the feature and its unit tests.

**Conventional Commits** was used as a naming guideline with several adaptions for GitLab features and some simplifications.\
_Note that GitLab automatically links commits to issues when an issue number is referenced with `#<issue no.>`_

Commit names are expected to look different on the `master`, `development` and `feature/fix-*` branches despite the use of a global matcher.

  - `master`: Version number with optional description

    Regexp: `v\d+.\d+(\n\n(\n\n|.)*)?`

    Commits must start with `vX.X`, each `X` representing a digit. Thereafter body text is allowed in one or more new paragraphs to allow for a detailed commit description away from the above title.

  - `development`: Target feature with optional issue link

    Regexp: `(feature|fix)-[a-z-]+ \((Closes )?#\d+\)`

    Commits must name the feature branch being merged, and have the option to specify the isue this feature is linked to in brackets, further optionally marking that issue for closure upon merge acceptance.\
    The following commit history is valid (top is latest):
    ```
    + feature-register-errorhandling (Closes #4)
    |
    + feature-register (#4)
    |
    + feature-login
    ```

  - `feature/fix-*`: Conventional Commit prefix with optional issue, plus description

    Regexp: `(feat|fix|test|config)(\(#\d+\))?: (.+)((\n\n|.)+)`

    Simplified Pattern: `<prefix>(#<issue>): <description>`

    Commits must use one of our descriptive prefixes (below), can optionally contain a linked issue in brackets, and should have a short title (plus optionally a longer commit description in a new paragraph).

    Prefixes:
    + `feat` - a newly implemented feature or functionality
    + `fix` - a fix to a broken or buggy feature or functionality
    + `test` - the creation of a new unit test
    + `config` - housekeeping and other non-programming tasks such as writing documentation, updating dependency versions, or changing configuration files

[gitlab-mobile-wiki]: https://gitlab.com/team-enigma/mobile/-/wiki "Mobile Wiki"
[gitlab-mobile-issues]: https://gitlab.com/team-enigma/mobile/-/issues "Mobile Issues"
[gitlab-mobile-boards]: https://gitlab.com/team-enigma/mobile/-/boards "Mobile Issues"
[gitlab-api-home]: https://gitlab.com/team-enigma/api/ "Truckin-IT API"