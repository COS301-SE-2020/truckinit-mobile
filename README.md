# Truckin-IT Mobile Applications
_A centralised collection of the three Truckin-IT mobile apps_

This repository contains the three mobile apps for the Truckin-IT system. Each app is composed primarily of shared components located on the 'common' package.

## Team Enigma
This project is a product by team Enigma for the "COS301 - Software Engineering" (University of Pretoria) 2020 Capstone Project Assignment.
- For more information about the team, [check out our website][enigma-website]!
- For our other related project modules, see the following:
  - API server ([gitlab](https://gitlab.com/team-enigma/api/), [github](https://github.com/COS301-SE-2020/truckinit-api))
  - Cluster Deployment ([gitlab](https://gitlab.com/team-enigma/deploy/), [github](https://github.com/COS301-SE-2020/truckinit-deploy))

## App Installation
_For a more detailed guide, see our [User Manual][enigma-usermanual-doc]_

Installation of the apps requires use of an Android device.
1. View the links for each mobile app below
2. Select the app of choice (Fleet Manager, Customer or Trucker)
3. Download the application package (.apk) to your Android device
4. Ensure app side-loading is enable in your device settings
5. Run the package, which will install the apo on your device immediately

You are welcome to install any or all of our apps
- Fleet Manager App ([app store link][fleet-manager-app])
- Customer App ([app store link][customer-app])
- Trucker App ([app store link][trucker-app])

## Setup
_NB: A Google Developer account is required for map functionality (using their location API)._

<details>

<summary>Setting up Flutter (click to expand)</summary>

> \* Note: If you are not already familiar with Flutter basics, please take a look at their [starter guide](https://flutter.dev/docs/get-started/codelab)
>
> 1. Install [Flutter 1.17.3](https://flutter.dev/docs/development/tools/sdk/releases) for build and run ([guide](https://flutter.dev/docs/get-started/install))
> 2. If you want to run unit tests or isolate controller classes, install the [Dart SDK](https://dart.dev/get-dart)
> 3. Android: [Enable USB debugging](https://www.embarcadero.com/starthere/xe5/mobdevsetup/android/en/enabling_usb_debugging_on_an_android_device.html) on your
>    device or [install an emulator](https://developers.arcgis.com/android/10-2/sample-code/emulator/)\
>    iOS: You will need XCode and an Apple developer license to run [on a device](https://developer.apple.com/library/archive/documentation/ToolsLanguages/Conceptual/Xcode_Overview/RunningonaDevice.html#//apple_ref/doc/uid/TP40010215-CH55-SW1)
>    or [in the simulator](https://developer.apple.com/library/archive/documentation/ToolsLanguages/Conceptual/Xcode_Overview/RunningintheSimulator.html#//apple_ref/doc/uid/TP40010215-CH54-SW1)
> 4. You can do Flutter dev with most popular IDEs. We like using [VSCode](https://code.visualstudio.com/) ([Flutter guide](https://flutter.dev/docs/get-started/test-drive?tab=vscode)),
>    which is nothing like [Visual Studio IDE](https://devrant.com/rants/2066988/after-wasting-most-of-the-afternoon-trying-to-fix-visual-studio-i-can-honestly-s)

</details>

1. Clone this repository (see Clone button above)
2. Download the Google Services configuration files for Android and iOS as needed\*
3. Copy the Android file to `android/app/`, and the iOS file to `ios/Runner`.
4. Run `common\core\tools\build` before first use to perform code generation.

\* From the [Firebase Console](https://console.firebase.google.com/u/0/project/_/settings/general), select the target project and download `google_services.json` (Android) and `GoogleService-Info.plist` (iOS).

## Documentation
While this README serves as a guideline, our official workflow, goals and user guides are viewable with the below official documents:

- **Requirement Specifications** ([link][enigma-srs-doc-latest]): Information on our functional requirements, quality standards, architectural goals and application use cases can all be found in our [Software Requirement Specification (SRS)][enigma-srs-doc-latest]*. The contents of this document will be updated continuously during the development process as new factors and goals come to light.

- **Coding Standards** ([link][enigma-api-standards-doc]): Workflow rules and implementation standards have been defined in our Coding Standards Documents for the [mobile][enigma-mobile-standards-doc] and [API][enigma-api-standards-doc] teams. These documents are varied slightly to avoid unwanted or unnecessary standards for specific environments.

- **Testing Policy** ([link][enigma-testing-policy-doc]): Internal rules followed by team members for writing and executing unit- and integration-tests are defined in our [Testing Policy][enigma-testing-policy-doc], as well as the technologies we use and the reasons we use them.

- **User Manual** ([link][enigma-usermanual-doc]): High-level information on the Truckin-IT system and user-friendly guides for each mobile app can be found in our [User Manual][enigma-usermanual-doc]. User guides will only represent currently implemented functionality, and as such may not fully reflect the contents of the SRS document above.

- **Technical Installation Manual** ([link][enigma-techinstallmanual-doc]): Our [Technical Installation Manual][enigma-techinstallmanual-doc] is a concise guide on configuring the necessary development and production environments for this project, as well as a technical approach to installing the mobile applications.

User stories are viewable in the [Wiki][gitlab-mobile-wiki]. In the name of brevity, all points have been limited to a short title and user story with no implementational or motivational detail. For detailed discussion of features please use the SRS Document.


\* Note: the above SRS Document is the latest version. See our version history below
- v1 ([link][enigma-srs-doc])
- v2 ([link][enigma-srs-doc2])
- v3 ([link][enigma-srs-doc3])
- v4 ([link][enigma-srs-doc4])


## Our Team
For more about us, [check out our website!](https://enigmasoftware.co.za/)

<table>
<tr>
  <td>
  <img alt="Daneel" src="https://enigmasoftware.co.za/img/daneel/daneel.jpeg" width="150pt">
  </td>
  <td>
    <h3>Daneel Nortier</h3>
    <p><em>Machine Learning and Optimisation</em></p>
    <p>(<a href="https://enigmasoftware.co.za/profiles/daneel">see profile</a>)</p>
  </td>
</tr>

<tr>
  <td>
  <img alt="Francois" src="https://enigmasoftware.co.za/img/francois/francois.jpg" width="150pt">
  </td>
  <td>
    <h3>Francois Snyman</h3>
    <p><em>Mobile & Web Development</em></p>
    <p>(<a href="https://enigmasoftware.co.za/profiles/francois">see profile</a>)</p>
  </td>
</tr>

<tr>
  <td>
  <img alt="Malick" src="https://enigmasoftware.co.za/img/malick/malick.png" width="150pt">
  <td>
    <h3>Malick Burger</h3>
    <p><em>Systems Administration and Deployment</em></p>
    <p>(<a href="https://enigmasoftware.co.za/profiles/malick">see profile</a>)</p>
  </td>
  </td>
</tr>

<tr>
  <td>
  <img alt="Preston" src="https://enigmasoftware.co.za/img/preston/profile.png" width="150pt">
  </td>
  <td>
    <h3>Preston van Tonder</h3>
    <p><em>API Design and DevOps</em></p>
    <p>(<a href="https://enigmasoftware.co.za/profiles/preston">see profile</a>)</p>
  </td>
</tr>

<tr>
  <td>
  <img alt="Xander" src="https://enigmasoftware.co.za/img/xander/xander.jpg" width="150pt">
  </td>
  <td>
    <h3>Xander Terblanche</h3>
    <p><em>UI/UX and Mobile Development</em></p>
    <p>(<a href="https://enigmasoftware.co.za/profiles/xander">see profile</a>)</p>
  </td>
</tr>
</table>


## Milestones

- **Capstone Demo 1** (12/06/2020)\
  _Initial Git management, CI/CD, documentation, and basic feature implementation_\
  **Demo Video** ([link][demo-1-vid])

+ **Capstone Demo 2** (23/07/2020)\
  _Updated SRS with architecture and quality requirements, user manual and continued implementation_\
  **Demo Video** ([link][demo-2-vid])

- **Capstone Demo 3** (20/08/2020)\
  _80% feature implementation, installation manual and updated requirement documentation_\
  **Demo Video** ([link][demo-3-vid])

+ **Capstone Demo 4 & Exam Demo** (~11/09/2020)\
  _100% feature implementation, completion of all documentation, plus 1 bonus "wow" factor_\
  **Demo Video** ([link][demo-4-vid])

- **Final Evaluation & Project Day** (~05/10/2020)\
  _Requirements TBA_\
  (demo video not available)

[demo-1-vid]: https://drive.google.com/file/d/1xw0LM0fvceLCPUfsJYU96KzZ6ITmWaVL/preview "Demo 1"
[demo-2-vid]: https://drive.google.com/file/d/1TCIj4JkCUdBKWeE84fsgQrzeAmtIvK5P/preview "Demo 2"
[demo-3-vid]: https://drive.google.com/file/d/1H6bxoAPjE4ZhnfrziqzC0KH2rpzIgIK7/preview "Demo 3"
[demo-4-vid]: https://drive.google.com/file/d/1nwn7I6-P-Pb1KL1wQL-BUPIhcJyxyj1C/preview "Demo 4"

## Project Management & Workflow

#### Issue Tracking
Project Management is centered in the GitLab [Issue Tracker][gitlab-mobile-issues] and [Wiki][gitlab-mobile-wiki]. The Wiki tracks and categorises user stories, while issues are created to manage the implementation of those stories' implementations and dependencies.

Each issue is linked to a Milestone (see above) and assigned a label which categorises it into a [Board][gitlab-mobile-boards] for backlog and active task tracking. Task assignment is integrated into the issue tracker, with new issues being created and assigned at the start of each sprint (Thursday to Thursday).

#### Branch & Commit Control
The popular [GitFlow](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow) branch-control system has been adopted along with a lightweight adaption of the [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0-beta.2/) commit-naming standard. Branch protection rules and strict naming standards have been configured on the [active GitLab repository](https://gitlab.com/team-enigma/mobile/) as described below (if you are reading this on the mirrored GitHub repository will not see these rules).

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

## Implementation Standards
During the course of our development of the mobile app, we will be following a set of guidelines to control the style and structure of our libraries and classes. These standards are subject to continuous change.

### Code-Writing and -Formatting Practices
Part of the motivation for selecting Dart & Flutter as our framework for the mobile apps was that is has a strong basis of extremely detailed conventions for writing and formatting code, and performs extremely powerful optimisation during its cross-compilation. As such, all code should adhere to the [Effective Dart](https://dart.dev/guides/language/effective-dart/style) and [Flutter Formatting](https://flutter.dev/docs/development/tools/formatting) guidelines.

### Mobile Architecture

The layout of the mobile app(s)' internal libraries should respect the following system to enable pipelining of data and elimination of errors in data composition and typing (made extremely easy thanks to [Dart's optional duck-typing](https://dart.dev/guides/language/type-system)).

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


[enigma-srs-doc-latest]: https://enigmasoftware.co.za/other/docs/Software_Requirements_Specification_v4.pdf "SRS Document v4 (latest)"

[enigma-srs-doc]: https://enigmasoftware.co.za/other/docs/Software_Requirements_Specification.pdf "SRS Document"
[enigma-srs-doc2]: https://enigmasoftware.co.za/other/docs/Software_Requirements_Specification_v2.pdf "SRS Document v2"
[enigma-srs-doc3]: https://enigmasoftware.co.za/other/docs/Software_Requirements_Specification_v3.pdf "SRS Document v3"
[enigma-srs-doc4]: https://enigmasoftware.co.za/other/docs/Software_Requirements_Specification_v4.pdf "SRS Document v4"

[enigma-api-standards-doc]: https://enigmasoftware.co.za/other/docs/Coding%20Standards.pdf "API Code Standards"
[enigma-mobile-standards-doc]: https://enigmasoftware.co.za/other/docs/Coding_Standards_Mobile.pdf "Mobile Code Standards"
[enigma-usermanual-doc]: https://enigmasoftware.co.za/other/docs/User_Manual.pdf "User Manual"
[enigma-techinstallmanual-doc]: https://enigmasoftware.co.za/other/docs/Technical_Installation_Manual.pdf "Technical Installation Manual"
[enigma-testing-policy-doc]: https://enigmasoftware.co.za/other/docs/Testing_Policy.pdf "Testing Policy"

[enigma-website]: https://enigmasoftware.co.za "Team Enigma"

[gitlab-mobile-wiki]: https://gitlab.com/team-enigma/mobile/-/wiki "Mobile Wiki"
[gitlab-mobile-issues]: https://gitlab.com/team-enigma/mobile/-/issues "Mobile Issues"
[gitlab-mobile-boards]: https://gitlab.com/team-enigma/mobile/-/boards "Mobile Issues"
[gitlab-api-home]: https://gitlab.com/team-enigma/api/ "Truckin-IT API"

[fleet-manager-app]: https://gitlab.com/team-enigma/mobile/-/raw/master/App%20Downloads/fleetmanager.apk?inline=false "Fleet Manager App"
[customer-app]: https://gitlab.com/team-enigma/mobile/-/raw/master/App%20Downloads/customer.apk?inline=false "Customer App"
[trucker-app]: https://gitlab.com/team-enigma/mobile/-/raw/master/App%20Downloads/trucker.apk?inline=false "Trucker App"
