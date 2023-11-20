# favorite_places

Flutter project utilizing location and geolocation services, as well as API requests to Google API and saving data locally using SQFLite

## Running

Switch API_KEY_HERE instances in `location_input.dart` and `place_detail.dart` for the Google Maps API Key, found in [the Google Cloud Platform.](https://console.cloud.google.com/google/maps-apis/overview)

## Basic structure

- models:
    - place.dart: Model of a location with it's coordinates and human-readable address, and a Place with a location, title and an image File, as well as an ID which is randomly created upon object creation, and re-used for already created objects.

- providers:
    - user_places.dart: Containes the provider objects that help the entire app share information on places and locations. Also creates new database entries and loads existing ones.

- screens:
    - places.dart: Main screen for the app; allows creation of new places, and viewing the data from already created places. Should there be data in the database, it will load said data.

    - add_place.dart: Input screen where the user chooses the name of the new place, takes a photo of it, and either selects a position on a Google Map or uses it's own current location. Said photo and map are then previewed before being added to the notifier.

    - place_detail.dart: Shows the information previously collected by the user about said place. Shows the photo with a subtitle, and a circular Maps preview which can be tapped to open Google Maps on said location.

    - map.dart: Used by both add_place.dart and place_details.dart, creates a new instance of a Google Maps objects, which can either have not been selected yet, allowing a location to be saved, or showing an already selected place, in which case the user cannot change the marker placement.

- widgets:
    - places_list.dart: Creates a ListView object which puts the created places in line, with a circular preview of the photo, the title of the place and it's human-readable address.

    - image_input.dart: Creates an object which interacts with the native camera features to take or select a picture, and then preview said photo.

    - location_input.dart: Creates an object that can either obtain the current location of the user, or allows the user to choose a marker placement using Google Maps API, and afterwards use the chosen location data to interact with the Google Maps API to obtain a map witha single marker, which is shown on screen.

- main.dart: Main app file from which the project is run.
