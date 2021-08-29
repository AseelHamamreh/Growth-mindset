# Read: 42 - Location


### Set up Google Play services
To access the fused location provider, your app's development project must include Google Play services. Download and install the Google Play services component via the SDK Manager and add the library to your project.

### Specify app permissions
Apps whose features use location services must request location permissions, depending on the use cases of those features.

### Create location services client
In your activity's onCreate() method, create an instance of the Fused Location Provider Client as the following code snippet shows.

```
private lateinit var fusedLocationClient: FusedLocationProviderClient

override fun onCreate(savedInstanceState: Bundle?) {
    // ...

    fusedLocationClient = LocationServices.getFusedLocationProviderClient(this)
}
```

### Get the last known location
Once you have created the Location Services client you can get the last known location of a user's device. When your app is connected to these you can use the fused location provider's getLastLocation() method to retrieve the device location. The precision of the location returned by this call is determined by the permission setting you put in your app manifest, as described in the guide on how to request location permissions.

To request the last known location, call the getLastLocation() method. The following code snippet illustrates the request and a simple handling of the response:

```
fusedLocationClient.lastLocation
        .addOnSuccessListener { location : Location? ->
            // Got last known location. In some rare situations this can be null.
        }
```

The getLastLocation() method returns a Task that you can use to get a Location object with the latitude and longitude coordinates of a geographic location. The location object may be null in the following situations:

* Location is turned off in the device settings. The result could be null even if the last location was previously retrieved because disabling location also clears the cache.
* The device never recorded its location, which could be the case of a new device or a device that has been restored to factory settings.
* Google Play services on the device has restarted, and there is no active Fused Location Provider client that has requested location after the services restarted. To avoid this situation you can create a new client and request location updates yourself. For more information, see Receiving Location Updates.

### Choose the best location estimate
The FusedLocationProviderClient provides several methods to retrieve device location information. Choose from one of the following, depending on your app's use case:

* getLastLocation() gets a location estimate more quickly and minimizes battery usage that can be attributed to your app. However, the location information might be out of date, if no other clients have actively used location recently.
* getCurrentLocation() gets a fresher, more accurate location more consistently. However, this method can cause active location computation to occur on the device

This is the recommended way to get a fresh location, whenever possible, and is safer than alternatives like starting and managing location updates yourself using requestLocationUpdates(). If your app calls requestLocationUpdates(), your app can sometimes consume large amounts of power if location isn't available, or if the request isn't stopped correctly after obtaining a fresh location.




