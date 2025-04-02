Design Document for the Java Zoo Midterm Project
1. Overview
   The Java Zoo project is designed to manage a list of incoming animals and generate a report based on their details. The application reads animal data from files, assigns names based on species, and organizes the information using Object-Oriented Programming (OOP) principles. This practice lays the groundwork for the upcoming midterm project.

2. Components
   Animal Base Class
   Holds common properties: name, age, and species. Provides getters, setters, and a custom toString method.

Animal Subclasses
Specific species (Lion, Tiger, Bear, Hyena) inherit from the Animal class. Each subclass can later be extended with unique behaviors or properties specific to that animal type.

File I/O Module
Handles reading from animalNames.txt (for available names per species) and arrivingAnimals.txt (for animal details) and writes the processed report to newAnimals.txt.

Report Generation Module
Aggregates data by species and outputs a formatted report that includes:

Species name (with proper capitalization)

Total count of animals per species

List of animals with their name and age

3. Data Structures
   ArrayList:
   Used for storing the Animal objects. It provides dynamic resizing and easy iteration, which is ideal for sequential processing of animals.

HashMap (and Queue):

A HashMap<String, Queue<String>> stores available names for each species, allowing quick access and removal of names as they are assigned.

A separate HashMap<String, Integer> counts animals per species to generate summary statistics for the report.

4. Interactions
   File Reading:

The application first reads the names file to populate the names map.

Then, it reads the arriving animals file. For each record, it extracts the age and species, retrieves an appropriate name (if available), creates an instance of the correct animal subclass, and updates the count.

Data Aggregation and Report Writing:

After processing, the list of animals and the species count map are used to group the animals by species.

The final report is written to newAnimals.txt with the required format.

OOP Principles:

Encapsulation is maintained by keeping class properties private.

Inheritance is used for creating species-specific behavior from the Animal class.

Polymorphism is enabled by treating all animal instances uniformly in the collection while still preserving subclass distinctions.

5. Future Enhancements
   GUI Integration:
   Consider adding a graphical interface for easier management and viewing of animal records.

Dynamic Species Handling:
Introduce a configuration file or a factory pattern that dynamically handles new species without modifying the codebase.

Extended Functionality:
Add methods to update animal details, remove animals, or track additional properties like health status or habitat.