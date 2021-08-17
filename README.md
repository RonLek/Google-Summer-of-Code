<div align="center">
    <a href="https://summerofcode.withgoogle.com/projects/#6521788818784256"><img src="https://i.imgur.com/pgkUceb.png" width="650" alt="google-summer-of-code"></a>
    <br>
    <b> 
        <p>
        Poll App Mega Extensions: Revamping the <a href="https://github.com/RocketChat/rocket.chat.app-poll">Poll App </a> on <a href="https://rocket.chat/">Rocket.Chat</a>
        </p>
    </b>
</div>

<p align="center">
    <code> 
        <a href="#project-abstract">Project Abstract</a>&nbsp;&nbsp;&nbsp;
        <a href="#deliverables">Deliverables</a>&nbsp;&nbsp;&nbsp;
        <a href="#working-demo">Working Demo</a>&nbsp;&nbsp;&nbsp;
        <a href="#contributions">Contributions</a>&nbsp;&nbsp;&nbsp;
        <a href="#mentor">Mentor</a>&nbsp;&nbsp;&nbsp;
        <a href="#links">Links</a>
    </code>
</p>

I got a chance to work on the most downloaded App on Rocket.Chat - The Poll App!

From not having used Typescript before, to building an entire App completely in Typescript - 3 months of Google Summer of Code passed.

I intend to maintain this repository as a final report summary of my GSoC work and a quick guide for all future GSoC aspirants.

## Project Abstract 📽️

The Rocket.Chat [Poll App](https://github.com/RocketChat/rocket.chat.app-poll) is the go-to app for teams and channel members of any Rocket.Chat room for a rich interactive poll. This project aims to hugely expand its scope making it a tool for enhancing participant's engagement with interactive quizzes / trivia / live-polls.

## 🚢 Deliverables

The following are the deliverables of this project:

- Improving upon the user-experience of existing response visualizations.
  - Highlight winner response [IMPROVEMENT].
  - Displaying dynamically updated total votes both during voting and after results. [IMPROVEMENT]
- Word cloud generation for both predefined and user-defined poll responses. [NEW]
- Feature for Mixed Visibility on responses (voters visible for selected number of responses only) in addition to Open and Confidential visibility types [NEW]
- Ability to add user-options by channel members after poll creation. [NEW] 
- Implementations for additional poll modes [NEW] 
  - 1-5 poll.
  - 1-10 poll.
  - Agree/Disagree poll.
  - Overrated/Underrated poll.
- Adding Live Poll Feature [NEW]
  - Multi-question polls.
  - Time limit for answering each question

**All of the above deliverables were completed within the GSoC period. 🎉**

## 📺 Demo

<!-- TODO: Add demo videos -->

## 🚀 Contributions


### Following is a list of Pull Requests and Issues which I submitted during the GSoC period.

<div align="center">

| PR Link   | Description  | Status | 
| :-----------: | :------------------------------------:| :------:|
| [PR #2](https://github.com/RocketChat/rocket.chat.app-poll/pull/2) | [IMPROVEMENT] Poll Response Visualizations. <br><br> <div align="left"> Highlights include:<ul><li>Highlighting winner response</li><li>Dynamic display of Total Votes.</li><div> | <img src="https://i.imgur.com/tskv8MM.png" width=50 height=40> |
| [PR #5](https://github.com/RocketChat/rocket.chat.app-poll/pull/5) | [NEW] Mixed visibility for poll responses | <img src="https://i.imgur.com/tskv8MM.png" width=50 height=40> |
| [PR #8](https://github.com/RocketChat/rocket.chat.app-poll/pull/8) | [NEW] Add user defined options | <img src="https://i.imgur.com/tskv8MM.png" width=50 height=40> |
| [PR #6](https://github.com/RocketChat/rocket.chat.app-poll/pull/6) | [NEW] Word cloud generation for poll responses | <img src="https://i.imgur.com/1r1keCi.png" width=50 height=40> |
| [PR #11](https://github.com/RocketChat/rocket.chat.app-poll/pull/11) | [NEW] Additional poll modes | <img src="https://i.imgur.com/1r1keCi.png" width=50 height=40>
| [PR #13](https://github.com/RocketChat/rocket.chat.app-poll/pull/13) | [NEW] Live Poll <br><br> <div align="left"> Highlights include <ul><li>Multi-Question Polls</li><li>Timed Polls</li><li>Late Retrieval of Live Poll</li></ul> | <img src="https://i.imgur.com/1r1keCi.png" width=50 height=40> |

</div>

<br>
    
#### The following Issues have been created to provide details over the features implemented.
    

<div align="center">
    
| Issue Link   | Description  | Status | 
| :-----------: | :------------------------------------:| :------:|
| [ISSUE #4](https://github.com/RocketChat/rocket.chat.app-poll/issues/4) | [FEATURE] Mixed Visibility for Poll Responses | <img src="https://i.imgur.com/ihaDyZS.png" width=50 height=40> |
| [ISSUE #7](https://github.com/RocketChat/rocket.chat.app-poll/issues/7) | [FEATURE] Allow adding user-defined choices after Poll creation | <img src="https://i.imgur.com/ihaDyZS.png" width=50 height=40> |
| [ISSUE #3](https://github.com/RocketChat/rocket.chat.app-poll/issues/3) | [FEATURE] Word Cloud Generation for Poll Responses | <img src="https://i.imgur.com/1r1keCi.png" width=50 height=40> |
| [ISSUE #10](https://github.com/RocketChat/rocket.chat.app-poll/issues/10) | [FEATURE] Additional Poll Modes Template | <img src="https://i.imgur.com/1r1keCi.png" width=50 height=40> |
| [ISSUE #12](https://github.com/RocketChat/rocket.chat.app-poll/issues/12) | [FEATURE] Live Poll: Multi-Question and Timed Polls | <img src="https://i.imgur.com/1r1keCi.png" width=50 height=40>

</div>
    
### My overall contributions at Rocket.Chat
    
Besides my GSoC project I have been contributing prolifically to other Rocket.Chat projects - [RC4Git](https://github.com/RocketChat/RC4Community), [RC4Community](https://github.com/RonLek/RC4Community), [Opensource-Contribution-Leaderboard](https://github.com/RocketChat/Opensource-Contribution-Leaderboard), [Rocket.Chat](https://github.com/RocketChat/Rocket.Chat).
    
- [Pull Requests (>50)](https://github.com/pulls?q=is:pr+org:RocketChat+author:RonLek)
- [Issues (>25)](https://github.com/issues?q=is:issue+org:RocketChat+author:RonLek)
