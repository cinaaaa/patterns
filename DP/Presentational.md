# Container/Presentational Pattern
#### Enforce separation of concerns by separating the view from the application logic

Let's say we want to create an application that fetches 6 dog images, and renders these images on the screen.

Ideally, we want to enforce separation of concerns by separating this process into two parts:

Presentational Components: Components that care about how data is shown to the user. In this example, that's the rendering the list of dog images.
Container Components: Components that care about what data is shown to the user. In this example, that's fetching the dog images.

---

## Presentational Component

A presentational component receives its data through props. Its primary function is to simply display the data it receives the way we want them to, including styles, without modifying that data.

Let's take a look at the example that displays the dog images. When rendering the dog images, we simply want to map over each dog image that was fetched from the API, and render those images. In order to do so, we can create a functional component that receives the data through props, and renders the data it received.

The DogImages component is a presentational component. Presentational components are usually stateless: they do not contain their own React state, unless they need a state for UI purposes. The data they receive, is not altered by the presentational components themselves.

---

## Container Components

The primary function of container components is to pass data to presentational components, which they contain. Container components themselves usually don't render any other components besides the presentational components that care about their data. Since they don't render anything themselves, they usually do not contain any styling either.

In our example, we want to pass dog images to the DogsImages presentational component. Before being able to do so, we need to fetch the images from an external API. We need to create a container component that fetches this data, and passes this data to the presentational component DogImages in order to display it on the screen.

---

## Hooks
In many cases, the Container/Presentational pattern can be replaced with React Hooks. 
The introduction of Hooks made it easy for developers to add statefulness without needing 
a container component to provide that state.

Instead of having the data fetching logic in the DogImagesContainer component, 
we can create a custom hook that fetches the images, and returns the array of dogs.
