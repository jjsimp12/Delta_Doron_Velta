# These are  my Delta Doron Velta cfg's, if you wish to use them you will have
# to edit the printer.cfg file and delete some of my settings in the SAVE_CONFIG
# section which looks simular to the below:
# 
# #*# <---------------------- SAVE_CONFIG ---------------------->
# #*# DO NOT EDIT THIS BLOCK OR BELOW. The contents are auto-generated.
# 
# Delete #*# [delta_calibrate] and anything in its section.
# Also delete #*# [bed_mesh default] and anything under its section. Bed mesh
# and sensors are a pain on this build.
# 
# After you have removed these sections and headers run the
# ENDSTOP_PHASE_CALIBRATE. Once this is done re-run
# DELTA_CALIBRATE METHOD=manual. Do the paper leveling at all the points
# it travles and when it is complete do a SAVE_CONFIG.


# To config PID for bed and extruder:

  PID_CALIBRATE HEATER=heater_bed TARGET=60 [WRITE_FILE=1]
  
  PID_PROFILE SAVE=heater_bed HEATER=heater_bed
  
  PID_CALIBRATE HEATER=extruder TARGET=210 [WRITE_FILE=1]
  
  PID_PROFILE SAVE=extruder HEATER=extruder


# Current OrcaSlicer start and end:

  Start Gcode：
    G21
    G90
    M82
    G28 ; home all axes
    M140 S[first_layer_bed_temperature]
    M104 S[first_layer_temperature] T0
    G1 F3000 Z1
    G1 X-78 Y0 Z0.4
    M107 T0
    M109 S[first_layer_temperature] T0
    M190 S[first_layer_bed_temperature]
    G92 E0
    G3 X0 Y-78 I78 Z0.3 E30 F2000
    G92 E0
  
  End Gcode：
    M107
    M104 S0
    M140 S0
    G92 E1
    G1 E-1 F300
    G28 X0 Y0
    M18 S180 ;disable motors after 180s

  # To install Kiauh and Git

  sudo apt update && sudo apt full-upgrade && sudo apt-get install git -y

  cd ~ && git clone https://github.com/dw-0/kiauh.git
  ./kiauh/kiauh.sh

