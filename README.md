# Graph Data Structure in JavaScript 🚀  

A simple implementation of the **Graph** data structure in JavaScript. This repository demonstrates how to create a graph class with essential methods and explains its functionality with practical examples.  

---

## What is a Graph?  
A **Graph** is a collection of nodes (also called vertices) and edges that connect pairs of nodes. Graphs can be either **directed** (edges have a direction) or **undirected** (edges do not have a direction). Graphs are used to represent various real-world structures such as networks, maps, and relationships between entities.  

---

## Features  
- **Add Vertex**: Add a new node to the graph.  
- **Add Edge**: Add a connection between two nodes.  
- **Remove Vertex**: Remove a node from the graph.  
- **Remove Edge**: Remove the connection between two nodes.  
- **Display**: View the graph structure.  

---

## Code Implementation  

Here’s the JavaScript implementation of the graph:  

```javascript
class Graph {
    constructor() {
        this.vertices = {}; // Stores all vertices (nodes)
    }

    // Add a new vertex to the graph
    addVertex(vertex) {
        if (!this.vertices[vertex]) {
            this.vertices[vertex] = [];
        }
    }

    // Add an edge between two vertices
    addEdge(vertex1, vertex2) {
        if (this.vertices[vertex1] && this.vertices[vertex2]) {
            this.vertices[vertex1].push(vertex2);
            this.vertices[vertex2].push(vertex1); // For undirected graph
        }
    }

    // Remove a vertex from the graph
    removeVertex(vertex) {
        if (this.vertices[vertex]) {
            delete this.vertices[vertex];
            for (let key in this.vertices) {
                const index = this.vertices[key].indexOf(vertex);
                if (index !== -1) {
                    this.vertices[key].splice(index, 1);
                }
            }
        }
    }

    // Remove an edge between two vertices
    removeEdge(vertex1, vertex2) {
        if (this.vertices[vertex1] && this.vertices[vertex2]) {
            this.vertices[vertex1] = this.vertices[vertex1].filter(v => v !== vertex2);
            this.vertices[vertex2] = this.vertices[vertex2].filter(v => v !== vertex1);
        }
    }

    // Display the graph structure
    display() {
        console.log(this.vertices);
    }
}
```

---

## Example Usage  

```javascript
// Initialize the graph
const graph = new Graph();

// Add vertices
graph.addVertex("A");
graph.addVertex("B");
graph.addVertex("C");

// Add edges
graph.addEdge("A", "B");
graph.addEdge("A", "C");

// Display the graph
graph.display(); // Output: { A: [ 'B', 'C' ], B: [ 'A' ], C: [ 'A' ] }

// Remove an edge
graph.removeEdge("A", "B");
graph.display(); // Output: { A: [ 'C' ], B: [], C: [ 'A' ] }

// Remove a vertex
graph.removeVertex("C");
graph.display(); // Output: { A: [], B: [] }
```

---

## Real-World Applications  
1. **Social Networks**: Representing users and their connections.  
2. **Route Planning**: Used in maps for finding the shortest path between locations.  
3. **Recommendation Systems**: Connecting items based on user preferences or behavior.  
4. **Web Crawling**: Representing the relationship between web pages and links.  

---

## TikTok Tutorial 🎥  
Want to see a quick tutorial on how to build this? Check out this TikTok video:  
[]()  

---

## How to Run the Code  
1. Clone the repository:  
   ```bash
   git clone https://github.com/fix2015/structure_graph
   cd structure_graph
   ```
2. Open the file `index.js` in your favorite code editor.  
3. Run the file using Node.js:  
   ```bash
   node index.js
   ```

---

## Contributing  
Contributions are welcome! If you have suggestions or want to add new features, feel free to create a pull request.  

---

## License  
This project is licensed under the MIT License.  

---

## Connect with Me:
- [LinkedIn - Vitalii Semianchuk](https://www.linkedin.com/in/vitalii-semianchuk-9812a786/)
- [Telegram - @jsmentorfree](https://t.me/jsmentorfree) - We do a lot of free teaching on this channel! Join us to learn and grow in web development.
- [Tiktok - @jsmentoring](https://www.tiktok.com/@jsmentoring) Everyday new videos
- [Youtube - @jsmentor-uk](https://www.youtube.com/@jsmentor-uk) Mentor live streams
- [Dev.to - fix2015](https://dev.to/fix2015) Javascript featured, live, experience but about Graph
