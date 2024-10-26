# Code Challenge: User Management Binary Tree API with Vue Frontend

**Objective:**  
Create a RESTful API that manages two different types of binary trees, where each node represents a user. The challenge is designed to assess your ability to apply SOLID principles, design clean and scalable code, and implement a basic Vue frontend to interact with the API. You will use **PostgreSQL** for data persistence and incorporate `_lft` and `_rgt` columns for optimization.

**Estimated Time:** 4-6 hours

**Note:** Completion of the entire challenge is highly encouraged but not required. The backend implementation should be the primary focus, and candidates are expected to dedicate more effort to it.

---

## Requirements

### 1. Backend (Laravel + PostgreSQL)
- Implement a RESTful API that can handle two variations of binary trees:
    - **Standard Binary Search Tree (BST)**
    - **Self-balancing Binary Tree (e.g., AVL Tree)**
- Each binary tree should have the following CRUD capabilities:
    - **Create**: Add a user to the tree, persisting the data in PostgreSQL.
    - **Read**: Fetch a list of users and their details from the tree.
    - **Update**: Modify details of an existing user.
    - **Delete**: Remove a user from the tree.
- **Tree Optimization:** Implement a solution using `_lft` and `_rgt` columns (nested set model) to optimize searching and organizing the tree structure. These columns represent the left and right boundaries of each node, allowing efficient retrieval of subtrees and hierarchy traversal. **Do not use external packages**; the solution should be implemented from scratch.
- Use **SOLID principles** to design the code, emphasizing abstraction and interface usage.
- **PostgreSQL** should be used to persist user data, with CTE usage optional.
- **PHPUnit Testing**: Focus on **unit tests** using PHPUnit to validate key functionalities, ensuring the core logic works as expected.

### 2. Frontend (Basic Vue)
- Create a simple Vue app that interacts with the RESTful API.
- The app should have the following features:
    - **Form to add a user** (e.g., name, email) to a selected binary tree type.
    - **Display a list of users** fetched from the tree, showing basic details (no need for tree visualization).
    - **Buttons to update and delete users** from the list.
- The design should be basic and functional, focusing only on essential CRUD interactions.

### 3. Docker
- Provide a `docker-compose.yml` file to set up the environment, including the Laravel backend, PostgreSQL database, and Vue frontend.

---

## Technical Details
- **Programming Language:** PHP (Laravel) for the backend, JavaScript (Vue) for the frontend.
- **Database:** **PostgreSQL** for persisting user data in the binary tree structure.
- **Tree Optimization:** Utilize `_lft` and `_rgt` columns to optimize tree searching and traversals. The **nested set model** uses these columns to efficiently represent hierarchical data, allowing operations like retrieving all descendants of a node in a single query.
- **API Design:** Follow RESTful conventions, with endpoints like `/api/bst/addUser`, `/api/bst/listUsers`, `/api/avl/updateUser`, etc.
- **SOLID Principles:** Focus on using interfaces and abstract classes where appropriate.
- **Testing:** Use **PHPUnit** to create unit tests that demonstrate the correctness and reliability of your core logic.

---

## Differences Between Tree Types

### 1. Standard Binary Search Tree (BST)
- **Structure:** Each node has a maximum of two children (left and right). The left child’s value is less than its parent, and the right child’s value is greater.
- **Behavior:**
    - **Insertion:** Adds nodes based on left-right rules without balancing.
    - **Search:** Traverses the tree by comparing values, may degrade to O(n) if unbalanced.
    - **Deletion:** Removes nodes and adjusts children based on three possible scenarios.
    - **Traversal:** Supports basic CRUD interactions without needing complex tree traversal.
- **Complexity:** Average O(log n), but can degrade to O(n) if the tree becomes unbalanced.

### 2. Self-Balancing Binary Tree (AVL Tree)
- **Structure:** Similar to BST, but automatically balances itself after each insertion or deletion.
- **Behavior:**
    - **Insertion:** Adds nodes and performs rotations if needed to maintain balance.
    - **Search:** Similar to BST, but always guarantees O(log n) due to balancing.
    - **Deletion:** Removes nodes and checks for balance, performing rotations as needed.
    - **Traversal:** Supports basic CRUD interactions without needing complex tree traversal.
- **Complexity:** Consistent O(log n) due to self-balancing property.

### Summary:
| Feature                | Binary Search Tree (BST)            | Self-Balancing Tree (AVL Tree)             |
|------------------------|-------------------------------------|-------------------------------------------|
| **Balancing**          | No automatic balancing              | Automatically balances after every change |
| **Insertion**          | Based on left-right rules, no balance checks | Adds nodes and checks for balance, performs rotations if needed |
| **Search**             | Traverses based on left-right comparisons, may degrade to O(n) in unbalanced cases | Traverses similarly but ensures O(log n) by maintaining balance |
| **Deletion**           | Deletes and adjusts children as necessary | Deletes, checks for balance, and performs rotations if needed |
| **Complexity**         | O(log n) on average, O(n) in worst case | O(log n) for all operations due to balancing |

---

## Deliverables
- A private GitHub repository containing:
    - The full source code for the Laravel backend, PostgreSQL setup, and Vue frontend.
    - PHPUnit **unit tests** to validate key functionalities.
    - Instructions on how to run the application using Docker.
    - A brief README explaining your code structure, database schema, and how you applied SOLID principles, plus any notes on what you may have done differently or other approaches you may have used.
    - Add `@jacob-hyde` as a collaborator to the repository.

---

## Assessment Criteria
- Code quality, readability, and structure.
- Proper use of SOLID principles and clean architecture.
- Effective implementation of the RESTful API.
- Functional integration of PostgreSQL, with optional usage of **CTEs**.
- Implementation of `_lft` and `_rgt` columns to optimize tree operations using a **nested set model**.
- Simple but functional Vue frontend that allows adding, listing, updating, and deleting users.
- Proper testing with **PHPUnit**, focusing on unit tests.
- Adherence to instructions and completeness of the solution.
