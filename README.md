
# Gepper Prinder - A Disruptive SaaS (Seasoning as a Service) Solution

## Introduction
IMAGINE, if you will, a pair of pepper grinders.
They are identical in every way, except for one thing, actually two things - rotating the top of one grinder clockwise will grind pepper on the other grinder, and rotating the top of the other grinder counter-clockwise will grind pepper on the first grinder.
And that's it. That's the whole idea.

The world yearns for a pepper grinder that can grind pepper on another pepper grinder.
And that's why I'm here.

## Why?
There are countless reasons why you might want to grind pepper on another pepper grinder.
IMAGINE, if you will, a dinner party.
You made Italian food, and you want to impress your guests.
For authenticity, you want TRUE Italian pepper on your pasta.
But you only have one pepper grinder.
What do you do?
You could grind the pepper on a plate and then transfer it to the grinder, but that's just not the same, the pepper is ONLY Italian if it's ground in ITALY.
That's where Pepper Grinder 2.0 comes in.
The other grinder was in Italy the whole time.
Your guests will be amazed at your attention to detail, as an Italian man, somwhere, is grinding pepper on your pasta.
Tears will roll down their faces as they taste the pepper, and they will thank you for your service.

## How?

Pepper Grinder 2.0 is a simple concept, but the implementation is a total pig.

### Hardware

The hardware is simple.
You need two identical pepper grinders.
That's it.

Well, you really need two stepper motors, two motor drivers (on the control board, and also force feeback for the grinding party), a microcontroller (with WiFi), a power source, encoders, pepper, a 3D printer, and a lot of time.
But that's REALLY it.

The hardware is split into a few parts:

#### Control Board & Electronics
Files are in the `electrical` directory.
Designed in KiCad, the control board is a simple design with a microcontroller, motor drivers, and a WiFi module.

#### Enclosure
Files are in the `mechanical` directory.
Currently, the enclosure is designed for a 3D printer, but it could be adapted for other manufacturing methods.
Designed in FreeCAD - all mechanical parts are considered in this section.

#### Bill of Materials
See the `BOM.md` file, which contains a list of all the parts needed.

### Software

The software is also simple, it is written in C++ and runs on the microcontroller.
The microcontroller is an ESP8266, and runs FreeRTOS.

#### Communication
We make the communication between the grinders as chatty as possible to ensure quality of grinding.
The data sent between the grinders are known as "pepper packets", and will ensure realtime grinding and accurate force feedback from the grindee to the grinding party.
GRPC is used for communication, as it is the most chatty protocol I could find (my boss uses WireShark in the office, and I just want him to notice the hopefully absurd amount of packets being sent).

## Future Augmentations

Currently, a pair of grinders must exist.
This may be a problem for the future, as when contracting Italian pepper grinding men, they may not be able to find the correct grinder in time, and the whole dinner party will be ruined.
A potential solution is to have them work a single grinder, and time division multiplex the grinding among all other grinders in the grinding pool.
This will require a central server to manage the grinding, and a network connection to each grinder, but it will be worth it for the authenticity.

Since a network connection is required, we should make sure that the grinders are secure - salting the pepper packets is a must.

We could also add a feature to grind salt on the other grinder, but that's a feature for Pepper Grinder 3.0.

