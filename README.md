# Raspberrypi
first usage

#connecting ultrasonic seensor to raspberry pi

#using python in raspberry pi:
pi@raspberrypi:$ sudo python
>>>import RPi.GPIO as GPIO #in order to use the RPI GPIO pins
>>>import pigpio
>>>import time
>>>GPIO.setmode(GPIO.BCM) #in order to use the GPIO pins as GPIO18 according to the raspberry pinout
>>> trig=4
>>>echo=17
>>>GPIO.setup(4, GPIO.OUT)
>>>GPIO.setup(17, GPIO.IN)
>>>GPIO.output(trig,True)
>>>time.sleep(0.0001) #given time is in seconds
>>>GPIO.output(trig, False)
>>>while GPIO.input(echo)==False
>>>start= time.time()
>>>while GPIO.input(echo)==True
>>>end= time.time()
>>>sig_time=end-start
>>>distance=sig_time/0.000058
>>>print('Distance: {} centimeters'.format(distance)) #display distance in cm if needed in inches divide sig_time by 0.000148
>>>GPIO.cleanup() #clean all GPIO pins




#connecting servo to raspberry pi
#there are two ways to do this either by installing and importing pigpio library or by writing a fuction and making use of the frequency and cycle of the pwm signal given by the raspberry pi
#knowing that GPIO18 is the only pin able to send a pwm signal for this reason we need to install the pigpio library in order to use more than one servo on different pins
/* 
in order to import the pigpio library we should pass by the following:

pi@raspberrypi:$wget abyss.co.uk/rpi/pigpio/piggpio.zip
pi@raspberrypi:$unzip pigpio.zip
pi@raspberrypi:$cd PIGPIO
pi@raspberrypi:$make
pi@raspberrypi:$sudo make install


pi@raspberrypi:$pigpiod
pi@raspberrypi:$import pigpio
>>>pi=pigpio.pi()
>>>pi.set_servo_pulsewidth(18, 800)
>>>pi.set_servo_pulsewidth(18, 1500)  // just to center the servo

*/
pi@raspberrypi:$ sudo python
>>>import RPi.GPIO as GPIO #in order to use the RPI GPIO pins
>>>import pigpio
>>>import time
>>>GPIO.setmode(GPIO.BCM) #in order to use the GPIO pins as GPIO18 according to the raspberry pinout

#function to set angle at the desired position

>>>def SetAngle(angle):
>>>	duty = angle / 18 + 2
>>>	GPIO.output(03, True)
>>>	pwm.ChangeDutyCycle(duty)
>>>	sleep(1)
>>>	GPIO.output(03, False)
>>>	pwm.ChangeDutyCycle(0)

#calling the function

>>>SetAngle(90) 
