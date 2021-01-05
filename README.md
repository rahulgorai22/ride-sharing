# ride-sharing


## Classes

```
Vehicle  Atrributes -> (_id, type, reg_no, model, color, capacity)
         Interfaces (VehicleHandler) -> init_vehicle(), generate_vehilce(), delete_vehicle(), modify_vehicle()
         Relations -> 1 Vehicle : 1 Driver
                      1 Driver : 1 Vehicle
```

```
Ride Attributes -> (_ride_id (primary_key), status, source (type location), destination (type location), fare)
         Interfaces (RideHandler) -> init_ride(), start_ride(), end_ride(), update_ride()
         Relations -> 1 Ride : 1 Rider
                      1 Driver : n Rides ( n = 1 for single booking, ex Uber Go)
                                         ( 1 <= n <= capacity for share ride, Uber pool)
```

```
Location Attributes -> (_id, latitue, longitude, address , zip, country)
         Interfaces (LocationHandler) -> init_location(), save_location()
         Relations -> Each objects can have multiple location objects saved.
```

```
Driver Attributes -> (_driver_id, name, email, base_location(type location), _vehile_id, []rides(array of ride id's)
       Interfaces (DriverHandler) -> register(), delete(), update()
       Relations -> 1 Driver : n Rides
                    1 Driver : 1 Vehicle
```
                  
