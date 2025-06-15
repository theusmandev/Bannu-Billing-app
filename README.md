# J&K Bannu Pulao Billing System

Welcome to the **J&K Bannu Pulao Billing System**, a Python-based desktop application built with Tkinter for managing restaurant billing operations. Designed for a fictional restaurant, this tool streamlines order processing, bill generation, and customer management with an intuitive GUI. It includes features like a built-in calculator, email bill sending, dark mode, and bill saving/searching capabilities, making it a versatile solution for small-scale restaurant management.

## Features

- **Interactive GUI**: User-friendly Tkinter interface with organized sections for customer details, product selection, and bill display.
- **Product Categories**:
  - **Pulao**: Aik Pao, Aadha Kilo, Aik Kilo.
  - **Kabab**: Chapli Kabab.
  - **Raita & Salad**: Raita, Salad.
  - **Cold Drinks**: Regular, Half Litre, Litre, 1.5 Litre.
  - **Mineral Water**: 500ml, 1000ml.
- **Billing Operations**:
  - Calculate total prices based on selected items and quantities.
  - Generate detailed bills with customer details, itemized list, and total amount.
  - Save bills to a local `bills/` directory with unique bill numbers.
  - Search and display saved bills by bill number.
  - Print bills using the system's default printer.
  - Send bills via email using Gmail SMTP.
- **Built-in Calculator**: A fully functional calculator for quick arithmetic operations, accessible via a button.
- **Dark Mode**: Toggle between light and dark themes for better usability.
- **Clear Function**: Reset all input fields and bill area with one click.
- **Input Validation**: Ensures valid numeric inputs for quantities and checks for required customer details.
- **Real-Time Date**: Displays the current date on generated bills.

## Demo

![J&K Bannu Pulao Billing System Demo](Demo/Gift.gif)  


## Prerequisites

- **Python 3.x**: Ensure Python is installed on your system.
- **Tkinter**: Usually included with Python. If not, install it:
  ```bash
  pip install tk
  ```
- **SMTP Access**: For the email feature, you need a Gmail account with "Less Secure App Access" enabled or an App Password (recommended for security).
- **Operating System**: Tested on Windows. For printing, ensure a default printer is configured.

## Installation

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/theusmandev/Bannu-Billing-app.git
   cd jk-bannu-pulao-billing-system
   ```

2. **Ensure Dependencies**:
   Verify Python and Tkinter are installed. No additional libraries are required for core functionality.

3. **Run the Application**:
   ```bash
   Bannu-Billing-app
   ```

   Ensure the `billing_system.py` file (rename your script accordingly) is in the project directory. Place the `Images/` folder with icon files (`main.ico`, `cal.ico`, `mail.ico`) in the same directory.

## Usage

1. **Launch the Application**:
   Run the script to open the GUI window titled "J&K Bannu Pulao".

2. **Enter Customer Details**:
   - Input the customer's name, phone number, and (optionally) bill number in the "Customer Details" section.
   - Use the "SEARCH" button to retrieve a saved bill by bill number.

3. **Select Products**:
   - Enter quantities for desired items (e.g., Aik Pao Pulao, Chapli Kabab, Regular Cold Drink) in the respective entry fields.
   - Default quantities are set to 0.

4. **Calculate Total**:
   - Click the "Total" button to compute prices for Pulao, Kabab, Raita & Salad, and Drinks/Mineral Water.
   - Prices are displayed in the "Total Prices" section (e.g., Pulao: 360 RS).

5. **Generate Bill**:
   - Click the "Bill" button to create a detailed bill in the text area, including:
     - Restaurant name and date.
     - Customer details and bill number.
     - Itemized list with quantities and prices.
     - Total amount.
   - The bill is automatically saved to the `bills/` directory with a unique bill number.

6. **Additional Actions**:
   - **Print**: Click "Print" to send the bill to the default printer.
   - **Send**: Click "Send" to email the bill. Enter your Gmail address, password (or App Password), and recipient's email in the popup window.
   - **Clear**: Click "Clear" to reset all fields and the bill area.
   - **Dark Mode**: Toggle between light and dark themes using the "Dark Mode" button.
   - **Calculator**: Open a calculator window by clicking "Calculator" for quick calculations.

7. **Email Setup**:
   - For the "Send" feature, configure your Gmail account:
     - Enable 2-Step Verification and generate an App Password (recommended).
     - Or enable "Less Secure App Access" in Gmail settings (less secure).
   - Input the App Password in the password field when prompted.

## Project Structure

- `billing_system.py`: Main script containing the GUI, billing logic, calculator, and email functionality.
- `Images/`:
  - `main.ico`: Icon for the main window.
  - `cal.ico`: Icon for the calculator window.
  - `mail.ico`: Icon for the email window.
- `bills/`: Directory for saving generated bills as `.txt` files.
- `demo.gif` (optional): Add a demo GIF or screenshot to showcase the application.

## How It Works

- **GUI**: Built with Tkinter, featuring frames for customer details, product selection, bill display, and total prices.
- **Billing Logic**:
  - Prices are hardcoded (e.g., Aik Pao Pulao: 180 RS, Chapli Kabab: 130 RS).
  - The `total` function calculates subtotals for each category and updates entry fields.
  - The `bill_area` function generates a formatted bill with customer details and itemized pricing.
- **File Handling**:
  - Bills are saved as `.txt` files in the `bills/` directory with unique bill numbers (randomly generated between 500–1000).
  - The `search_bill` function retrieves saved bills by bill number.
- **Email Sending**: Uses `smtplib` to send bills via Gmail SMTP, with a popup for sender/receiver details.
- **Calculator**: A separate Tkinter window with buttons for digits, operators, square, square root, and clear functions.
- **Dark Mode**: Toggles between light (`white`) and dark (`#212121`) themes, updating widget colors dynamically.
- **Printing**: Uses `tempfile` and `os.startfile` to print bills via the system's default printer.

## Contributing

Contributions are welcome! To contribute:

1. Fork the repository.
2. Create a new branch (`git checkout -b feature/your-feature`).
3. Make your changes (e.g., add new menu items, improve UI, or enhance email security).
4. Commit your changes (`git commit -m "Add your feature"`).
5. Push to the branch (`git push origin feature/your-feature`).
6. Open a pull request.

Please ensure your code follows PEP 8 style guidelines and includes comments for clarity.

## Future Enhancements

- Add support for multiple restaurants or customizable menu items.
- Implement a database (e.g., SQLite) for bill storage and customer history.
- Enhance email security with OAuth2 for Gmail authentication.
- Add a PDF export option for bills.
- Include a settings panel for custom prices and themes.
- Support multi-language interfaces for broader accessibility.

## Known Issues

- **Email Sending**: May fail if Gmail's security settings are not configured correctly. Use an App Password for reliable operation.
- **Printing**: Limited to Windows due to `os.startfile`. Cross-platform printing may require additional libraries.
- **Bill Number Collisions**: Random bill numbers (500–1000) may occasionally overlap. Consider using sequential or timestamp-based numbering.


## Acknowledgments

- Inspired by the need for efficient restaurant billing solutions.
- Thanks to the Python, Tkinter, and open-source communities for their resources.
- Special thanks to Muhammad Usman for the original design and vision.

Feel free to star ⭐ this repository if you find it useful, and share your feedback or ideas in the issues section!

*Created by [Muhammad Usman]*
