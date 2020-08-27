# Details

### Project

Using a Game Controller as a Navigation Aid

### Student

Divyanshu Mahajan

### Mentor

Tony Atkins

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
    <i>Apart from the satisfaction that came with passing the evaluation</i> 😌, <i>I became happier after reading
    these notes</i> ❤️<br>
    <i>I feel blessed and privileged having this opportunity to work under the mentorship of Tony</i> 🙌✨
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

---

## Week Seven

### Time Period

13 July - 19 July

### Weekly Check-in

- In this week's check-in, we discussed the remaining features for the project and the order we want them to be
completed.
- We also talked about adding some other features apart from those specified in the proposal, such as zoom in/out
  ([#29](https://github.com/fluid-lab/gamepad-navigator/issues/29)), maximize/restore browser windows
  ([#28](https://github.com/fluid-lab/gamepad-navigator/issues/28)), reopening closed tabs
  ([#24](https://github.com/fluid-lab/gamepad-navigator/issues/24)), et cetera.
- My mentor suggested completing the configuration panel first. Still, I shared that the inter-navigation features such
  as opening and closing new windows and switching them would be easy to implement. So we decided to complete those
  first.

### Tasks Completed

- [PR #25](https://github.com/fluid-lab/gamepad-navigator/pull/25): Added the ability to switch browser tabs in both
  forward and backward directions using gamepad buttons.
- [PR #31](https://github.com/fluid-lab/gamepad-navigator/pull/31): Added documentation for `gamepad.navigator`
  component.
- [PR #33](https://github.com/fluid-lab/gamepad-navigator/pull/33): Added feature to open and close browser windows
  using the gamepad.
- [PR #36](https://github.com/fluid-lab/gamepad-navigator/pull/36): Added feature to switch browser windows in forward
  and reverse direction using the gamepad. Also fixed the issue
  [#34](https://github.com/fluid-lab/gamepad-navigator/issues/34) where non-active tabs and windows were reading the
  gamepad inputs.

---

## Week Eight | End of Phase Two

### Time Period

20 July - 26 July

### Weekly Check-in

- In this week's check-in, we discussed about the changes to the configuration panel that I prepared before the
  check-in.
- My mentor suggested making the SVG buttons/triggers/axes clickable for the user to navigate directly to the input's
  configuration menu instead of tabbing to it. I added that we could use a list instead to make things easier and to
  save time working on other issues, and we both agreed with it.
- He also suggested displaying the extra options such as Speed Factor, Invert Axes, et cetera, if it's relevant to the
  action. Additionally, adding a description of the gamepad input would be suitable instead of merely showing the
  gamepad input index.
- Another point we discussed was adding a Set All to None button, which could be used by the user to set only one or
  more controls on the gamepad. He also suggested disabling the Save Changes button if the user does not change the
  configuration.
- Apart from the above, we talked about adding another button named Restore Default Controls for restoring the default
  configuration of the gamepad controls.

### Tasks Completed

- [PR #37](https://github.com/fluid-lab/gamepad-navigator/pull/37): Added configuration panel with all the features and
  suggestions, as discussed above.

---
 
## Week Nine | Second Evaluation

### Time Period

27 July - 2 August

### Weekly Check-in

- In the weekly check-in, we discussed the project plan and rearranged a few milestones to be completed before the
  design crit.
- We also talked about the structure of the configuration panel and decided that we should refactor it and split it into
  two separate pull requests addressing the following:
  - Changing the selectors to use `viewComponent` selectors.
  - Using `fluid.binder` to attach our component's model to the DOM input elements' data.
- We also discussed in brief about the design crit where I'll present my work to the community. My mentor said that
  it'd be around 5th or 12th August at 7:30 pm.

### Tasks Completed

- [PR #39](https://github.com/fluid-lab/gamepad-navigator/pull/37): Added the "Discard Changes" button to the
  configuration panel with the mechanism to store unsaved changes.
- [PR #42](https://github.com/fluid-lab/gamepad-navigator/pull/42): Added feature to zoom in/out using gamepad buttons,
  axes, and thumbsticks.
- [PR #43](https://github.com/fluid-lab/gamepad-navigator/pull/43): Added feature to maximize/restore windows using the
  gamepad.
- [PR #46](https://github.com/fluid-lab/gamepad-navigator/pull/46): Added feature to reopen closed tabs/windows using
  the gamepad.
- [PR #47](https://github.com/fluid-lab/gamepad-navigator/pull/47): Fixed monitor switching issues with maximize/restore
  windows (on macOS X).
- [PR #48](https://github.com/fluid-lab/gamepad-navigator/pull/48): Added list to switch between different inputs'
  configuration menu and polished the UI of the configuration panel.
- [PR #49](https://github.com/fluid-lab/gamepad-navigator/pull/49): Added documentation for configMaps grade.
  
---

## Second Evaluation Results

<p align="center">
  <img src="https://i.imgur.com/3gv2HWr.png" />
  <p align="center">
    <i>Glad we made it!</i> 🙏✨
  </p>
</p>

---

## Week Ten | Beginning of Phase Three

### Time Period

3 August - 9 August

### Weekly Check-in

- In the weekly check-in, we discussed the upcoming design crit on 11th August 2020, where I’ll be presenting my work to the
  community members.
- The crit would also involve taking feedback from the community members for feature additions, improvements in the current
  implementation, and creating tickets based on those points.
- My mentor advised that I record a video demonstrating the extension's functionality instead of a live demo to avoid any
  technical issues in between.
- He also guided me on the presentation style and the preparations that I should make beforehand.

### Tasks Completed

- [PR #51](https://github.com/fluid-lab/gamepad-navigator/pull/51): Added documentation for inputMapper.base component.
- [PR #52](https://github.com/fluid-lab/gamepad-navigator/pull/52): Updated the documentation of `navigator` component.
- Updated [PR #47](https://github.com/fluid-lab/gamepad-navigator/pull/47),
  [PR #48](https://github.com/fluid-lab/gamepad-navigator/pull/48), and
  [PR #49](https://github.com/fluid-lab/gamepad-navigator/pull/49) as per the feedback recieved from my mentor.

---

## Week Eleven

### Time Period

10 August - 16 August

### Weekly Check-in

- We had multiple check-ins this week. The first one took a day before the design crit.
- I shared the presentation slides with my mentor that I prepared for the crit, and he suggested some changes to make it
  better.
- He briefed me about the structure of the design crit and the sequence that will be followed.
- My mentor suggested me to keep the demo video not more than 10 minutes. I added that the playtime was exceeding the
  range owing to the number of features we have. To this, he suggested that I can show one of the pair features to reduce
  the playtime.
- The second check-in took on the day after the design crit. I shared that my college will be opening on 19th August 2020,
  so I would have less time to work on the project after that. My mentor suggested to complete the documentation and then
  frame approaches to trigger the event hooks.
- We mutually agreed that I'd complete the remaining work (tests, long-term goals, et cetera) after the program ends.
- Owing to the time we have before the college opens, he suggested that we should check-in next week if necessary.

### Tasks Completed

- [PR #54](https://github.com/fluid-lab/gamepad-navigator/pull/54): Added documentation for the `inputMapper` component
  and updated the `visibilityChangeTracker` function to allow passing custom configuration options.
- [PR #55](https://github.com/fluid-lab/gamepad-navigator/pull/55): Added documentation for the `messageListener`
  component.
- [PR #56](https://github.com/fluid-lab/gamepad-navigator/pull/56): Added documentation for the `configurationPanel`
  component.
- [PR #57](https://github.com/fluid-lab/gamepad-navigator/pull/57): Added the list of actions, default controls, and
  reference to the demo video link to README.
- Started looking into approaches to simulate the gamepad for testing using the
  [Selenium WebDriver](https://www.selenium.dev/selenium/docs/api/java/org/openqa/selenium/WebDriver.html).
- Started working on different approaches to trigger event hooks.

---

## Week Twelve | End of Phase Three

### Time Period

17 August - 23 August

### Weekly Check-in

- We didn't check-in this week because of the time constraints. But there were a few things we discussed during our
  chat.
- The first thing was finding an icon for the extension.
- The other thing we talked about was publishing the extension to the Chrome Web Store. My mentor suggested that I
  should frame the steps to publish the extension in brief.

### Tasks Completed

- Looked into various web sites for icons that we can use for the extension. Since all of those had some kind of
  attribution terms associated with themselves, I created a custom icon myself.
- [PR #63](https://github.com/fluid-lab/gamepad-navigator/pull/63): Added the extension icon and steps to publish
  the extension.
- Updated [PR #56](https://github.com/fluid-lab/gamepad-navigator/pull/56) and
  [PR #57](https://github.com/fluid-lab/gamepad-navigator/pull/57) as per the feedback recieved from my mentor.

---

## Week Thirteen | Wrap-up | Final Evaluation

### Time Period

24 August - 31 August

### Tasks Completed

- Updated [PR #63](https://github.com/fluid-lab/gamepad-navigator/pull/63) by adding multiple Grunt tasks for
  automating the process of creating a release on GitHub. The first grunt tasks creates a zip file, the second task
  updates the `version` in the `manifest.json` and `package.json` files, and the third task creates a release on GitHub.
- Searched and looked for approaches to trigger event hooks.
