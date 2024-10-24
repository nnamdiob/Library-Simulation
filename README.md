
# Multi-Threaded Patron Rental Simulator 

## Project Description
This project simulates a library book rental system with a graphical interface, allowing patrons to rent books from the library and visualize the rental queue. The system is implemented in C, and it features several key components that work together to create a realistic simulation of the rental process.

The project has been adapted from an earlier restaurant drive-thru simulation, where concepts such as rental windows, patrons, and book rentals have replaced the original restaurant items and cars. The simulator uses X11 graphics to create a visual representation of patrons interacting with the library.

Key components of the project include:
- **Librarian:** Acts as the library server, managing patron queues and handling requests for book rentals.
- **Patron:** Represents individuals who rent books from the library, and interacts with the librarian to place rental requests.
- **Generator:** Generates a specified number of patrons to interact with the system.
- **Display:** Uses X11 to display the library, patrons, and rental activities visually.
- **Library Server:** Handles incoming patron requests, such as getting in line or placing a rental, and manages the overall flow of the library operations.

## Project Files
- **librarian.c**: Implements the server-side functionality that accepts patrons, processes book rentals, and manages the shutdown procedure.
- **patron.c**: Represents individual patrons who can rent books.
- **generator.c**: Generates multiple patrons to interact with the system, simulating random rental requests.
- **display.c & display.h**: Handles the graphical display of the library, including patron activity, using X11 graphics.
- **libraryServer.c**: Manages the server functionalities, coordinating between librarian, patrons, and display.
- **library.h**: Contains the definitions and constants shared across different components.
- **makefile**: Provides build instructions to compile the project.

## How to Build and Run the Project

### Prerequisites
- **C Compiler**: Ensure that you have GCC or a similar compiler installed.
- **X11 Development Libraries**: The display functionality requires X11 to draw the graphical elements. Make sure you have installed the X11 libraries. On Ubuntu, you can install them with:
  ```
  sudo apt-get install libx11-dev
  ```

### Building the Project
1. **Download the project files** to a local directory.
2. Open a terminal in the project's root directory.
3. Run the following command to build the project:
   ```
   make all
   ```
   This command will compile all the necessary files and create the executables needed to run the simulation.

### Running the Project
1. **Start the Library Server**:
   ```
   ./libraryServer
   ```
   This will start the server and make the library ready for patrons.

2. **Start the Generator** to simulate multiple patrons renting books:
   ```
   ./generator
   ```
   The generator will create several patrons, each attempting to rent books from the library.

3. Alternatively, you can **run an individual patron** by specifying the book indices they wish to rent:
   ```
   ./patron 1 2 3 4 5 up to 10
   ```
   This command simulates a patron renting books with indices `1, 2, 3, 4, 5`. Note: Valid book indices are from `1` to the total number of books available (`NUM_BOOK_ITEMS`).

4. The **display window** will show the library environment, including patrons moving through the rental line and the rental window activity. Ensure that you have an X11 server running to view the graphical display.

### Stopping the Server
To gracefully shut down the library server, send a shutdown command via the patron script or manually close the server.
    ```
   ./shutDown
   ```

