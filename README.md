Based on [node-red-contrib-solar-power-forecast](https://flows.nodered.org/node/node-red-contrib-solar-power-forecast].

Thanks to [Dean Cording](https://github.com/DeanCording).

# node-red-contrib-solar-power-forecast-plus
A Node Red node to forecast the power output of a solar system under ideal conditions at a specified time.

Input message payload contains the timestamp for solar power output to be calculated at.
Can also receive on object the parameters for dynamic requests.

Uses the [suncalc](https://github.com/mourner/suncalc) to calculate the current sun position. Power forecast is adjusted for panel tilt, orientation, altitude, panel area, number of panels and panel efficiency.

## Configuration
- Name
- Lat & lon is the location of the solar system.
- Tilt is degrees from the horizontal.
- Orientation is the bearing in degrees from North.
- Altitude is in metres above sea level.
- Area is the surface of a single panel in m^2.
- Number is the number of panels in the system.
- Efficiency is the conversion efficiency of the panel under ideal conditions.

## Input
- msg.payload contains the timestamp for the calculation.
- msg.payload.tilt  contains the Titl for the calculation.
- msg.payload.orientation contains the Orientation for the calculation.

## Output
msg.payload contains:
- timestamp: Timestamp of calculation
- name: identification for calculation
- powerforecast: Forecast of electrical power generated by the system under ideal conditions.

See [PV Education](http://www.pveducation.org/pvcdrom/properties-of-sunlight/solar-radiation-at-earths-surface) for details of calculation.
