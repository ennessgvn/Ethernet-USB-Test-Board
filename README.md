# Ethernet&USB TestBoard
Before giving the necessary details for this project, I would like to give basic information about Ethernet and USB signals. In line with this informations, you will be able to have information about differential pairs and routing in the project.

## Ethernet Protocol
Ethernet refers to the most common type of Local Area Network (LAN) in use today. A LAN is a network to which computers are connected, as opposed to a WAN that spans a wider geographical area.
As a wired protocol, the type of Ethernet cable you use is important. Most commonly, you'll see Category 5 (CAT5) Ethernet cables. CAT5 and CAT6 cables can handle 10MBit/s Ethernet respectively.
The number of pins of the Ethernet port varies according to the type of port used. The RJ45 port used in this project has 4 pairs of data pins and 2 pairs of LED pins.
![image](https://user-images.githubusercontent.com/79998692/189123300-06242c25-2a19-4362-a863-1c0b981f4d13.png)

## USB 
Universal Serial Bus (USB) is a two-wire serial communication protocol. It works with the PnP method. USB Protocol sends and receives data serially between host and external peripheral devices via D+ and D- data signal lines. USB has two data lines as well as VCC and GND pins to power the device. Since the USB Connector used in this project is USB 3.0, it has 9 pins.

![image](https://user-images.githubusercontent.com/79998692/189124449-0ba842e6-381e-435e-8163-249e13269cec.png)

Since the USB Connector used in this project is USB 3.0, it has 9 pins. Two pairs of these pins are used for high-speed communication, while one pair is used for low-speed communication, which is also used in USB 2.0.

## Details of Project
There are 8 Ethernet ports, 1 USB port, 1 Management and console port within the project. The data taken from a 100 pin socket with a flex cable coming from the motherboard is distributed to the ports in accordance with the line impedances. The required stack-up design was completed in accordance with the Ethernet (100 ohm) and USB (90 ohm) impedances.

![LAYER STACK MANAGER](https://user-images.githubusercontent.com/79998692/189530135-001ca309-5c1d-409b-93d5-dd005f0f6a54.PNG)

As can be seen in the picture, in this 4-layer designed card, the 1st and 4th layers are used for signal, while the 2nd and 3rd layers are reserved for GND. The prepreg material and core thickness were determined according to the impedance values specified for Ethernet and USB. In line with these determined values, single pair and differential pair thicknesses (W1) and trace gap determined. 

## Shematic Circiut of Project

The circuit drawn on two different schematic pages shows the connection of the 100 pin socket to the Management, USB and console ports on the first page. Each signal type was labeled (NetClass) for ease of tracking connections during drawing. If these tags contain differential paths, they are paired with the differantial pair command. 

![1 sayf2](https://user-images.githubusercontent.com/79998692/189530705-dfee25e1-2713-44d9-bda7-ae3a61c2d99a.PNG)

The second page contains the schematic representation of the Ethernet connectors. Data and led pairs coming from the 100 pin socket are transferred from the first schematic page to a main schematic page with the harness method. On the main schematic page, two diagrams are drawn representing the two schematic pages. With the pin-to-pin connection between these schemes, a connection can be made from a pin on page 1(USB,MNG,Console) to a connector on page 2 (ETH).

![main](https://user-images.githubusercontent.com/79998692/189537733-44077576-8ec1-41c2-8c35-630bdd56b39c.PNG)

With this Harness method, connection can be more effective. In addition, it provides the opportunity to follow the signal more easily and troubleshoot the schematic.

![harness](https://user-images.githubusercontent.com/79998692/189537860-ca30cb2c-0a39-4a25-8ff8-a323bf291739.PNG)

## PCB Layout of Project

In the PCB design, which is the next stage of the project whose schematic design has been completed, first of all the elements are placed on the board according to certain criteria. These criteria are that the connectors should face the long edge of the board and their inputs should face out.

![pcb2](https://user-images.githubusercontent.com/79998692/189538159-559406fe-cd01-4366-a7bb-99d28034d4f2.PNG)

After the elements were placed, it was determined which signal pairs would be drawn on which layer. In this direction, the differential pairs under the socket were drawn from the Bottom layer, and the differential pairs above the socket were drawn from the Top layer. In this way, free space in the card was gained and it allowed to place more vias in these spaces. The spacing of the drawn differential lines was kept at a certain distance and the lines were isolated from each other from noise. Line equalization process was performed for ethernet signals whose drawings were completed. With this operation, the simultaneous transmit and receive simultaneously required for ethernet was achieved. GND polygons were placed in the 2nd and 3rd layers on the line where the drawn lines coincide. More vias were placed in the gaps in order to distribute the GND more homogeneously.

![pcb1](https://user-images.githubusercontent.com/79998692/189538677-c77b4a3b-638f-4b25-aa1d-1cfab50a3320.PNG)

![image](https://user-images.githubusercontent.com/79998692/189538743-3ad00357-eefc-4bd2-a12a-315ee137ba6f.png)

