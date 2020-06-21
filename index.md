# Details

**Project:** Using a Game Controller as a Navigation Aid<br>
**Student:** Divyanshu Mahajan<br>
**Mentors:** Tony Atkins, Colin Clark

# Community Bonding Period

### Time Period

May 4 - May 31 (4 weeks)

### Learnings and Work Done

- Studied [jqUnit](https://docs.fluidproject.org/infusion/development/jqUnit.html), [Infusion View API](https://docs.fluidproject.org/infusion/development/ViewAPI.html), and [Context Awareness API](https://docs.fluidproject.org/infusion/development/ContextAwareness.html) as my mentor suggested.
- Made changes to the Infusion-based [Gamepad Prototype](https://github.com/dmahajan980/gamepad-prototype-using-infusion) as per the discussions with my mentor.
- Worked on the Infusion's improvement ticket - [FLUID-6500](https://github.com/fluid-project/infusion/pull/992).
- Observed and learned about the Fluid Community's workflows and practices.

# Coding Period

## Week One

### Time Period

June 1 - June 7

### Weekly Check-in

- We discussed about the various candidate technnologies that I shortlisted for the project and some queries related to those.
- We decided that I'll spend the current week learning and trying out both the technologies and observe their usage patterns to make an informed choice of the final candidate.

### Tasks Completed

- [PR #4](https://github.com/fluid-lab/gamepad-navigator/pull/4): Prepared a document for candidate technologies that can be used and narrowed the list down to Chrome Extension and Electron App.
- [PR #5](https://github.com/fluid-lab/gamepad-navigator/pull/5): Created the initial skeleton for the project repository. Read the documentation of [Grunt](https://gruntjs.com/) and [ESLint](https://eslint.org/) for setting up the configuration.
- Tested the [Gamepad API Vibration](https://www.chromestatus.com/feature/5705158763741184) and studied the various [Chrome Extension APIs](https://developer.chrome.com/extensions/api_index). I wrote some sample extensions alongside and also started exploring [Electron.js](https://www.electronjs.org/) and [Robot.js](https://robotjs.io/).
- Investigated and discussed approaches with the Fluid Community members about using Infusion's npm package inside a Chrome Extension. After deliberation, I came down to the approach used in the [UIO+ Chrome Extension](https://github.com/fluid-project/uio-plus) for the same.

---
 
## Week Two

### Time Period

June 8 - June 14

### Weekly Check-in

- In the previous weekly check-in, we decided that I'll learn and try out both the technologies I proposed. So, we discussed about my review of the two candidates, their benefits, and limitations apart from the ones already mentioned in the document.
- We decided that I'll prepare a written analysis of the two technologies to choose the final candidate and after that, we'll work on the project plan.

### Tasks Completed

- [PR #6](https://github.com/fluid-lab/gamepad-navigator/pull/6): Configured [Grunt Banner](https://www.npmjs.com/package/grunt-banner) plugin to add license/copyright boilerplate at the top of relevant files and restructured license and copyright-related files as per the Fluid Community's conventions. Studied RegExp for configuring the plugin to find the existing banner and replace with the newer ones.
- Made changes to the [PR #5](https://github.com/fluid-lab/gamepad-navigator/pull/5) as suggested by the mentor.
- Completed studying and reviewing [Electron.js](https://www.electronjs.org/) and [Robot.js](https://robotjs.io/). For the analysis of the candidates, I implemented a [demo app](https://github.com/dmahajan980/electron-robot-demo) which uses Gamepad API to take inputs from a gamepad and process them into OS level actions.
- Prepared the analysis for the two shortlisted candidates - Electron App and Chrome Extension and finalized the Chrome Extension for the project with my mentor.<br>
  _(Updated in [PR #4](https://github.com/fluid-lab/gamepad-navigator/pull/4))_

---
 
## Week Three

### Time Period

June 15 - June 21

### Weekly Check-in

- In this check-in, we discussed and decided upon the project plan and rearranged the project milestones and deliverables that I mentioned in my proposal. We also decided that I should complete intra-navigation features first and by the end of the first evaluation.
- We talked about the possible ways and techniques to test our work, such as testing whether chrome extension loads in the browser, simulating gamepad inputs, et cetera. We believe that we need to investigate the testing tools and techniques further so that the work can be tested extensively.
- We decided that I should add tests and support for continuous integration into the project by the end of the second phase.
- One of the features we should include in the project is the flexibility to re-map controls. My mentor was curious to know if we can overcome the dependency on the keyboard and mouse for the same, and we decided that I'll come up with an approach for the same.


### Tasks Completed

- [PR #8](https://github.com/fluid-lab/gamepad-navigator/pull/8): Added [grunt-contrib-copy](https://www.npmjs.com/package/grunt-contrib-copy) and [grunt-contrib-clean](https://www.npmjs.com/package/grunt-contrib-clean) for clearing and copying the unpacked extension files and wrote an infusion component to read inputs from the gamepad.
- Modified the above pull request to have the co-piloting feature, similar to the ["co-pilot mode" in Xbox One](https://www.youtube.com/watch?v=Ib9nL8qTbX0&list=PLUvQt4_vdB-hK8BI5CZr5XQjD3cFH4hYd) and other changes, as suggested by my mentor.
- Investigated ways to simulate keypresses and agreed upon, with my mentor, that we might have to use custom synthetic events for navigation.
- Looked into methods by which we can tab across elements. For the purpose, we had the [jQuery UI focusable selector](https://api.jqueryui.com/focusable-selector/), which lacked support for certain DOM elements. So I modified the function definition and added support for more DOM elements.
- Moreover, the selector returns the items according to the flow of the webpage and not in order of their tabindex. So I added an extra layer of sorting to return the elements in that particular order.
- Another concern that needs to be addressed was closing the modals and alert dialogs. I researched and found that there's no way to do so using JavaScript. But I made a list of few workarounds we can use:
  - Using the Chrome Extension's [Notification API](https://developer.chrome.com/extensions/notifications) for notifying users about the alert and clearing the standard alert method's definition.
  - Replacing the alert method's definition to display a custom on-screen dialog box or the standard [jQuery UI dialog](https://jqueryui.com/dialog/#modal-confirmation).
- Implemented the vertical and horizontal scroll feature. Also implemented scrolling for the standard directions (up, down, left, right) so that the user can scroll using buttons as well.<br>
  (_PR to be sent after the [PR #8](https://github.com/fluid-lab/gamepad-navigator/pull/8) is merged, to avoid merge conflicts)_
- Started investigating ways to simulate gamepad input for testing purposes.
  
