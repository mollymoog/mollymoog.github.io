---
layout: post
title:      "Build out the counting component"
date:       2021-02-06 00:00:16 -0500
permalink:  build_out_the_counting_component
---


* Needs to have local state, so will be a class component
* Assign the key(in this case, heart) an initial value of 0
* Use an event handler(onClick) to call the function that will count for you
* The function will be updating the local state, you will want to pass state in as a variable to the setState function.

```
import React from 'react';

class Heart extends React.Component {

    constructor(props) {
        super(props)
        this.state= {
            heart: 0
        }
    }

    handleClick = () => {
        this.setState((boy) => ({
            heart: boy.heart + 1
        }))
        console.log(this.props.id)
    }

    render() {
        return (
        <p onClick={this.handleClick} >♡ {this.state.heart}</p>
        )
    }

}

export default Heart
```
