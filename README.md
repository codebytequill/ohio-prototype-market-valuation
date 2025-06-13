Real Estate Valuation & Prospecting Tool
A single-page web application designed as a learning tool to demonstrate the core mechanics of a real estate analysis platform. This application provides simplified property valuation, circle prospecting, and market forecasting features using vanilla JavaScript, HTML, and Tailwind CSS.

Overview
This project was created to provide a hands-on, interactive way to understand how front-end code can manage and display data to solve real-world business problems. It simulates a real estate dashboard where a user can select a property, view a calculated market value based on its features, and identify nearby properties for prospecting purposes. All data is handled client-side within a "mock database" for simplicity and learning.

Features
State-Based Filtering: The application is structured to handle data from specific states, starting with Ohio.

Dynamic Property Selection: The list of available properties updates dynamically based on the selected state.

Simplified Market Valuation: A clear, easy-to-understand algorithm calculates a property's estimated value based on its base value, square footage, and overall condition.

Market Forecasting: Users can simulate changing market conditions (Stable, Growing, Declining) to see how valuations are impacted in real-time.

Circle Prospecting: Identifies neighboring properties from the dataset based on street name and zip code, providing a list of potential leads.

Clean & Responsive UI: Styled with Tailwind CSS for a modern, professional, and mobile-friendly user interface.

How It Works
This application is built to be self-contained and requires no external database or back-end.

Mock Database
All property data is stored in a JavaScript array of objects at the top of the <script> tag in the index.html file.

const properties = [
    {
        id: 1,
        address: "123 Main St",
        city: "Columbus",
        state: "OH",
        zip: "43215",
        sqft: 1850,
        beds: 3,
        baths: 2.5,
        condition: "Good",
        baseValue: 320000
    },
    // ... more properties
];

This approach allows you to easily see the data structure and add, remove, or modify properties without needing a complex server setup.

Valuation Algorithm
The valuation is calculated using a straightforward function calculateValuation(prop, trend). This function takes a property object and the market trend as inputs and performs a series of adjustments to the baseValue:

Adds value based on square footage.

Applies a multiplier based on the property's condition ("Excellent" adds value, "Fair" detracts).

Applies a final multiplier based on the selected market trend from the forecast dropdown.

This function can be easily modified to test different valuation models.

How to Use
Open the index.html file in any modern web browser.

Select a state from the "Select a State" dropdown (defaults to Ohio).

Choose a property from the "Select a Property to Analyze" dropdown.

The Valuation Report and Circle Prospecting report will automatically appear on the right.

Change the Market Forecast dropdown to see the Estimated Market Value update in real-time.

Learning & Modification Ideas
This project is designed to be a learning sandbox. Here are some ways you can experiment with and expand upon the code:

Add More States and Properties: Add new property objects to the properties array with different state abbreviations. Then, add the new state as an <option> in the "Select a State" dropdown in the HTML.

Enhance the Valuation Model: Modify the calculateValuation function. How would you add value for the number of beds or baths? What if you introduced a "price per sqft" that varies by city?

Improve the Prospecting Logic: The current prospecting logic finds neighbors on the same street and zip. Could you modify it to find all properties within a certain radius of square footage?

Activate the "Custom Property" Feature:

Add HTML input fields for address, sqft, beds, baths, etc.

In the JavaScript, write the code to read the values from these inputs when the "Calculate Custom" button is clicked.

Pass these values to the calculateValuation function to display a report for a property that isn't in the mock database.
