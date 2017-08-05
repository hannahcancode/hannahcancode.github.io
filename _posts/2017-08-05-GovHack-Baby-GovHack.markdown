---
layout: post
title:  "GovHack, Baby GovHack"
---

Last week I participated in my first GovHack! I registered the day before and I wasn't sure whether I would join in, but I went along on the Friday night for the opening and very quickly I was included in a long standing team of Hobart friends. I'm really grateful they let me join in, they're a well oiled GovHack machine.

This team generally make fun minigames for their GovHack entries, and this year was no exception. Having stumbled upon a wealth of data of inquests from colonial Tasmania, we decided to make a card game about the lives and deaths of early settlers and convicts in Tasmania, called Death Who. There were plenty of weird and brutal ways to die - a few visitations by God, being crushed by tins of boiling milk, and death by misadventure. We had backend and frontend devs, and data and asset wranglers. You can find more about the whole project on the [The Secret Lab](https://www.secretlab.com.au/govhack2017) and the backend server written in Go on [Josh Deprez's blogpost](https://joshdeprez.com/post/69-govhack-2017/), but I thought I'd write about the website [Shea](https://twitter.com/sheabunge) and I  made to complement the game.

![Screenshot](https://res.cloudinary.com/doe2gejvd/image/upload/s--eihSyjIO--/c_scale,w_730/v1501899662/Screen_Shot_2017-08-05_at_12.19.51_pm_kh7zyx.png){: .img-responsive, .center-image}

After players had finished playing they are presented with a button to see more information about their hand of five people who they've just been trying to kill. Because it was a hackathon and speed is necessary, I set up a React website using [Create React App](https://github.com/facebookincubator/create-react-app).

I set up a very basic route in ```index.js``` using [React Router](https://github.com/ReactTraining/react-router) to fetch params from the URL, allowing me to keep track of the player: 
 
~~~
<Route path="/:id" component={App} />
~~~
{: .language-js}

Now the game just has to append ```/playerid``` to the end of the url it generates at the end.

The server would provide a json object of the current game state, and in ```App.js``` I make a fetch request to the server. As the server sends back the whole game state, rather than just one player's, I use ```this.props.match.params.id``` as I'm digging into the json object so I can just grab the player's hand.

~~~
getData() {
fetch(serveraddress)
  .then(response => response.json())
  .then(response => response.players[this.props.match.params.id].hand.people)
  .then(response => {
      this.setState({data: response})
    }
  )
  .catch(error => console.log(error))
}
~~~
{: .language-js}

In ```App.js``` I can then feed ```this.state.data``` into our two components - the navbar (or gravestones!) and the main text component.

In ```Navbar.js``` we map through the 5 card items in the hand and, using Shea's css, create a gravestone for each, with the name of the person and a symbol for their death 'engraved' on each. We also keep track of which card we're currently rendering data for, and using an onClick function update the state every time we move between cards.

Finally, for ```Data.js``` we just feed through the data of the current card we're looking at, using the above current card id in the state. We go through each bit of possible data in the object of the individual card, check if it exists, and if it does we spit it out as part of a sentence, giving a link to the actual data source at the end of each piece of information.

It was a really interesting experience developing a website in this short space of time and with so many dependencies. We really couldn't start working on the actual guts of the site until 

    a) The server knew what data would be available
    b) I knew what data I would be getting from the server
    
This meant that we basically had to wait for the entire game logic to be finished in order for us to get everything together, which meant that, while I'd set up the routing and basic app structure on day one, a lot of rushing on the second day to get everything done.
  
Finally, for ease of deployment, I put the website on Heroku using the [Create React App Buildpack](https://blog.heroku.com/deploying-react-with-zero-configuration). This worked like a charm expect for the routing. A quick google search determined I had to add a new file, ```static.json```, to overwrite some of the defaults:

~~~
{
  "root": "build/",
  "clean_urls": false,
  "routes": {
    "/**": "index.html"
  }
}
~~~
{: .language-json}

You can check out the [Github](https://github.com/admiraldolphin/govhack2017) to see the code, see the website working with some hardcoded data [here](http://deathwho.herokuapp.com/1), or you can play the game itself and see it work with the live data!