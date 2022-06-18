# How to use P2P tunnels in Applied Energistics 2
AE2 (short for Applied Energistics 2) is a great mod for storing your items, autocrafting and much more. However once you'll get a big ME system going, you'll start running into some issues with **channels**.

## Channels 
Most of the things you can connect to your network (interfaces, ME Drives, ME chests, terminals, busses, crafting multiblocks etc.) use up a channel each, and channels are provided from your ME contorller multiblock. These blocks also do transmit channels themselves. You can carry 8 channels with most cables, but dense cables allow you to carry 32.

image

Channels are provided to blocks from the shortest path possible, so make sure your cable lines aren't touching each other, since that might cause you some troubles in the long run.

image

**Colored pipes** don't connect to different colored pipes but do connect to fluix/uncolored pipes. **Cable anchors** prevent cables from connecting from a specific place.

image

These will help you manage your cables to some extend. But there is something much more powerful that you can use.

## The P2P Tunnel
P2P (stands for point-to-point) tunnels act like a link between two points connected with some cable. They can carry a certain thing like items, fluids, energy and even light. But most importantly, they can carry channels.

image

In order to function, they too need a channel each, but **they can't use the channels they get from the input side**, so you'll need to make sure there is a channel for each one given to them from the back. There is a misconception that they compress channels, but that's untrue. Instead, they carry channels with a channel cost.

image

You'll either have these passing through your primary ME system, or you'll have a **subnetwork** for the middle part. If you go with the former, which you usually will, you'll need to keep a few things in mind:

#### 1) Make sure you don't exceed the channel limit
Depending on how many channels you wanna be using, you might want to add an ME controller or two to you subnetwork. The subnetwork is seperated from your main network, so you're free to use them. A network without any ME controllers is considered **Ad-Hoc**. It'll still work, but the channels you can use will be hard capped at 8, so make sure you don't exceed that limit.

image

Here, we have a total of 10 P2P tunnels (5 input and 5 output, outputs are off-screen), so we'll need to have a controller for our subnetwork too.

#### 2) Make sure your subnetwork is getting powered. 
To function, **every network needs power**. To supply your subnetwork with that much needed power, you can:
        a) plug your power to your ME controller.
        b) use an *energy acceptor* and plug your power through it
        c) connect your subnetwork to your main with the use of **quartz fibers**. They'll let energy pass through but not channels, meaning two networks will still be seperated.

image
