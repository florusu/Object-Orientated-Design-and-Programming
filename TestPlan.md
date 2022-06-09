# Test Plan

|#| Name|Purpose|Expected|Actual|
|---|---|---|---|---|
|1|getCurrentStationName|To get current station name from the ticket machine config based on corresponding uuid|It will get the correct station name and display it|Displays null value in current station|
|2|getCurrentStationNameFix|Display Station Name based on uuid instead of null value by correctly configuring ticket machine before|Display correct Station Name|Displays set Station Name|
|3|getCurrentStationZone|Get the corresponding station zone from the uuid that was set in ticket config|Displays the corresponding station Zone|Displays the correct station Zone|
|4|listDestinationZones|Creates a list of destination Zone buttons based on existing data|Creates and displays a list of buttons|Creates a list of destination zone buttons|
|5|selectDestinationZone|Click a destination zone button to change url with corresponding zone information|Adds the zone information to url|Adds the selected zone number to the url|
|6|stationListDropbox|Create a dropdown that is populated by all stations according to existing data|Creates a dropbox that lists stations|Creates a dropdown that lists stations|
|7|populateDropdown|When zone button is clicked, populate dropdown with corresponding zones|Correctly Populates Dropdown according to selected zone|Does not display the proper station according to zone|
|8|populateDropdown|Populate dropdown based on zone input through finding the station list values by zone value|Populates dropdown based on destination zone|Populates properly based on Zone input|
|9|creditCardCheckTrue|Compare and the input on the credit field to a regex pattern and see if valid|Return True if the entered value is correctly formatted|Returns True for inputted value|
|10|creditCardCheckFalse|Compare and the input on the credit field to a regex pattern and see if invalid|Return False if the entered value is incorrectly formatted|Returns False for inputted value|
|11|calculatePriceZones|Minus destination zone from starting zone|Produce a positive value to be used for calculation|Produced a positive or negative value depending on zones|
|12|calculatePriceZonesFix|Use an absolute to minus destination zone from starting zone|Produce a positive value to be used for calculation|Produced a positive value|
|13|calculatePriceTicket|Multiply zones travelled value by rate to get price|produces the proper price of a ticket|Produced appropriate ticket price|
|14|generateTicket|Produces a valid ticket to be used for ticketGate|Produces a ticket with all fields filled|Produces a valid ticket|
|15|getArrivalStation|Get the arrival station name from button input|get a valid station name and display it|displays the station name|
|16|getArrivalStationError|Choose invalid station name|The station name will be invalid|Valid Station returns false|
|17|decodeTicket|Get the ticket XML data from user and decode data|decode the ticket data|decodes ticket XML data|
|19|validateDate|check the arrival time and check against the time the ticket was issued time|Time will be valid if within 24 hours|Time is valid|
|20|validateStation|get the destination station from the ticket and check if it matches the arrival station|Stations match|validStation is true|
|21|validateStationError|get the destination station from the ticket and set a different station as arrival station|Stations don't match|validStation is false|
|22|openGate|If validStation, validDate and validFormat are true and open gate|Gate will open|Gate opens|
|23|openGateError|If validStation, validDate and validFormat are false see if gate opens|Gate will remain closed|Gate opens|
|24|openGateErrorFix|If validStation, validDate or validFormat are false see if gate opens by checking if even one value is false|Gate will remain closed|Gate is closed|
|25|changeConfig|Set the ticketMachine to the one associated by the provided UUID|The ticket machine is set to the selected one| The ticket machine is set based on uuid|
|26|createStation|Creates a new station and its associated name and value|Creates a new station with a name and zone|Creates a new station with a name and zone|
|26|createTicketMachine|Adds a new ticket machine to the station|Creates a new ticket machine for the station| Creates a new ticket machine for the station|
|27|createMachineUUID|Assigns a UUID for every new station created|Create a unique UUID for  machine|Every new machine has a new UUID|
|28|updateStationName|Change the name of the station and assign it to new input|Changes the name of the selected station|Selected station named changed|
|29|updateStationZone|Change the zone of the station and assign it to new input|Changes the zone of the selected station|Selected station zone changed|
|30|deleteTicketMachine|Delete the ticket machine at the station by the UUID of the ticket machine|Deletes the selected ticket machine from the station|Deletes the selected ticket machine from the station|
