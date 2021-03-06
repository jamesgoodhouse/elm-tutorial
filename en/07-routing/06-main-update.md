> This page covers Elm 0.18

# Main update

We need our main `update` function to respond to the new `OnLocationChange` message.

In __src/Update.elm__ add a new branch:

```elm
...
import Routing exposing (parseLocation)

...

update msg model =
    case msg of
        ...
        OnLocationChange location ->
            let
                newRoute =
                    parseLocation location
            in
                ( { model | route = newRoute }, Cmd.none )
```

Here when we receive the `OnLocationChange` message, we parse this location and store the matched route in the model.