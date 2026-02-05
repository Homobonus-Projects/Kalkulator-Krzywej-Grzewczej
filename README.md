# ⚙️ Wizualizator Krzywej Grzewczej (i-Sense)

A web-based tool designed to help users visualize and calculate the optimal heating curve for De Dietrich condensing boilers (specifically referencing the i-Sense series, formerly AD289). This interactive calculator allows you to set key parameters and instantly see how your boiler's flow temperature should adjust based on outdoor temperature for efficient and economical operation.

## ✨ Features

-   **Interactive Input**: Easily adjust four critical parameters for your heating system.
-   **Real-time Calculation**: Instantly calculates and displays the heating curve's slope.
-   **Dynamic Chart Visualization**: Utilizes Chart.js to render a clear and interactive graph of the heating curve.
-   **Contextual Comments**: Provides insightful comments and recommendations based on the calculated slope, guiding you towards optimal boiler settings for different heating systems (e.g., underfloor heating, radiators).
-   **Responsive Design**: Built with Tailwind CSS for a clean and adaptable user interface across various devices.

## 💡 How it Works

The tool operates by defining a linear heating curve based on two user-specified points:

1.  **Punkt Bazowy (Base Point)**:
    *   `T zewn. baza [°C]` (Base outside temperature): The outdoor temperature at which your heating system typically begins to operate.
    *   `T zasilania baza [°C]` (Base flow temperature): The desired flow temperature of the water in your heating system when the outdoor temperature is at the base point.

2.  **Punkt Klimatu (Climate Point)**:
    *   `T zewn. klimatu [°C]` (Climate outside temperature): The lowest expected outdoor temperature for your region (e.g., during the harshest winter days).
    *   `T zasilania klimatu [°C]` (Climate flow temperature): The maximum desired flow temperature of the water in your heating system during the coldest conditions.

The **slope** of the heating curve is then calculated using these two points. This slope determines how aggressively the boiler increases the flow temperature as the outdoor temperature drops. A flatter curve generally indicates more economical operation for condensing boilers.

## 🚀 Technologies Used

-   **HTML5**: Structure of the web page.
-   **Tailwind CSS**: Utility-first CSS framework for styling.
-   **Chart.js**: JavaScript charting library for interactive data visualization.
-   **Vanilla JavaScript**: For all the logic, calculations, and DOM manipulation.

## 🖥️ Usage

1.  Open the `index.html` file in your web browser.
2.  You will see four input fields under "Parametry Krzywej Grzewczej" (Heating Curve Parameters).
3.  Adjust the values for:
    *   `T zewn. baza [°C]` (e.g., 20°C)
    *   `T zasilania baza [°C]` (e.g., 20°C)
    *   `T zewn. klimatu [°C]` (e.g., -20°C)
    *   `T zasilania klimatu [°C]` (e.g., 55°C)
4.  Click the "Wygeneruj Krzywą" (Generate Curve) button. The chart will update, and the calculated "Nachylenie krzywej (Slope)" and a "Komentarz (Wg. De Dietrich)" will be displayed.
5.  Observe the generated heating curve on the graph, the calculated slope, and the accompanying advice to fine-tune your boiler's settings for optimal performance and energy efficiency.

## ⚙️ Deployment

This project includes a GitHub Actions workflow (`.github/workflows/deploy.yml`) that automates the deployment process. Upon a `push` to the `main` branch, the `index.html` file is copied to a specified directory (`/var/www/heatcurve/index.html`) on a `self-hosted` runner, making it available via a web server (e.g., Nginx).

## 🤝 Contributing

Feel free to fork the repository, make improvements, and submit pull requests.

## 📄 License

This project is open-source and available under the MIT License.