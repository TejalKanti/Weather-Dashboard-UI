# Weather Dashboard UI App

**Developer**: Tejal Kanti 

**Student Number**: ST10513267

**Group**: 2

**Course**: MAST

**Subject**: Mobile App Scripting

---


## Links: 

**GitHub Repository**: https://github.com/TejalKanti/Weather-Dashboard-UI.git

---

## Project Overview

The Weather Dashboard UI App is a website application developed as part of an ICE Task in the MAST subject. This application was created using react native. 

---

## Development Environments

1. **Expo**
   
2. **React Native**
   
3. **TypeScript**
   
4. **Institutional VM**
   
5. **Blue Stacks 5**

6. **Expo Go**

---

## Error Log Table

| # | Location | Problem | Error Type | Correction |
| :-: | :--- | :--- | :--- | :--- |
| **1** | Main Imports | The `ImageBackground` component was used in the render tree but was missing from the import list from `'react-native'`. | **Runtime** | Added `ImageBackground` to the destructured `'react-native'` import statement so the native engine can resolve the component layout. |
| **2** | `App` Component (`citySelector`) | The selection condition and updater checked `selectedCity === weather.country` and triggered `setSelectedCity(weather.country)`. Because `selectedCity` is initialized with the city name (`'Johannesburg'`), it compared a city string to a country string, breaking button active-states and setting wrong values on tap. | **Logic** | Updated `weather.country` to `weather.city` in both the style comparison expression and the `onPress` callback handler so matching state resolves cleanly. |
| **3** | `ImageBackground` element | The `source` property was passed a raw string URL (`selectedWeather.backgroundImage`). In React Native, remote web network images require an object source mapping with a `uri` key. | **Runtime / UI** | Wrapped the image asset string inside an object format: `source={{ uri: selectedWeather.backgroundImage }}` to force proper image network fetching. |
| **4** | `currentDetails` layout block | The humidity detail card value was incorrectly pointing to `{selectedWeather.feelsLike}` instead of the data object's humidity property. | **Logic** | Replaced `{selectedWeather.feelsLike}` with `{selectedWeather.humidity}` to display accurate atmospheric metrics. |
| **5** | 24 Hour Forecast (`ScrollView`) | The inner layout configuration had `horizontal={false}` assigned. Because it is embedded within a parent vertical `ScrollView`, it failed to allow left-to-right swipe panning for hours. | **UX / UI Layout** | Toggled the configuration flag to `horizontal={true}` to activate proper inline swipe mechanics for the hourly dashboard segment. |
| **6** | Hourly loop mapping | Inside the `.map()` loop, the layout displayed `{selectedWeather.temperature}`. This caused the component to repeat the city's current overall temperature over every single hourly timeline node. | **Logic** | Pointed the JSX node to the localized loop variable property `{hour.temperature}` to show real chronological temperature changes. |
| **7** | Hourly map iteration | The map iterator used the list item value `key={hour.time}`. Because timestamps can occasionally experience overlap profiles or empty dataset values, this could crash dynamic virtual lists. | **TypeScript / React** | Appended the index variable context dynamically to create an isolated key reference structure: `key={hour.time + index}`. |
| **8** | 5 Day Forecast container | The dynamic evaluation list used block curly braces `{ ... }` inside the `.map()` callback but lacked an explicit `return` keyword statement. This caused the engine to yield `undefined`, rendering an invisible block. | **Logic / Syntax** | Substituted the heavy evaluation block wrapper braces `{}` with immediate evaluation wrapper parentheses `()` to enforce implicit JSX component returns. |
| **9** | Daily dynamic listing nodes | The daily list item layout positioned the high text layer wrapping `{day.low}°` and the low text layer wrapping `{day.high}°`. This inverted the graphical intent of the column hierarchy. | **Logic / UI** | Realigned the semantic markup definitions to ensure `{day.high}°` binds directly to the `highTemperature` style class and `{day.low}°` binds to the `lowTemperature` class. |
| **10** | Sun & Moon grid element | The Sunrise information field value node was mapped directly to `selectedWeather.sunset`, rendering the sunset timestamp twice. | **Logic** | Rectified the model reference to assign `selectedWeather.sunrise` explicitly onto the Sunrise component instance. |
| **11** | `WeatherDetail` component | The lower layout UI mapped `{label}` within the dynamic element value block, displaying the descriptive key string twice instead of displaying the unique property measurement value. | **Logic** | Altered the child text expression nodes inside the subcomponent container block to target the passed component parameter `{value}` instead. |

---

## Testing


1. Valid Form & State Interaction (City Selection)

Scenario: Simulating user clicks on the city selection navigation filters (Johannesburg, Cape Town, Durban).

Execution: Tapped each option sequentially to ensure state properties matched exactly (selectedCity === weather.city).

Result: Pass. The layout dynamically switched the background image cards instantly. Active component styles toggled accurately, and sub-metric displays refreshed safely without data leaks or lagging UI elements.


2. Invalid Data & State Ingestion (Error Handling Boundary)

Scenario: Simulating a condition where an invalid or corrupted city variable payload gets passed to the component state engine.

Execution: Set selectedCity manually to a dummy string value ('Pretoria') to force a data miss inside the local lookup array.

Result: Pass. The fallback engine triggered cleanly without breaking the virtual machine execution stack. The UI gracefully returned the custom message: "Weather information unavailable."

---

## Screenshots

<img width="540" height="960" alt="Screenshot_2026 10 07_22 30 06 757" src="https://github.com/user-attachments/assets/d1207bc1-ad2c-4fc3-bdd8-96d093309d24" />

*Caption for screenshot 1: Home Screen.*


<img width="540" height="960" alt="Screenshot_2026 10 07_22 30 06 757" src="https://github.com/user-attachments/assets/0760016a-66fc-4938-a2ea-a8c0567cf162" />

*Caption for screenshot 2: Joburg Dashboard.*


<img width="540" height="960" alt="Screenshot_2026 10 07_22 30 32 153" src="https://github.com/user-attachments/assets/456f4fd4-0f9d-44a5-8e51-bb8c5a52a75b" />

*Caption for screenshot 3: Joburg Dashboard.*


<img width="540" height="960" alt="Screenshot_2026 10 07_22 30 39 086" src="https://github.com/user-attachments/assets/0db42708-ddb8-44b6-aed4-57608da00757" />

*Caption for screenshot 4: Joburg Dashboard.*


<img width="540" height="960" alt="Screenshot_2026 10 07_22 30 51 663" src="https://github.com/user-attachments/assets/dfd1e165-4135-4859-b12b-1bef1e2b18c6" />

*Caption for screenshot 5: Cape Town Dashboard.*


<img width="540" height="960" alt="Screenshot_2026 10 07_22 31 31 054" src="https://github.com/user-attachments/assets/0d491835-bca7-4ad6-ae83-efb479fa9894" />

*Caption for screenshot 6: Cape Town Dashboard.*


<img width="540" height="960" alt="Screenshot_2026 10 07_22 31 40 887" src="https://github.com/user-attachments/assets/cad056c3-7554-442f-ad21-a697f00d01fb" />

*Caption for screenshot 7: Cape Town Dashboard.*


<img width="540" height="960" alt="Screenshot_2026 10 07_22 32 34 447" src="https://github.com/user-attachments/assets/3e3d083e-477b-4937-b555-497aca2cbd5d" />

*Caption for screenshot 8: Durban Dashboard.*


<img width="540" height="960" alt="Screenshot_2026 10 07_22 32 43 854" src="https://github.com/user-attachments/assets/05b7f460-9f3a-46dd-8a3b-9a6ed42cd235" />

*Caption for screenshot 9: Durban Dashboard.*


<img width="540" height="960" alt="Screenshot_2026 10 07_22 32 52 586" src="https://github.com/user-attachments/assets/e9b3878b-67f2-4f38-b0d0-fd07a35f9bf1" />

*Caption for screenshot 10: Durban Dashboard.*

---

## Conclusion

Debugging this application highlighted how minor oversight syntax bugs—like omitting component imports or forgetting implicit map return statements—will completely break mobile runtime compilation. Correcting the city selector highlighted the necessity of maintaining strict state parameter integrity, as comparing a city variable to a country property completely broke layout interactivity. Fixing data mappings showed that mapping incorrect UI variables or misconfiguring scroll properties will cause static data duplication and lock layout navigation. The process proved that combining precise TypeScript definitions with meticulous runtime state validation is essential to delivering a fluid, bug-free mobile interface input validations and UI controls. Correcting the state management structure showed that utilizing array restructuring spread syntax is critical to prevent new data entries from accidentally overwriting existing records. Fixing the array filter deletion logic demonstrated that applying the correct strict comparison operators is essential to keep state manipulations isolated to a single targeted element. Ultimately, the investigation highlighted that maintaining strict TypeScript type contracts and testing edge-case boundary limits are fundamental to building predictable, crash-free mobile applications.

---

