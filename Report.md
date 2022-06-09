# Report

## Decisions on Diagrams

### Domain Diagram

I decided to split my diagram up into two separate sections, focussing on the standard user side of the program and the ReST user side of the program in two separate instances. This isolates all important information and gives a clear indication of how a station manager and client would make use of the program. For the standard user/customer side of the diagram, I decided to focus mostly on the ticket object creation process, letting the respective DAO handle calculations and such. The ReST side was also quite similar in design, with CRUD operations being dealt with by the DAO, with the addition of modifying a station going to a Station.JSP which would allow you to assign and create TicketMachines to the respective station.

The end product completely met what I gad set out to achieve and functions mostly the same, with only the minor change in creating a ticket and ticket machine. Where a ticket object is inputted to encode it and gets output whenever the validation function is called. As for the creation of a machine, it makes use of a station object and its data to uniquely create an associated machine for the station

### Use-Case

The use cases are all divided into 4 different instances, that of the ticket, gate, customer and ReST user. This allows me to isolate the functionality of each part based on the specific roles of characters. For instance, the customer represent actions that are needed to both make use of the ticket machine and ticket gate, specifically the input of data. Whereas the ReST user is responsible for everything that consists of creating Stations and their respected tickets which will directly affect the user.

The use cases implemented properly, other than the final delete all stations case. As it sometimes causes the program to crash whenever stations have associated ticket machines still in them I was, unfortunately, unable to properly fix this, but as it is not in our TODO tasks, I decided to keep things at this point.

## Rationale for test plan

I decided to use my use cases as a basis and backbone to create my test plan, emphasizing focus on tests that directly influence the end result of each jsp. I tested both successful and purposefully unsuccessful test to ensure that my program was working as intended at met the criteria of my Use cases. These test are especially extensive in the Customer side where they are responsible for inputting data as it proves to be the area where the most error could occur.

## Critical evaluation of code

## Model

![Ticket](assets\Ticket.png)

I appended the standard model of a ticket to ensure that it would be suitable for use on my gate. By adding these extra fields I can easily check whether the destination is correct on arrival and assign rate and cost after calculating.

## TicketMachine

![CalculatePrice](assets\CalculatePrice.png)

The price calculator makes use of the associated DAO to effectively calculate the ticket cost. It starts with working out the number of zones travelled by taking the absolute value of the start station- end zone, ensuring that even if the value is 0 that customers are charged a base rate. Afterwards, the zones travelled is multiplied by the base cost, which is determined by seeing if the time of day is peak or offpeak prices.

![RegEx](assets\RegEx.png)

To ensure that the inputted credit card is a valid format I have made use of a regex pattern. It starts by compiling the pattern and matching the inputted user string, successfully encoding the ticket if the payment is valid.

## TicketGate

![CheckValid](assets\CheckValid.png)

The gate, after un-marshalling the ticket uses 3 checks to ensure that it is valid. Firstly seeing if the ticket has been purchased within a 24-hour time span. Secondly, ensuring that the hash is proper and valid, meaning the values in the ticket have not been tampered with. Lastly ensuring that the ticket is used at the right station. All of which are required to have passed in order for the gate to Open

## ReST

![AddTicket](assets\AddTicketMachine.png)

This action allows users to create a ticket machine for the corresponding station it is at, making sure that it is unique and the only one of its kind. It accomplishes this by creating a Ticket Machine object and then using the DAO to save it to the system.
