This app lets you create cars

## Table of Contents

- [Required-Technologies](#required-technologies)
- [Installation](#installation)
- [Usage](#usage)
- [Code Snippet](#code-snippet)
- [Features](#features)
- [Future-Features](#future-features)
- [License](#license)
- [Technologies](#technologies-used)
- [Credits](#credits)
- [Contact Me](#contact-me)

## Required Technologies

This project requires node.js and its included npm package manager.\
You can go to <a href="https://nodejs.org/en/download/package-manager">this</a> website to download node.js and npm. Just follow node's included download instructions!

## Installation

Once the files are downloaded onto your machine open the project folder in your preferred terminal.\
To install the necessary dependencies run the "npm i" command to install the required files. and then run "npm run start" to run the vehicle creator!

## Usage

Once the code is started you'll be prompted with choices to create a new vehicle or select an existing one. Creating a new vehicle lets you create a vehicle ranging from types Car, Truck, Motorbike. Choosing one of these types will then prompt you with questions helping you to create a complete vehicle. Selecting the select and existing vehicle option will have you select an already created vehicle from a list of existing vehicles.

Once a vehicle has been selected or created it will take you to the actions menu. This menu lets you perform various actions on your vehicle. You can use the arrow keys to scroll through the menu. There are vehicle specific actions like "Towing" and "Wheelies" that are specific to the Truck and Motorbike respectively. At the bottom there is an option to select or create another vehicle which will take you back to the first menu as well.

## Code Snippet

This bit of code is used to called when "Tow Vehicle" is selected in the vehicle actions menu. A prompt is started to choose a vehicle to tow. If the same vehicle is selected then the function will break as a truck cannot tow itself. If the vehicle that is trying to be towed is a Car or Motorbike then execute the tow function located within the Truck.ts class.

```
findVehicleToTow(truck: Truck): void {
    inquirer
      .prompt([
        {
          type: 'list',
          name: 'vehicleToTow',
          message: 'Select a vehicle to tow',
          choices: this.vehicles.map((vehicle) => {
            return {
              name: `${vehicle.vin} -- ${vehicle.make} ${vehicle.model}`,
              value: vehicle,
            };
          }),
        },
      ])
      .then((answers: {vehicleToTow: Car | Motorbike | Truck}) => {
        console.log(answers)

```

## Features

Features include:

- Being able to create Cars, Trucks, and Motorbikes
- A menu for selecting existing vehicles
- Vehicle specific actions. Like towing for trucks and Wheelies for motorcycles
- Being able to change the speed of vehicles in the actions menu
- Being able to turn vehicles in the actions menu

## Future Features

Features that may be implemented in the future include:

- Being able to save created cars to a file
- Loading created cars from a save file
- More in depth features.
- Adding miles traveled to cars as well as car condition

## License

Licensed under the MIT license.

## Technologies Used

<ul>
<li>Node.js (for installing packages as well as building and running code).</li>
<li>Inquire.js (for question prompts).</li>
<li>Visual Studio Code (for writing code).</li>
<li>Mozila Web Docs and W3 Schools (for getting help with JavaScript).</li>
</ul>