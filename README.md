![Header](https://i.imgur.com/4DBUyqZ.png) 


***

### Views 


![Views](https://i.imgur.com/tXuArBp.png)

![Views](https://i.imgur.com/MGyTY1D.png)

![Views](https://i.imgur.com/OUv87K4.png)



___

<br>

### User Story


1) The user is first sent to the Home page ('/' path) where they will be presented with a 'Log In' option, a 'Register' option and an option to see a list of all states. The user will be greeted and will be able to read how to use the site in the 'About' section. 

2) The menu bar will present the options to Register ('/auth/register' path) or Login ('/auth/login' path). Upon login attempts, if the username is already in use it will be indicated on the page. If the username and password are valid, the user will be successfully logged in.

3) If the user selects 'See All States' ('/states' path) they will be taken to a page displaying an index of all states. If the user clicks on a state in this list, they will be routed to that states respective page ('/states/:id' path). Displayed in each states' page will be the states' name, capital, population, top attraction and photos. 

4) When the user is logged in, they will be able to browse and learn about states, click the 'I have been here!' button to add states to their profile and utilize the commenting features. 

5) On each states' page, users can leave comments regarding their travels and interact with other users. Each users' respective comments can be updated and deleted. Comments are a feature available only to registered users. Unregistered and/or users that are not logged in will be routed to do so if commenting is attempted.

6) The user can log off ('/auth/logout) at anytime via the menu bar. Upon doing so they will be routed to the Login page.



___

<br>

### WireFrames

![Wireframe](https://i.imgur.com/MpnQ7Rp.jpg)

![Wireframe](https://i.imgur.com/Ja4shyo.jpg)

![Wireframe](https://i.imgur.com/bNKrE9T.jpg)

![Wireframe](https://i.imgur.com/pyq2xok.jpg)

![Wireframe](https://i.imgur.com/HN9yTVs.jpg)



___

<br>

### Schemas

#### State Schema
```language

stateSchema = ({
  state: {
    type: String,
    required: true
  },
  capital: {
    type: String,
    required: true, 
  },
  population: {
    type: Number,
    required: true
  },
  topAttractions: [String],
  stateBird: String, 
  birdImage: String, 
  comments: [Comment.schema]
})



```

#### User Schema
```language

userSchema = ({
  user: {
    type: String,
    required: true 
  },
  password: {
    type: String, 
    required: true 
  },
  emailAddress: {
    type: String, 
    required: true  
  }, 
  firstName: String, 
  lastName: String,
  dateOfBirth: Date,
  states: [{
    type: mongoose.Schema.Types.ObjectId,
    ref:'State'
  }],
})

```
