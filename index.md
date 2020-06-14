# Details

**Project:** Using a Game Controller as a Navigation Aid<br>
**Student:** Divyanshu Mahajan<br>
**Mentors:** Tony Atkins, Colin Clark

# Community Bonding Period

### Time Period

4 weeks (May 4 - May 31)

### Learnings and Word Done:

- Studied [jqUnit](https://docs.fluidproject.org/infusion/development/jqUnit.html), [Infusion View API](https://docs.fluidproject.org/infusion/development/ViewAPI.html), and [Context Awareness API](https://docs.fluidproject.org/infusion/development/ContextAwareness.html) as my mentor suggested.
- Made changes to the Infusion-based [Gamepad Prototype](https://github.com/dmahajan980/gamepad-prototype-using-infusion) as per the discussions with my mentor.
- Worked on the Infusion's improvement ticket - [FLUID-6500](https://github.com/fluid-project/infusion/pull/992).
- Observed and learned about the Fluid Community's workflows and practices.

# Coding Period

## Week One

### Time Period

1 week (June 1 - June 7)

### Weekly Check-in:

- We discussed about the various candidate technnologies that I shortlisted for the project and some queries related to those.
- We decided that I'll spend the current week learning and trying out both the technologies and observe their usage patterns to make an informed choice of the final candidate.

### Tasks Completed:

- [PR #4](https://github.com/fluid-lab/gamepad-navigator/pull/4): Prepared a document for candidate technologies that can be used and narrowed the list down to Chrome Extension and Electron App.
- [PR #5](https://github.com/fluid-lab/gamepad-navigator/pull/5): Created the initial skeleton for the project repository. Read the documentation of [Grunt](https://gruntjs.com/) and [ESLint](https://eslint.org/) for setting up the configuration.
- Tested the [Gamepad API Vibration](https://www.chromestatus.com/feature/5705158763741184) and studied the various [Chrome Extension APIs](https://developer.chrome.com/extensions/api_index). I wrote some sample extensions alongside and also started exploring [Electron.js](https://www.electronjs.org/) and [Robot.js](https://robotjs.io/).
- Investigated and discussed approaches with the Fluid Community members about using Infusion's npm package inside a Chrome Extension. After deliberation, I came down to the approach used in the [UIO+ Chrome Extension](https://github.com/fluid-project/uio-plus) for the same.

---
 
## Week Two

### Time Period

1 week (June 8 - June 14)

### Weekly Check-in:

- In the previous weekly check-in, we decided that I'll learn and try out both the technologies I proposed. So, we discussed about my review of the two candidates, their benefits, and limitations apart from the ones already mentioned in the document.
- We decided that I'll prepare a written analysis of the two technologies to choose the final candidate and after that, we'll work on the project plan.

### Tasks Completed:

- [PR #6](https://github.com/fluid-lab/gamepad-navigator/pull/6): Configured [Grunt Banner](https://www.npmjs.com/package/grunt-banner) plugin to add license/copyright boilerplate at the top of relevant files and restructured license and copyright-related files as per the Fluid Community's conventions. Studied RegExp for configuring the plugin to find the existing banner and replace with the newer ones.
- Made changes to the [PR #5](https://github.com/fluid-lab/gamepad-navigator/pull/5) as suggested by the mentor.
- Completed studying and reviewing [Electron.js](https://www.electronjs.org/) and [Robot.js](https://robotjs.io/). For the analysis of the candidates, I implemented a [demo app](https://github.com/dmahajan980/electron-robot-demo) which uses Gamepad API to take inputs from a gamepad and process them into OS level actions.
- Prepared the analysis for the two shortlisted candidates - Electron App and Chrome Extension and finalized the Chrome Extension for the project with my mentor.<br>
  _(Updated in [PR #4](https://github.com/fluid-lab/gamepad-navigator/pull/4))_
