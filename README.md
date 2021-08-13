# Models
* The main purpose of this exercise is to model the flow of requests in a slightly more complex project (e.g a project that involves multiple models in different languages, plus styling code)
* Two models are reproduced below. For full models, take a look at images
### Text to reproduce model using diagram.codes: 
* Model 1 (visting home page)
[client->controller:"GET /"
controller->views: "load html"
views=>css: "load styling"
css-->views: "return styling"
views->googleapi: "Load jquery lib"
googleapi->views: "return jqeury lib"
views->client:"html output"]

* Model 2 (clicking temperature up)
[client->views: "user clicks temp up button"
views->interface:"interface listenns to dom event"
interface->controller:"post request to /temperature that specifies up/down/reset"
controller->model:"temperature.up"
interface->controller:"get request"
controller->model:"request model data"
model->controller:"returns model data, controller converts to json"
controller->interface:"json of model data"
interface->views:"parse json, update html attribs using jquery"
views->client:"updated html output"]

* Model 3 (clicking power saving mode on)
[client->views: "user clicks power saving on button"
views->interface:"interface listenns to dom event"
interface->controller:"post request to /power-saving-mode that specifies if on"
controller->model:"thermostat.power_save_on"
interface->controller:"get request to /temperature"
controller->model:"request model data"
model->controller:"returns model data, controller converts to json"
controller->interface:"json of model data"
interface->views:"parse json, update html attribs using jquery"
views->client:"updated html output"]


# Thermostat

An exemplar for the Thermostat Single Page Web App project.

## How to use

```
ruby app.rb

```

## Testing

To run feature tests:

```
rspec
```

To run unit tests:

```
open public/javascript/SpecRunner.html
```
