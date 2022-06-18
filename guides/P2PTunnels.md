# How to Use P2P Tunnels in Applied Energistics 2
AE2 (short for Applied Energistics 2) is a great mod for storing your items, autocrafting and much more. However once you'll get a big ME system going, you'll start running into some issues with **channels**.

## Channels 
Most of the things you can connect to your network (interfaces, ME Drives, ME chests, terminals, busses, crafting multiblocks etc.) use up a channel each, and channels are provided from your ME contorller multiblock. These blocks also do transmit channels themselves. You can carry 8 channels with most cables, but dense cables allow you to carry 32.

![2022-06-18_10 54 16](https://user-images.githubusercontent.com/100072467/174430656-b3ce42a5-1a8f-4c33-8601-edf96c5d9e14.png)
We have 3 ME interfaces on the right, so they're getting 3 channels in total.

Channels are provided to blocks from the shortest path possible, so make sure your cable lines aren't touching each other, since that might cause you some troubles in the long run.

![2022-06-18_10 58 49](https://user-images.githubusercontent.com/100072467/174430682-33688f0f-b8f1-4f58-8872-d38801c06e62.png)

**Colored pipes** don't connect to different colored pipes but do connect to fluix/uncolored pipes. **Cable anchors** prevent cables from connecting from a specific place.

![2022-06-18_11 01 56](https://user-images.githubusercontent.com/100072467/174430704-fdee4dc1-19e4-4116-801c-1d286dd1a959.png)

These will help you manage your cables to some extend. But there is something much more powerful that you can use.

## The P2P Tunnel
P2P (stands for point-to-point) tunnels act like a link between two points connected with some cable. They can carry a certain thing like items, fluids, energy and even light. But most importantly, they can carry channels.

![2022-06-18_11 18 54](https://user-images.githubusercontent.com/100072467/174430735-4702ca6e-efb3-4847-9234-53a5ad52ea55.png)
Here, we have a P2P tunnel carrying the light of the torch on the left side to right side.

In order to function, they too need a channel each, but **they can't use the channels they get from the input side**, so you'll need to make sure there is a channel for each one given to them from the back. There is a misconception that they compress channels, but that's untrue. Instead, they carry channels with a channel cost.

![2022-06-18_11 09 47](https://user-images.githubusercontent.com/100072467/174430838-e95f390a-90c5-41cd-8d5e-1f855863871d.png)
Here, the channels are sent to the interfaces with P2P channels. The path channels take seems longer at first glance, but keep in mind that P2P tunnels are pretty much links between two points.

You'll either have these passing through your primary ME system, or you'll have a **subnetwork** for the middle part. If you go with the second option, which you usually will, you'll need to keep a few things in mind:

#### 1) Make sure you don't exceed the channel limit
Depending on how many channels you wanna be using, you might want to add an ME controller or two to you subnetwork. The subnetwork is seperated from your main network, so you're free to use them. A network without any ME controllers is considered **Ad-Hoc**. It'll still work, but the channels you can use will be hard capped at 8, so make sure you don't exceed that limit.

![2022-06-18_11 31 00](https://user-images.githubusercontent.com/100072467/174431024-bcb86619-ca85-462a-8d48-3ad0158a5146.png)
Here, we have a total of 10 P2P tunnels (5 input and 5 output, outputs are off-screen), so we'll need to have a controller for our subnetwork too.

#### 2) Make sure your subnetwork is getting powered. 
To function, **every network needs power**. To supply your subnetwork with that much needed power, you can either:

a) plug your power to your ME controller.

b) use an *energy acceptor* and plug your power through it.
        
c) connect your subnetwork to your main with the use of **quartz fibers**. They'll let energy pass through but not channels, meaning two networks will still be seperated.

![2022-06-18_11 39 13](https://user-images.githubusercontent.com/100072467/174431059-8ae33362-3454-4afa-9196-2e799c247ede.png)
