# ElenNu Binding

Scrapes the Web-site https://elen.nu after estimated prices, prices for next day will be shown from 15:00.
This binding delivers the prices for actual time-delivered electricity regarded to the Swedish electricity-spot-market. ( Nordpool )

Depending on whether the configuration-parameters as checkTimeInterval and ascendingOrderXJson is set, and if they are, and how they are configured, the different switches Block X will be set to ON/OFF.

It is possible to view current prices for each configured asOX, use Channels like: Price at asOX.
It is possible to view current prices for each hour, use Channels like: Price at Hour XX.

## Supported Things

This binding is not connected to any device, it use the Web.

## Discovery

Discovery is not supported.

## Thing Configuration

This binding require 3 mandatory parameters:

| Parameter                | Description                                            | Type    |  Unit   | Default value | Example value |
|--------------------------|--------------------------------------------------------|---------|---------|---------------|---------------|
| url                      | Host name or IP address                                | String  | ---     | ---           | https://elen.nu/dagens-spotpris/se3-stockholm/#dagens-timpriser   |
| checkTimeInterval        | Check time interval regarded to eventual desired order | Integer | Seconds | 60            | 60            |
| ascendingOrderXJson      | Describing desirable blocks                            | String  | ---     | --            | {"asO0":"12-0-0","asO1":"12-1-0","asO2":"12-2-0","asO3":"12-3-0","asO4":"12-3-1","asO5":"12-4-0","asO6":"12-4-1","asO7":"12-5-0","asO8":"12-5-1","asO9":"12-6-0","asO10":"12-7-0","asO11":"12-8-0"} 

Url's regarded to different regions in Sweden:
https://elen.nu/dagens-spotpris/se1-lulea/#
https://elen.nu/dagens-spotpris/se2-sundsvall/# 
https://elen.nu/dagens-spotpris/se3-stockholm/#
https://elen.nu/dagens-spotpris/se4-malmo/#


Parameter ascendingOrderXJson describes which scheme to use.
Example.
Block 24 is the entire day
24-0-0 is the cheapest hour,
24-1-0 is the second cheapest hour and so on.

Block 12 is divided in 12 parts with 2 hours in each part,
12-0-0 is the cheapest hours in part 0,
12-0-1 is the next cheapest hours in part 0,
12-1-0 is the cheapest hours in part 1 and so on.

Block 8 is divided in 8 parts with 3 hours in each part,
8-0-0 is the cheapest hours in part 0,
8-0-1 is the next cheapest hours in part 0,
8-0-2 is the third cheapest hours in part 0,
8-1-0 is the cheapest hours in part 1 and so on.

Block 6 is divided in 6 parts with 4 hours in each part,
6-0-0 is the cheapest hours in part 0,
6-0-1 is the next cheapest hours in part 0,
6-0-2 is the third cheapest hours in part 0,
6-0-3 is the fourth cheapest hours in part 0,
6-1-0 is the cheapest hours in part 1 and so on.

Block 4 is divided in 4 parts with 6 hours in each part,
4-0-0 is the cheapest hours in part 0,
4-0-1 is the next cheapest hours in part 0,
4-0-2 is the third cheapest hours in part 0,
4-0-3 is the fourth cheapest hours in part 0,
4-0-4 is the fifth cheapest hours in part 0,
4-0-5 is the sixth cheapest hours in part 0,
4-1-0 is the cheapest hours in part 1 and so on.

Block 2 is divided in 2 parts with 12 hours in each part,
2-0-0 is the cheapest hours in part 0,
2-0-1 is the next cheapest hours in part 0,
2-0-2 is the third cheapest hours in part 0,
2-0-3 is the fourth cheapest hours in part 0,
2-0-4 is the fifth cheapest hours in part 0,
2-0-5 is the sixth cheapest hours in part 0,
2-0-6 is the seventh cheapest hours in part 0,
2-0-7 is the eight cheapest hours in part 0,
2-0-8 is the ninth cheapest hours in part 0,
2-0-9 is the tenth cheapest hours in part 0,
2-0-10 is the eleventh cheapest hours in part 0,
2-0-11 is the twelfth cheapest hours in part 0,
2-1-0 is the cheapest hours in part 1 and so on.

## Channels

| Channel Name              | Channel Type   | Description                                                  |
|---------------------------|----------------|--------------------------------------------------------------|
| Average price             | String         | Todays average price, containing all hours                   |
| Calculated Average Price  | String         | Calculated average price, containing hours for selected asoX |
| Block 24                  | Switch         | Switch for block 24     |
| Block 12                  | Switch         | Switch for block 12     |
| Block 8                   | Switch         | Switch for block 8      |
| Block 6                   | Switch         | Switch for block 6      |
| Block 4                   | Switch         | Switch for block 4      |
| Block 2                   | Switch         | Switch for block 2      |
| Price at Hour 00          | String         | Todays price at hour 0  |
| Price at Hour 01          | String         | Todays price at hour 1  |
| Price at Hour 02          | String         | Todays price at hour 2  |
| Price at Hour 03          | String         | Todays price at hour 3  |
| Price at Hour 04          | String         | Todays price at hour 4  |
| Price at Hour 05          | String         | Todays price at hour 5  |
| Price at Hour 06          | String         | Todays price at hour 6  |
| Price at Hour 07          | String         | Todays price at hour 7  |
| Price at Hour 08          | String         | Todays price at hour 8  |
| Price at Hour 09          | String         | Todays price at hour 9  |
| Price at Hour 10          | String         | Todays price at hour 10 |
| Price at Hour 11          | String         | Todays price at hour 11 |
| Price at Hour 12          | String         | Todays price at hour 12 |
| Price at Hour 13          | String         | Todays price at hour 13 |
| Price at Hour 14          | String         | Todays price at hour 14 |
| Price at Hour 15          | String         | Todays price at hour 15 |
| Price at Hour 16          | String         | Todays price at hour 16 |
| Price at Hour 17          | String         | Todays price at hour 17 |
| Price at Hour 18          | String         | Todays price at hour 18 |
| Price at Hour 19          | String         | Todays price at hour 19 |
| Price at Hour 20          | String         | Todays price at hour 20 |
| Price at Hour 21          | String         | Todays price at hour 21 |
| Price at Hour 22          | String         | Todays price at hour 22 |
| Price at Hour 23          | String         | Todays price at hour 23 |
| Price at asO0             | String         | Todays price at asO0    |
| Price at asO1             | String         | Todays price at asO1    |
| Price at asO2             | String         | Todays price at asO2    |
| Price at asO3             | String         | Todays price at asO3    |
| Price at asO4             | String         | Todays price at asO4    |
| Price at asO5             | String         | Todays price at asO5    | 
| Price at asO6             | String         | Todays price at asO6    |
| Price at asO7             | String         | Todays price at asO7    |
| Price at asO8             | String         | Todays price at asO8    |
| Price at asO9             | String         | Todays price at asO9    |
| Price at asO10            | String         | Todays price at asO10   |
| Price at asO11            | String         | Todays price at asO11   |
| Price at asO12            | String         | Todays price at asO12   |
| Price at asO13            | String         | Todays price at asO13   |
| Price at asO14            | String         | Todays price at asO14   |
| Price at asO15            | String         | Todays price at asO15   |
| Price at asO16            | String         | Todays price at asO16   |
| Price at asO17            | String         | Todays price at asO17   |
| Price at asO18            | String         | Todays price at asO18   |
| Price at asO19            | String         | Todays price at asO19   |
| Price at asO20            | String         | Todays price at asO20   |
| Price at asO21            | String         | Todays price at asO21   |
| Price at asO22            | String         | Todays price at asO22   |
| Price at asO23            | String         | Todays price at asO23   |


## How to use the binding!

The purpose of this binding is to retrieve and sort out the cheapest hours of the day for electricity in ascending order.
One must use Rules or the like to make decisions to handle delivered information from the binding.

Best result will be if the binding is started at at any full hour. It will then do a scrape and check regarded to configured checkTimeInterval.

Rule examples, where I let the binding handle an Nexa switch connected to a Tellstick Duo.

Rule_ElenNu_Block12_On

configuration: {}
triggers:
  - id: "1"
    configuration:
      itemName: ElennuBinding_Block12
      state: ON
    type: core.ItemStateChangeTrigger
conditions: []
actions:
  - inputs: {}
    id: "2"
    configuration:
      command: ON
      itemName: DEVICENexaEYCR2300Flakt_Switch
    type: core.ItemCommandAction


Rule_ElenNu_Block12_OFF

configuration: {}
triggers:
  - id: "1"
    configuration:
      itemName: ElennuBinding_Block12
      state: OFF
    type: core.ItemStateChangeTrigger
conditions: []
actions:
  - inputs: {}
    id: "2"
    configuration:
      command: OFF
      itemName: DEVICENexaEYCR2300Flakt_Switch
    type: core.ItemCommandAction
    