# Timmy_Project
#!/usr/bin/env pybricks-micropython
from pybricks.hubs import EV3Brick
from pybricks.ev3devices import (Motor, TouchSensor, ColorSensor,
                                 InfraredSensor, UltrasonicSensor, GyroSensor)
from pybricks.parameters import Port, Stop, Direction, Button, Color
from pybricks.tools import wait, StopWatch, DataLog
from pybricks.robotics import DriveBase
from pybricks.media.ev3dev import SoundFile, ImageFile
ev3 = EV3Brick()
m_right = Motor (Port.A)
m_left = Motor (Port.B)
head = UltrasonicSensor (Port.S3)
def Move (sec):
    sec = sec * 1000
    m_right.run(sec)
    m_left.run(sec)
    wait(sec)
def Turn (sec):
    sec = sec * 1000
    m_right.run(sec)
    m_left.run (-1 * sec)
    wait (sec)
def Looki ():
    diz = head.distance()
    Move ((diz-200)/400)
while True:
    Turn(1.6)
    Looki()
