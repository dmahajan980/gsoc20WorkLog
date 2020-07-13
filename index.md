# Details

### Project

Using a Game Controller as a Navigation Aid

### Student

Divyanshu Mahajan

### Mentors

Tony Atkins, Colin Clark

# Community Bonding Period

### Time Period

4 May - 31 May (4 weeks)

### Learnings and Work Done

- Studied [jqUnit](https://docs.fluidproject.org/infusion/development/jqUnit.html),
  [Infusion View API](https://docs.fluidproject.org/infusion/development/ViewAPI.html), and
  [Context Awareness API](https://docs.fluidproject.org/infusion/development/ContextAwareness.html) as my mentor
  suggested.
- Made changes to the Infusion-based
  [Gamepad Prototype](https://github.com/dmahajan980/gamepad-prototype-using-infusion) as per the discussions with my
  mentor.
- Worked on the Infusion's improvement ticket - [FLUID-6500](https://github.com/fluid-project/infusion/pull/992).
- Observed and learned about the Fluid Community's workflows and practices.

# Coding Period

## Week One | Beginning of Phase One

### Time Period

1 June - 7 June

### Weekly Check-in

- We discussed about the various candidate technnologies that I shortlisted for the project and some queries related to
  those.
- We decided that I'll spend the current week learning and trying out both the technologies and observe their usage
  patterns to make an informed choice of the final candidate.

### Tasks Completed

- [PR #4](https://github.com/fluid-lab/gamepad-navigator/pull/4): Prepared a document for candidate technologies that
  can be used and narrowed the list down to Chrome Extension and Electron App.
- [PR #5](https://github.com/fluid-lab/gamepad-navigator/pull/5): Created the initial skeleton for the project
  repository. Read the documentation of [Grunt](https://gruntjs.com/) and [ESLint](https://eslint.org/) for setting up
  the configuration.
- Tested the [Gamepad API Vibration](https://www.chromestatus.com/feature/5705158763741184) and studied the various
  [Chrome Extension APIs](https://developer.chrome.com/extensions/api_index). I wrote some sample extensions alongside
  and also started exploring [Electron.js](https://www.electronjs.org/) and [Robot.js](https://robotjs.io/).
- Investigated and discussed approaches with the Fluid Community members about using Infusion's npm package inside a
  Chrome Extension. After deliberation, I came down to the approach used in the
  [UIO+ Chrome Extension](https://github.com/fluid-project/uio-plus) for the same.

---
 
## Week Two

### Time Period

8 June - 14 June

### Weekly Check-in

- In the previous weekly check-in, we decided that I'll learn and try out both the technologies I proposed. So, we
  discussed about my review of the two candidates, their benefits, and limitations apart from what was already
  mentioned in the document.
- We decided that I'll prepare a written analysis of the two technologies to choose the final candidate and after that,
  we'll work on the project plan.

### Tasks Completed

- [PR #6](https://github.com/fluid-lab/gamepad-navigator/pull/6): Configured
  [Grunt Banner](https://www.npmjs.com/package/grunt-banner) plugin to add license/copyright boilerplate at the top of
  relevant files and restructured license and copyright-related files as per the Fluid Community's conventions. Studied
  RegExp for configuring the plugin to find the existing banner and replace with the newer ones.
- Made changes to the [PR #5](https://github.com/fluid-lab/gamepad-navigator/pull/5) as suggested by the mentor.
- Completed studying and reviewing [Electron.js](https://www.electronjs.org/) and [Robot.js](https://robotjs.io/). For
  the analysis of the candidates, I implemented a [demo app](https://github.com/dmahajan980/electron-robot-demo) which
  uses Gamepad API to take inputs from a gamepad and process them into OS level actions.
- Prepared the analysis for the two shortlisted candidates - Electron App and Chrome Extension and finalized the Chrome
  Extension for the project with my mentor.<br>
  _(Updated in [PR #4](https://github.com/fluid-lab/gamepad-navigator/pull/4))_

---
 
## Week Three

### Time Period

15 June - 21 June

### Weekly Check-in

- In this check-in, we discussed and decided upon the project plan and rearranged the project milestones and
  deliverables that I mentioned in my proposal. We also decided that I should complete intra-navigation features first
  and by the end of the first evaluation.
- We talked about the possible ways and techniques to test our work, such as testing whether chrome extension loads in
  the browser, simulating gamepad inputs, et cetera. We believe that we need to investigate the testing tools and
  techniques further so that the work can be tested extensively.
- We decided that I should add tests and support for continuous integration into the project by the end of the second
  phase.
- One of the features we should include in the project is the flexibility to re-map controls. My mentor was curious to
  know if we can overcome the dependency on the keyboard and mouse for the same, and we decided that I'll come up with
  an approach for the same.


### Tasks Completed

- [PR #8](https://github.com/fluid-lab/gamepad-navigator/pull/8): Added
  [grunt-contrib-copy](https://www.npmjs.com/package/grunt-contrib-copy) and
  [grunt-contrib-clean](https://www.npmjs.com/package/grunt-contrib-clean) for clearing and copying the unpacked
  extension files and wrote an infusion component to read inputs from the gamepad.
- Modified the above pull request to have the co-piloting feature, similar to the
  ["co-pilot mode" in Xbox One](https://www.youtube.com/watch?v=Ib9nL8qTbX0&list=PLUvQt4_vdB-hK8BI5CZr5XQjD3cFH4hYd)
  and other changes, as suggested by my mentor.
- Investigated ways to simulate keypresses and agreed upon, with my mentor, that we might have to use custom synthetic
  events for navigation.
- Looked into methods by which we can tab across elements. For the purpose, we had the
  [jQuery UI focusable selector](https://api.jqueryui.com/focusable-selector/) and the
  [jQuery UI tabbable selector](https://api.jqueryui.com/tabbable-selector/), but these lacked support for certain DOM
  elements. So I modified the function definition and added support for more DOM elements.
- Moreover, the selector returns the items according to the flow of the webpage and not in order of their tabindex. So
  I added an extra layer of sorting to return the elements in that particular order.
- Investigated ways to simulate gamepad input for testing purposes but couldn't find anything that suits to our needs.
  The only possible way is by passing a mock of the Gamepad API.
- Another concern that needs to be addressed was closing the modals and alert dialogs. I researched and found that
  there's no way to do so using JavaScript. But I made a list of few workarounds we can use:
  - Using the Chrome Extension's [Notification API](https://developer.chrome.com/extensions/notifications) for
    notifying users about the alert and clearing the standard alert method's definition.
  - Replacing the alert method's definition to display a custom on-screen dialog box or the standard
    [jQuery UI dialog](https://jqueryui.com/dialog/#modal-confirmation).
- Implemented the vertical and horizontal scroll feature. Also implemented scrolling for the standard directions (up,
  down, left, right) so that the user can scroll using buttons as well.<br>
  (_PR to be sent after the [PR #8](https://github.com/fluid-lab/gamepad-navigator/pull/8) is merged, to avoid merge
  conflicts)_

---
 
## Week Four | End of Phase One

### Time Period

22 June - 28 June

### Weekly Check-in

- In this week's check in, we decided that we should focus on the tab navigation functionality and tests related to it.
- We talked about the absence of jQuery UI [focusable](https://api.jqueryui.com/focusable-selector/) and the
  [tabbable](https://api.jqueryui.com/tabbable-selector/) pseudo-selectors inside Infusion, which would be used for our
  project. To resolve the issue, my mentor opened the [FLUID-6522](https://issues.fluidproject.org/browse/FLUID-6522)
  for me to work on.
- My mentor suggested me to use `tabbable` instead of the `focusable` pseudo-selector for the tab navigation.
- I shared that we can't have a gamepad simulator for testing purposes. So we decided that we'll use a gamepad-mock
  based approach for the tests to work.
- I also shared that we can't manipulate the alert dialog boxes using JavaScript and would probably have to modify the
  system definition to use custom UI alert boxes. One suggestion that I had was to use
  [Chrome's Notification API](https://developer.chrome.com/extensions/notifications) or the
  [jQuery UI Dialog](https://jqueryui.com/dialog/) for replacing the original modal definition. But my mentor suggested
  to work on it after we are done with the UI of the Chrome Extension (in third phase).

### Tasks Completed

- [PR #9](https://github.com/fluid-lab/gamepad-navigator/pull/9): Added horizontal and vertical scroll for
  intra-webpage navigation. Along with this, I added the configrable options inside maps which can be used for every
  navigation action we build.
- [PR #10](https://github.com/fluid-lab/gamepad-navigator/pull/10): Added tabbing and reverse tabbing for intra-webpage
  navigation (using [ally.js](https://allyjs.io/)). Along with it, some TODOs were added and bugs were fixed related to
  the previous pull requests.
- [FLUID-6522](https://github.com/fluid-project/infusion/pull/997): Added jQuery UI
  [focusable](https://api.jqueryui.com/focusable-selector/) and the
  [tabbable](https://api.jqueryui.com/tabbable-selector/) pseudo-selectors. The pull request was later withdrawn as we
  discovered [ally.js](https://allyjs.io/) which is better and worked well with Chrome.
- Made changes to the [PR #8](https://github.com/fluid-lab/gamepad-navigator/pull/8) as suggested by my mentor.
- Investigated various ways, strategies, libraries, and frameworks which can be used to test out Chrome extension. I
  discussed this with my mentor and we decided that we might have to use multiple testing libraries and frameworks as
  per the requirements and the design of our Chrome Extension.
- Wrote some basic tests for scroll navigation -
  [Commit](https://github.com/dmahajan980/gamepad-navigator/commit/7656024df3b65685927a24856738a12004f654ed) and made
  slight modifications to the components in my previous commits.<br>
  (_PR to be sent later_)

---
 
## Week Five | First Evaluation

### Time Period

29 June - 5 July

### Weekly Check-in

- In this week's check-in, we discussed the testing patterns and strategies that we use in our tests.
- My mentor briefed me about a few concerns about the codebase parts that might produce an error while writing tests
  and discussed ways to rectify them.
- We also talked about the current testing pattern that I used in my first test fixture, and my mentor suggested some
  changes in that test fixture and to be followed in every other test fixture.

### Tasks Completed

- [PR #12](https://github.com/fluid-lab/gamepad-navigator/pull/12): Added tests for horizontal and vertical scrolling.
- [PR #13](https://github.com/fluid-lab/gamepad-navigator/pull/13): Added tests for tab navigation.
- [PR #16](https://github.com/fluid-lab/gamepad-navigator/pull/16): Added click feature for webpage clicks using the
  gamepad and also added some tests.
- [PR #17](https://github.com/fluid-lab/gamepad-navigator/pull/17) and
  [PR #18](https://github.com/fluid-lab/gamepad-navigator/pull/18): Updated scroll and tab navigation tests to follow
  the same pattern used in the click tests.
  
---

## First Evaluation Results

<p align="center">
  <img src="https://i.imgur.com/uPubqlO.png" />
  <p align="center">
    <i>
      Apart from the satisfaction that came with passing the evaluation :relieved:, I became happier after reading these
      notes :sparkling_heart:<br>
      Having a mentor like mine is truly a blessing :raised_hands::sparkles:
    </i>
  </p>
</p>

---

## Week Six | Beginning of Phase Two

### Time Period

6 July - 12 July

### Weekly Check-in

- In this week's check-in, we discussed about adding GitHub Actions to the project's repository since we already had
  some basic tests.
- We talked about the project plan and decided that we should proceed with the history navigation where the focus before
  the user navigated some other page should be restored, after the user navigates back to the same page in history.
- We also decided that we'll go for the integration tests in the Phase 3 when we are done with the configuration panel
  and may skip the browser tab navigation, if needed. The important parts to be implemented are the history navigation,
  page refresh, and the back button.
- My mentor also talked about the Design Crit where I'll present my work to the community members and obtain their
  feedback. Their suggestions will be considered to improve the funcionality of the gamepad navigator.

### Tasks Completed

- [PR #19](https://github.com/fluid-lab/gamepad-navigator/pull/19): Added feature for forward and backward history
  navigation.
- [PR #21](https://github.com/fluid-lab/gamepad-navigator/pull/21): Added feature to open and close tabs.
- Started working on the forward and backward browser tab navigation and the single-press tab navigation.
