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
        <a href="#-project-abstract">Project Abstract</a>&nbsp;&nbsp;&nbsp;
        <a href="#-deliverables">Deliverables</a>&nbsp;&nbsp;&nbsp;
        <a href="#-demo">Demo</a>&nbsp;&nbsp;&nbsp;
        <a href="#-contributions">Contributions</a>&nbsp;&nbsp;&nbsp;
        <a href="#-blog">Blog</a>&nbsp;&nbsp;&nbsp;
        <a href="#-mentors">Mentors</a>&nbsp;&nbsp;&nbsp;
        <a href="#-links">Links</a>
    </code>
</p>

I got a chance to work on the most downloaded App on Rocket.Chat - The Poll App!

From not having used Typescript before, to building an entire App completely in Typescript - 3 months of Google Summer of Code passed.

I intend to maintain this repository as a final report summary of my GSoC work and a quick guide for all future GSoC aspirants.

## ⭐ Project Abstract

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

**All of the above deliverables were completed within the GSoC period. Yay! 🎉**

## 📺 Demo

### 📊 Improved Response Visualizations of Poll Results

The Poll App currently offers a basic grayscale visualization of responses in the form of a bar graph. This has been significantly improved to better the user experience through the following implementations:

#### Highlight Winner Response

If you’ve used the Poll App before you would know how boring grayscale gets. It is impossible to identify which vote is the winner. This subfeature improves upon this by using unicode characters to display winner responses in blue and the remaining in black. This theme has been inspired by Twitter Polls.

Now this has a tricky edge case. What if more than two responses have the same number of votes? Which one becomes blue then? Answer: All of them!

#### Dynamically Updated Total Votes

In the current Poll App the only way to estimate the total number of votes is to manually count total votes received per response. Moreover, since the numbers of votes for each response keep changing asynchronously as members vote it is cumbersome to keep count of the total votes. This subfeature eliminates this hurdle and provides dynamically updated total votes. It also displays a "Final Results" label when the Poll has ended.

https://user-images.githubusercontent.com/28918901/130346282-5f89a383-499f-41df-8528-eb16fc0627d0.mp4

### 👀 Mixed Visibility Mode

The Poll App offered two visibilities of voter identities for responses - Open and Confidential. This implementation adds another visibility - Mixed. The Mixed visibility mode now allows the Poll creator to decide beforehand for which options the voter identities should be revealed and for which ones they should stay anonymous.

https://user-images.githubusercontent.com/28918901/130346389-6539289c-a6fa-42b0-8edb-8681dc285461.mp4

### 🙌 Ability to Add User-Defined Options

Polls posted in groups on platforms such as Facebook allow group members to add options after the poll has been created. This better involves the community and evokes ideas and opinions from the entire group, not limited to only the poll creator. Through this implementation a similar functionality has been extended to the Rocket.Chat Poll App.

https://user-images.githubusercontent.com/28918901/130346432-6039c672-f739-4573-854c-6ec5a159ab85.mp4

### ☁️ Word Cloud Generation for Poll Responses

Until now the only way to view responses was a bar graph. Bar graphs are simple. Bar graphs do the job and bar graphs are just OK. Introducing word clouds for poll responses. Wordcloud make can make use of a specific user-defined API to fetch wordclouds. An option is to use the [Quickchart wordcloud API](http://quickchart.io/documentation/word-cloud-api/) which works well on Rocket.Chat servers with Internet access. 

In case you're running a Rocket.Chat server locally in an isolated environment, I have created an API for fetching wordclouds (which works better than Quickchart enterpise 🚀). This API even allows you to customize your wordcloud responses and also factors in number of votes for size of each word within the wordcloud. I have open-sourced the word-cloud API [here](https://github.com/RonLek/wordcloud-api). Feel free to use and contribute!

https://user-images.githubusercontent.com/28918901/130346661-358ceac8-3504-41d7-b23e-f9119ce652b7.mp4

### ✨ Additional Poll Modes 

Currently the Poll App has two modes of poll creation - Multiple Choice and Single Choice. This implementation extends these modes to the following types:
- 1-to-5 Poll.
- 1-to-10 Poll.
- Agree/Disagree Poll.
- Overrated/Underrated Poll.

The benefit that these polls provide to the users is that the users get a template of poll options without having to fill them out themselves. For example, if it is a poll to “rate your favorite movie out of 10” instead of typing in all the numbers from 1 to 10, the user simply selects the 1-10 poll mode and the Poll App automatically fills out the options for the user.

https://user-images.githubusercontent.com/28918901/130346483-ea670ea2-8132-4f47-ba84-b0638ea48ebc.mp4

### ❤️ Live Polls 

We come to our final feature. Live Polls. This is like a mini-GSoC project on its own. If you have ever seen live quizzes where the user needs to vote before the time ends. Well this is it!

Live Polls are a collection of multiple polls that are also timed. They allow the Poll creator to either jump to the next poll or wait for a `Time to vote` number of seconds to let the Poll App automatically finish the current poll and post the next Poll. The data is pulled from the persistent storage and the [Scheduler API](https://rocketchat.github.io/Rocket.Chat.Apps-engine/modules/scheduler.html) is used to schedule Poll finishes. Live Polls can be triggered through the `/poll live <number of polls>` command.

A very good use-case of Live Polls is through schools and colleges to conduct timed-exams and quizzes on Rocket.Chat.

https://user-images.githubusercontent.com/28918901/130346847-fbbdb43d-70c8-4bfc-8871-73a247d4d434.mp4

Another feature of Live Polls is late retrieval. This allows the poll creator to pre-initialize the polls with questions, options and time to vote and retrieve them at a later time using and id. The id generated is unique to each Live Poll.

Live Polls can be saved for later through the `/poll live save <number of polls>` command and can be retrieved through the `/poll live load <id>` command.

https://user-images.githubusercontent.com/28918901/130346957-8db90149-29e9-4868-9bd9-a64f47a94556.mp4

Live Polls can be retrieved by anyone within the room provided they possess the Live Poll id. On using the `/poll live load` command with a wrong or a non-existent Live Poll id an error message is shown to the user executing the command.

## 🚀 Contributions

### PRs

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

### Issues
    

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
    
## 😎 Blog
    
I have been writing blogs regarding each stage of GSoC. 

Fun fact: One of my blogs got published on HackerNoon as well! 🕕
    
<div align="center">
    
| **GSoC Phase** | Blog |
|:--------------------|:-------------------|
| Selection | [How I Got Selected into Google Summer of Code](https://rohanlekhwani.medium.com/how-i-got-selected-into-google-summer-of-code-e3db8bbaeb56) |
| Community Bonding Period | [Google Summer of Code: How to Ensure a Successful Community Bonding Period](https://rohanlekhwani.medium.com/google-summer-of-code-how-to-ensure-a-successful-community-bonding-period-605a5147ee20) |
| Coding Phase 1 | [Commit, Push, Merge: GSoC Coding Phase 1](https://rohanlekhwani.medium.com/commit-push-merge-gsoc-coding-phase-6b6c6daf8229) |
| First Evaluation | [GSoC First Evaluations: All You Need to Know](https://rohanlekhwani.medium.com/gsoc-first-evaluations-all-you-need-to-know-18f89ff2676a) |
| Coding Phase 2 | In Progress |
| Final Evaluation | In Progress |
    
</div>
    
## 🎓 Mentors

A big big thank you to my mentors for their guidance before and throughout GSoC. 🙏 
    
I learned beyond GSoC from them and am forever grateful to be mentored by them.

- **Ramkumar KB** - [GitHub](https://github.com/ramkumarkb). [LinkedIn](https://www.linkedin.com/in/ramkumarkb)

- **Murtaza Patrawala** - [GitHub](https://github.com/murtaza98). [LinkedIn](https://www.linkedin.com/in/murtaza-patrawala-b17419166/)

## 🔗 Links
    
- My GSoC Presentation can be found [here](https://bit.ly/gsoc-presentation).

- Watch the above presentation in video - [here](https://youtu.be/3jSNDDECdDg) !
 
- We maintained a Kanban board to track our progress. [Take a look](https://github.com/orgs/RocketChat/projects/40)

- Want to discuss about GSoC / Rocket.Chat / Open-source ? Let's connect!
<div align="center">

| **Student** | Rohan Lekhwani |
|:--------------------|:-------------------|
| **Organization** | [Rocket.Chat](https://rocket.chat/) |
| **Project** | [Poll App Mega Extensions](https://summerofcode.withgoogle.com/projects/#6521788818784256) |
| **GitHub** | [@RonLek](https://github.com/RonLek) |
| **LinkedIn** | [rohanlekhwani](https://www.linkedin.com/in/rohanlekhwani) |
| **Twitter** | [rohanlekhwani](https://www.twitter.com/rohanlekhwani) |
| **Website** | [ronlek.github.io](https://ronlek.github.io) |
| **Email** | <a href="mailto:rohanlekhwani@gmail.com">rohanlekhwani@gmail.com</a> |
| **Rocket.Chat** | [rohan.lekhwani](https://open.rocket.chat/direct/rohan.lekhwani) |
       
</div>
