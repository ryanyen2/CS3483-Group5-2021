<p align="center">
    <a href="https://github.com/ryanyen2/CS3483-Group5-2021/issues"><img alt="GitHub issues" src="https://img.shields.io/github/issues/ryanyen2/CS3483-Group5-2021?color=sucess&style=flat-square"></a>
    <a href="https://github.com/ryanyen2/CS3483-Group5-2021/network"><img alt="GitHub forks" src="https://img.shields.io/github/forks/ryanyen2/CS3483-Group5-2021?color=sucess&style=flat-square"></a>
    <a href="https://github.com/ryanyen2/CS3483-Group5-2021/stargazers"><img alt="GitHub stars" src="https://img.shields.io/github/stars/ryanyen2/CS3483-Group5-2021?color=sucess&style=flat-square"></a>
    <a href="https://github.com/ryanyen2/CS3483-Group5-2021/blob/master/LICENSE"><img alt="GitHub license" src="https://img.shields.io/github/license/ryanyen2/CS3483-Group5-2021?color=sucess&style=flat-square"></a>
</p>

# HiLive

> A live streaming chatroom involving multiple modalities, such as voice, gesture, and facial expression.

## Introduction
We focus on demonstrating the design, as well as highlighting the advantages and our considerations on design features, using the knowledge and design principles learned in CS3483.

As mentioned in our previous design reports, the project is motivated by the limited chatroom in the live stream. This interface is designed for a better chatroom experience in a live streaming platform based on Twitch, which is a popular video game live streaming platform. It also could be further generalized and adopted by video platforms like YouTube. Viewers usually type some messages in the chatroom and send some emojis to communicate with others and vibrant the atmosphere in the streaming room. However, the monotonous form of interaction has long been criticized by users. Therefore, we propose HiLive, where people can not only send emojis that are generalized according to their recognized facial expression but also say something and send the transcribed message directly without typing it out themselves. With the gesture recognition function, users are no longer bound to the keyboard, therefore, they can have an immersive live streaming interaction experience. 


## Features

### Front Page
The front page levereage the use if Twitch API, and the OAuth authentication system. Users can login and register to the website with Twitch account. And the front page also provides a list of avaliable Live streams for users to click into it.

  <p align="center">
    <img  max-width="768" src="https://i.imgur.com/tbDfTvZ.png">
  </p>
<br />

### Recommended Channels Component

The `<VideoGroup data={[]}/>` component is completely reusable, it only takes a data array from the official Twitch API and shuffles the results (Some sort of recommended channels "algorithm")

  <p align="center">
    <img  max-width="768" src="https://i.imgur.com/mpvTCuY.png">
  </p>
<br />

### Facial Expression Recognition
The facial expression recognition to emoji is a interesting feature that can let user interact with streamers directly. We have trained a model with more than 2000 images for different emoji categories. The prdiction outcome is in real-time and can be seen in the demo video we provided. The following figure capture some of the facial expression recognition results.

![angry image](/demo/angry.png)
![smile image](/demo/smail.png)
![surprise image](/demo/surprise.png)
![tease image](/demo/tease.png)



### Speech to Text Component
Speech to Text used the Google Cloud Speech Recognition API to transcribe the voice to text and sent it to the chatroom. The website will capture the users voice with MDN Web Audio API, which means it will streaming the user's voice and activate the speech-to-text once receving the real-time speech data in byte format.


### Gesture Recognition Component
The gesture recognition using the repository from [Real-time Hand Gesture Recognition with 3D CNNs](https://github.com/ahmetgunduz/Real-time-GesRec). Here is the demo video of the outcome.
<div align="center" style="width:image width px;">
  <img  src="https://media.giphy.com/media/9M3aPvPOVxSQmYGv8p/giphy.gif" width=500 alt="simulation results">
</div>

Figure: A real-time simulation of the architecture with input video from EgoGesture dataset (on left side) and real-time (online) classification scores of each gesture (on right side) are shown, where each class is annotated with different color. 

## Built With:

- [x] Next.JS
- [x] Typescript
- [x] Axios
- [x] Styled-Components
- [x] TwitchAPI
- [x] Deployed to Vercel

## Run this locally

To run this project locally, you'll need Node.js installed.

Install dependencies preferably with `yarn` but you can also use `npm install`

Create a .env file in the root of the folder based on .env.example.

Run your Next.JS App with `yarn dev` or `npm run dev`

Go to `localhost:3000` and check out this amazing clone
