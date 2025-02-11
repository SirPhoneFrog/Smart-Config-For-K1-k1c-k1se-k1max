# Smart-Config-For-K1-k1c-k1se
Stock configs in K1 series printers are truly terrible, so I've just rewritten it.

# Why?
Because I want to use my printer for maximum, and with right config

# For which printer is it?
k1se-for k1se
k1 series-for upgraded k1 se/k1c/k1 with 20 teeth pulleys

# Changes
1. Build volume for X axis is maximal, 235mm. +15mm to stck one (I tested with 233mm long part printed)
2. Acceleration and limits
3. Accel_per_hz: bigger for right calibration of shapers, if you installed the LATEST version of klipper with NEW shapers calibration or installed anoter spring on X-replace with stock
4. No interpolation. No interpolatin on CoreXY please.
5. Btt sfs 2 support.
   
# Wher for K1MAX?
I don't have it, I can't test it

# How to use?
Replace section with [include ******] with same from your config.
After:
1. Calibrate shapers and look on graphs
2. Calibrate PID
   ```
   PID_CALIBRATE HEATER=extruder TARGET=295
   ```
   ```
   SAVE_CONFIG
   ```
   ```
   PID_CALIBRATE HEATER=heater_bed TARGET=80
   ```
   ```
   SAVE_CONFIG
   ```
4. Replase your **start gcode** with this:
   ```
   M140 S0 
   M104 S0 
   START_PRINT BED_TEMP=[bed_temperature_initial_layer_single] EXTRUDER_TEMP=[nozzle_temperature_initial_layer] SET_RETRACTION RETRACT_LENGTH=[retraction_length] RETRACT_SPEED=[retraction_speed] UNRETRACT_EXTRA_LENGTH=[retract_restart_extra] UNRETRACT_SPEED=[deretraction_speed] RESPOND TYPE=command MSG="Retraction length set to [retraction_length]mm" RESPOND TYPE=command MSG="Retract speed set to [retraction_speed]/[deretraction_speed]mm/c"
   ```

# !!!I FOUND MISTAKE!!!
Write me in telegram or make an __issue__ her
