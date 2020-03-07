# SpotMicroAI

Hello, I'm Fran and i'm going to guide you in the steps needed to make your SpotMicroAI software autobootable.

We will cover too the configuration file that belongs to your SpotMicroAI, the place where you map the I2C address and your servos.

## AutoUpdate

Check at the run script located at: https://gitlab.com/custom_robots/spotmicroai/basic-runtime/-/blob/master/run_spotmicroai.sh

Notice SpotMicroAI will always update its sofware on every boot if wifi is available.

This will not wipe out your configuration file, just the OS will have the latest updates.

# Configuration file

Is time for you to setup your mappings and i2c address. Edit the file **~/spotmicroai.json** to do so.

You can use FileZilla and do it locally or nano editor.

```
ssh pi@192.168.1.XX

nano ~/spotmicroai.json
```

The default config file will be generated from the source: https://gitlab.com/custom_robots/spotmicroai/basic-runtime/-/blob/master/spotmicroai.default, which assume you have 2 PCA9685 boards, 1 LCD 16x2 I2C screen and the GPIO 17 port mapped to the 0E port in the PCA9685 boards as explained in the Electronics repository at https://gitlab.com/custom_robots/spotmicroai/electronics

For safetyness, all your rest_angle values for the servos are set up at 90 degree in the default configuration

You can validate your json with the following page https://jsonlint.com/

## TIP

You can use "i2cdetect -y 1" tool to identify your i2c addresses


# Calibration

* To calibrate SpotMicroAI you may have the main software not running and reboot, so the GPIO configuration will reset.

* Alternativelly you can just unplug the GPIO17 cable and reboot.

![spotmicroai_compass.jpg](spotmicroai_compass.jpg)

The calibration tool will help you to find the sweet spot, you can navigate there your config file and test each servo to get to the final calibration.

```
ssh pi@192.168.1.XX

cd ~/spotmicroai/calibration

./calibration.sh
```

![calibration-tool](calibration-tool.JPG)

## What is rest position?

![spotmicroai_rest_angle_shoulder_and_leg.jpg](spotmicroai_rest_angle_shoulder_and_leg.jpg)

![spotmicroai_rest_angle_leg_and_feet.jpg](spotmicroai_rest_angle_leg_and_feet.jpg)

# When you have done the calibration

* Activate your spot
* Activate your remote controller
* Press Start (XBOX controller) u Options (PS4 remote controller) to power up your servos
* Press the buttons!

# Run the software automatically on boot

Just enable it using the following script:

```
ssh pi@192.168.1.XX

cd ~/spotmicroai/systemd/
./enable_spotmicroai_on_boot.sh
```

Note you also have the "disable_spotmicroai_on_boot.sh" script to disable the auto-boot

## Check the logs

You can check the logs with the daemon.log if you enabled autoboot or the log folder in spotmicroai

```
tail -f /var/log/daemon.log
```
or
```
tail -f ~/spotmicroai/logs/SpotMicroAI.log
```

# How to debug a problem

Look up in this page to see how to check the logs, if there are errors they are pretty self explanatory.

Also you can ask us in Slack: https://spotmicroai-inviter.herokuapp.com/

If you like to test components individually check the folder **~/spotmicroai/integration_tests** for scripts to check the PCA9685 boards, the LCD screen, the GPIO...