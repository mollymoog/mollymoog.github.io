---
layout: post
title:      "React/Redux Reflect"
date:       2021-01-30 19:50:10 +0000
permalink:  react_redux_reflect
---


When I’m not coding I’m usually talking to my best friend. We can spend hours thinking of different problems that need solving, and daydreaming about how we’re going to change the world with our solutions. During one of these conversations I realized that with my newly acquired coding skills, I could build one of our ideas. 
Okay I lied a bit there, if I’m not coding or talking to my friend, we are most likely playing some sort of board game, which is where this project comes in. During quarantine, we’ve found a few online substitutes for our favorites, including one based on CodeNames. This is a straightforward game based around a set of random words; I wanted to mimic this application but give the admin more control over the lists of words, basing them around difficulty. 
After a few days scouring the internet for an API of words categorized by difficulty, I started to realize that what seems so easy to me is not so easy for a computer. I quickly pivoted and went with images instead of words, another way of making the game more accessible, but this question of why creating random lists of words is not easy still haunted me. 

Moving forward with the images, I remembered that this was only the first step, and that the rest of the project still loomed ahead. Step two was getting these images saved in my backend, well saving all 3,000 of them would not be efficient, so instead I used RestClient to initiate fetches to the API from my backend. Many articles that I found advised factoring the code into its own restclient file, but since I wanted to assign the images to a game at the instantiation of the game, I chose to put it right in the controller. This also gave me the freedom to associate different images with the teams and pass that all to the front end in one motion. On the front end, this allowed me to create a game on the click of a button, and then fetch the images associated with that game while the page loaded. 
This worked, most of the time. Sometimes it didn’t work though, my app would hit the ImageContainer, and there wouldn’t be a gameId for it to use to fetch the images. Because this is an asynchronous action, I realized I had to account for the time it might take to create the game by putting in a timer. I had to fiddle around with it, and found that 10 seconds was ample time (though a bit longer than I would’ve liked) for the create game action to complete and pass the gameId to the ImageContainer.

```
    componentDidMount() {
        this.timer = setInterval(() => {
            if (this.state.seconds > 0) {
                this.setState({
                    seconds: this.state.seconds -1
                })
            } else {
                let gameId = this.props.games[0].id
                this.props.fetchImages(gameId)
            }
        }, 1000)
    }
```
