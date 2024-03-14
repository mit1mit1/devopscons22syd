## Lots and Lots of Little (or not so little) things (managing scale and hyperscale on the edge (or edges)) - Peter Lees, Head of Solutions and Innovation, Asia-Pacific at Suse

Today is SUSE's 30th birthday. Please visit their birth city, Nuremberg, a cool medieval city.

(Editor's note: IoT is related to edge - see https://www.machinemetrics.com/blog/edge-devices)

We have lots and lots of devices sitting on the edge - what are they, how can we use them.

What is the software and hardware challenges introduced with edge computing at scale?

The reality of edge scale is that there is a huger and huger number of edge devices, they grow exponentially as non edge grow linearly.

Edge definition:

Near edge: 10s to 100s of devices close to data centre.

Far edge: 1000s of devices near a node point.

Tiny edge: many many devices, smart lightbulbs and sensors and stuff, in the middle of anywhere.

E.g.: Home Depot (American Bunnings minus the sausage) has 2300 stores, across many locations far from the data centre. Each store does not have an IT person, so everything needs to work with nothing more than "have you tried turning it off and on".

Solution: cashier checkouts are connected to servers in each site, which is a box with Kurbernetes installed. Send the box to the location and tell the store to plug it in and turn it on, and remote control takes over.

E.g: Wind farms. Each windmill has its own 'data centre' on board, but has to connect and mesh with all the others, but then also has to connect to the real data centre, which is remote.

Edge means: decisions have to be made in the software locally. In this case, the individual windmill decides what to do so it works in sync with the others with local execution.

E.g.: Dairy farms need a bunch of automation stuff to track air quality, etc., etc., and needs to be installable by a farmer in a farm.

Mining prone trucks in remote sites need to stay out in the sticks for ages without going back in for updates. They need to make updates in the field easily.

E.g.: Garbage trucks have cameras on the arms to make sure they aren't chucking the bins into the trucks too. Video is recorded, AI on the truck tells if the bin was chucked in and automatically orders a new bin. All the processing is happening locally, in the truck.

E.g.: U2 spy plane, produced from the 50s to the 80s but still running and being updated. Needs to be autonomous inside the machine, but also needs to be updated. Again, the software is crucial as data needs to be interpreted locally and acted on rapidly (readjust camera super rapidly etc.).

E.g.: Drones for building maintenance work in Hong Kong. Drone should be able to fly around and identify using its own AI which bits of the building actually need work. And of course, the drone also will need updating.

E.g.: Medical devices. Infrequently updated hardware, hard to access places, so need to update software on the edge.

E.g.: Bottle factory. Kurbernetes used to green test, make sure roll back appropriately if software updates fail.

All these things are cloud native, even if they aren't speaking to the cloud _per se_.

E.g.: Satellite - small as possible, potato in space. Can't send a technician up there.

E.g.: Telco company wanted to redo their broadband system. Near edge - data centre. Far edge - things on side of the road that run things every few hundred kilometres. Technician should only have to plug in a box at each thing on the side of the road.

## Common themes of edge technology:

- IT expertise is not available at location
- Small footprint required, and/or tight power and space budgets
- Non-stop operation
- Physically hostile environment
- Maximised automation
- Hardware configuration is the last mile

## SUSE

SUSE is all open source stuff.

They have stuff for home automation with raspberry pies.
