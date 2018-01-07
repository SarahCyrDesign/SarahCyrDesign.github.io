---
layout: post
title:      "React/Redux with Ruby API Project"
date:       2018-01-07 20:14:11 +0000
permalink:  react_redux_with_ruby_api_project
---


As I write this blog, I am still in disbelief of how far I have come in this program from April 2017. I pushed myself beyond my comfort zone and learned that I am far more capable  than I have ever imagined. Going through the Flatiron program has truly been a life changing experience for me. Now at the apex of the curriculum, I am tasked to present to you my final project - **Feathered Homes**


I decided to create an App that sheds light on a worthy cause of mine. Presently there has been an increase in unwanted parrots in the United states ever since their popularity for ownership has risen in response. Most likely new owners are unprepared of the responsibilities of raising parrots long term whether their lifespan can range from a few to 70+ years. As a an unfortunate result, many parrots have been abandoned and remain homeless. The Feathered Homes app is created so that owners can anonymously place their bird up for adoption and potential new adoptees can look at the available birds. The app also serves as a resource to showcase a listing of available bird rescues and sanctuaries in the U.S. 

![](https://i.imgur.com/xUETVYQ.png?1)

<br>
<br>

![](https://i.imgur.com/eRhB2HF.png?1)

<br>
<br>

![](https://i.imgur.com/d7QEoQ4.png?1)

<br>
<br>

The application has a Rails API backend that renders JSON and uses the database to persist data. In order to allow for users to upload their own bird photos, I utilized the 'paperclip' and 'paperclip-cloudinary' gems. Cloudinary is an external server that stores the uploded photos and has wonderful resources and support. The 'geocoding' gem was also utilized in conjunction to Google's location API for owners to add in their adress and in return have a Google map show up in the client-side UI. There was no need to render ERB pages in Rails since we are moving all fornt-end login to React .

The client portion of the application is run by React, a JavaScript library which holds a powerful UI and Redux, a stable, lightweight, state container for JavaScript apps. Redux encapsulates your entire application’s state in one place and the application’s state is immutable.  You can isolate your state and it helps with debugging. React feels lightweight in it's rendering because it shows you in realtime how your front-end is rendered instantaneously. By breaking parts of the UI by components and containers, you can easily keep track of the state patterns and properties(props) of the various elements of your app.

As an example of the react flow, a new feature I added towards the completion of the project is the ability to add hearts to a bird, a representation of likes in Facebook:  

* First we break our hearts into an action and make a call to our Ruby API:

```
src/action/birdAction.js

export function addHeart(id, values) {
  return (dispatch) => {
    return fetch(`/api/birds/${id}.json`, {
      method: 'PUT',
      headers: {
       'Accept': 'application/json',
       'Content-Type': 'application/json'
     },
      body: JSON.stringify({bird: {hearts: values}}),
    })
    .then(response => response.json())
    .then(bird => {
      dispatch({type: 'ADD_HEART', id});
    })
    .catch( () => dispatch(birdsHasErrored(true)));
  }
}
```

- With Redux we utilize functions used to call a reducer(a JavaScript reduce method) which takes two parameters: an action and a next state. Reducers are also pure functions therefore no side effects occur.

- Notice the use of .slice() instead of .splice to update the state of the hearts, which doesn't destructively alter the object's properties.

```
export function birds(state = [], action) {
...
...
case 'ADD_HEART':
      let index = state.findIndex(bird => bird.id === action.id);
      let bird = state[index];

      return [
        ...state.slice(0, index),
        Object.assign({}, bird, { hearts: bird.hearts += 1 }),
        ...state.slice(index + 1)
      ];


    default:
      return state;
  }
}



```


- Since adding a heart has to do with the bird model itself, we need to add it to the Bird component

- We also need an event handler for when a user clicks on the 'fill a heart' button do that upon
  rendering the content, the state of the number of hearts present is changed


```
src/components/Bird.js

import { addHeart } from '../actions/birdActions'

class Bird extends Component {

  handleOnHeart = () => {
    this.props.addHeart(this.props.bird.id, this.props.bird.hearts + 1)
  }
	
	 render(){
      const bird = this.props.bird;
      return (
			....
			....
			<p><button
              className="heart-btn"
              onClick={this.handleOnHeart}>
              Fill a Heart
            </button> {bird.hearts} <i className="red heart icon"></i></p>
		}				

```

Follow my project on GitHub for future features! https://github.com/SarahCyrDesign/feathered-homes


