# espressoPID
Arduino based Proportional Integral Derivative (PID) Controller to control a single boiler in an expresso machine. 

<b>Hardware</b>
- NodeMCU
- Thermocouple (K type) or RTD PT100/PT1000
- ADC and amplifier for temperature measurement
- 40A Solid State Relay (SSR) DC controlling AC (DA)
- OLED screen
- Push buttons
- Wiring harness for disconnecting Arudino cleanly.

<b>Requirements</b>
- PID auto starts on power connection
- Should have ability to switch between brewing and steaming settings using a switch.
- Should be able be controlled via the wifi connection.  Options for control include hosted website, MQTT to Home Assistant or other App (Blynk?).
- Capability for local display such as OLED.
  - Current boiler temperature
  - Setpoint for boiler temperature
  - Time operating
  - Shot timer (will require sensing brew switch or Hall sensor on solenoid valve)
  - Pressure (will require installing pressure transducer).
- Stealth install, hidden internal to machine <u>or</u> external box mounted for OLED.
- No external buttons - interface with existing switches 
  - except if adjusting PID settings locally is desired in the future (possibly a pre-fusion control!) 
  - consider adding buttons on rear for stealth.
- Single SSR to drive heater
- Wifi connectivity - not required to function, PID functions auto-start.
- MQTT publish and subscribe (or other suitable interface with Home Assistant)
- PID autotuning functionality
- Integral anti-windup - use a band to support initial heatup without integral term, proportional is likely sufficient until about 80 degC.

<b>Home Assistant</b>
- Climate card (less preferred as the functionality is limiting)
- Vertical stack card (preferred)
  - Current boiler temperature
  - Setpoint for boiler temperature
  - Mode (heating/brew/steam)
  - Trend of temperature/setpoint
  - Slider bar for brew setpoint
  - Slider bar for steam setpoint
  - Time operating 
- Push notifications
  - boiler at setpoint and stable.
  - auto-tune results
  - shot timer
  - warnings   
