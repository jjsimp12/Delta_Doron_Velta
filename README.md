# Klipper-Backup 💾 
Klipper backup script for manual or automated GitHub backups 

This backup is provided by [Klipper-Backup](https://github.com/Staubgeborener/klipper-backup).

These are  my Delta Doron Velta cfg's, if you wish to use them you will have
to edit the printer.cfg file and delete some of my settings in the SAVE_CONFIG
section which looks simular to the below:

#*# <---------------------- SAVE_CONFIG ---------------------->
#*# DO NOT EDIT THIS BLOCK OR BELOW. The contents are auto-generated.

Delete #*# [delta_calibrate] and anything in its section.
Also delete #*# [bed_mesh default] and anything under its section. Bed mesh
and sensors are a pain on this build.

After you have removed these sections and headers run the
ENDSTOP_PHASE_CALIBRATE. Once this is done re-run
DELTA_CALIBRATE METHOD=manual. Do the paper leveling at all the points
it travles and when it is complete do a SAVE_CONFIG.


