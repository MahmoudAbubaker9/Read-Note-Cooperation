# Read-Note-Cooperation

# Read: 42 - Location

Using the Google Play services location APIs, your app can request the last known location of the user's device.


## Set up Google Play services

* To access the fused location provider, your app's development project must include Google Play services.

* Download and install the Google Play services component via the SDK Manager and add the library to your project.

## Specify app permissions

To protect user privacy, apps that use location services must request location permissions.

### Types of location access

* Category: Either foreground location or background location.
* Accuracy: Either precise location or approximate location.

## Create location services client

In your activity's onCreate() method, create an instance of the Fused Location Provider Client as the following code snippet shows.

```
private FusedLocationProviderClient fusedLocationClient;

// ..

@Override
protected void onCreate(Bundle savedInstanceState) {
    // ...

    fusedLocationClient = LocationServices.getFusedLocationProviderClient(this);
}

```


## Get the last known location
 - Once you have created the Location Services client you can get the last known location of a user's device. 
 - getLastLocation() method - to retrieve the device location. It returns a Task that you can use to get a Location object with the latitude and longitude coordinates of a geographic location.
 - The location object may be null in the following situations - location is turned off in the device settings, device never recorded its location, and Google Play services on the device has restarted.
