# Introduction

I found no EMS-like system to really satisfy my goals in terms of optimal use of solar panel energy in combination 
with two electric cars and a smart meter, but having no 'home battery'
One car, a Tesla, has a Tesla Wall Connector gen2, and the other car is a Mercedes EQ has an Easee charger, and 
I also have an Easee 'Equalizer' that is connected to the P1 port of the smart meter. Using the Equalizer provides
some of the functionality but I'm still sending a lot of solar power to the grid, or if I'm not, I'm drawing too
much power from the grid to get to the minimum of 5 or 6 amps per phase to get the car to charge in the first place.
I don't want to start bying other hardware or paying for all sorts of subscriptions and I also want to use my home
control device (LogicMachine5) to drive the automation because it is fully capable of doing it.

# Requirements

- do not overload the main fuse, taking into account power use by the rest of the house
- when plugged in, loads the car(s) to a level of, say, 60%, which is sufficient for daily use, preferrably when
  (grid sourced) electricity is cheaper
- as soon as the car(s) reach 60%, only load when there is solar energy available with as little as additional
  grid electricity possible, but using all of the available solar energy
- allow exceptions based on planning (from google agenda) or manual intervention to load the car to a high level by
  some date/time to cover larger distances. In case of manual intervention, this mode is automatically reset after
  one such load cycle

# Integrations needed

Integration platform will be a LogicMachine5 by Embedded Systems, used for home control via KNX (and other protocols).
It supports Modbus connections and API calls via http, therefor all needed integrations are possible.
Via the LM app on the phone, remote connection is possible in a secure way.

Integrations:

- Tesla car API (for start/stop loading and SoC)
- Mercedes car API (for SoC)
- Easee Charger (for Active Load Balancing, ie prevent the main fuse from blowing, and start/stop loading)
- Easee Equalizer (for reading values from the smart meter, thanks to its connection to the P1 port of the meter)
- SMA PV converters (I have two of those) for knowing exactly what solar power is available, since this the energy
  I want to use up completely, using only the 2 electric cars as buffer. With data from only the smart meter,
  it is not possible to know what the power is being drawn by: the cars (which can be controlled) or the household
  (which cannot be controlled).
- (future) Google agenda with information about what SoC is required basically for the next morning.

# EMS logic

This home brew 'EMS' (energy management system) should implement following logic:

- to be completed ...
