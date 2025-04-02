Experimenting with Data Structures
Alternative Data Structures
Using Enum for Species:

Idea: Define an enum for species (e.g., public enum Species { LION, TIGER, BEAR, HYENA }).

Benefit: This approach can help prevent typos in species names and improve code readability.

TreeMap for Sorted Output:

Idea: Replace HashMap<String, Integer> with TreeMap<String, Integer> when counting species.

Benefit: A TreeMap will maintain the species in sorted order, which could be useful for a neat, alphabetically ordered report.

Concurrent Collections:

Idea: If you plan to extend the application to support multithreading (e.g., reading input concurrently), consider using concurrent collections like ConcurrentHashMap for species count.

Benefit: This ensures thread safety without significant performance drawbacks.

Stream API Enhancements:

Idea: Use Java 8 Streams to group animals by species and count them.

java
Copy
Map<String, Long> speciesCount = animals.stream()
.collect(Collectors.groupingBy(Animal::getSpecies, Collectors.counting()));
Benefit: This can reduce boilerplate code and make the processing logic more declarative.

Testing Data Structures
Prototype Small Code Segments:
Write small, isolated code snippets to test how these alternative structures handle typical operations (e.g., insertion, removal, sorting). This experimentation can reveal performance differences and help decide on the best structure for your project's needs.

Benchmarking:
If you plan to handle a large number of animal records, consider benchmarking different data structures (ArrayList vs. LinkedList, HashMap vs. TreeMap) to see which performs best in your context.

