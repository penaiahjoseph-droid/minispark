# MiniSparkRDD

A lightweight Python implementation inspired by Apache Spark's Resilient Distributed Dataset (RDD) architecture. This project demonstrates lazy evaluation, Directed Acyclic Graph (DAG) execution, and basic distributed data processing concepts using Python.

## 📌 Project Overview

MiniSparkRDD simulates the core working principles of Apache Spark by implementing:

- RDD abstraction
- Lazy transformations
- DAG (Directed Acyclic Graph)
- Executor for pipeline execution
- Basic optimizer
- CSV data loading
- Data parsing utilities

The project processes an Amazon products dataset and performs filtering and mapping operations similar to Spark.

---

## 📂 Project Structure

```
MiniSparkRDD/
│
├── src/
│   ├── __init__.py
│   ├── dag.py
│   ├── executor.py
│   ├── loader.py
│   ├── node.py
│   ├── optimizer.py
│   ├── parser.py
│   ├── rdd.py
│   └── utils.py
│
├── Data/
│   └── amazon.csv
│
├── main.py
└── README.md
```

---

## 🚀 Features

- Create custom RDD objects
- Filter data using lambda functions
- Map transformations
- FlatMap transformation support
- Lazy execution using DAG
- Simple query optimization
- CSV file loading
- Display execution results

---

## ⚙️ Technologies Used

- Python 3.x
- CSV Module
- Object-Oriented Programming
- Functional Programming (Lambda)
- DAG Execution Model

---

## 🏗 Architecture

```
CSV Dataset
      │
      ▼
 Loader
      │
      ▼
    RDD
      │
      ▼
 Transformations
(Filter / Map / FlatMap)
      │
      ▼
     DAG
      │
      ▼
 Optimizer
      │
      ▼
  Executor
      │
      ▼
  Final Output
```

---

## 📊 Dataset

The project uses an Amazon product dataset containing:

- Product ID
- Product Name
- Category
- Discounted Price
- Actual Price
- Discount Percentage
- Rating
- Rating Count
- Product Description

The sample dataset includes products from Electronics, Fashion, Furniture, and Home Appliances. :contentReference[oaicite:0]{index=0}

---

## 📖 How It Works

### Step 1: Load Dataset

Reads the CSV file into memory.

```python
data = load_csv("Data/amazon.csv")
```

### Step 2: Create RDD

```python
amazon_rdd = RDD(data)
```

### Step 3: Apply Transformations

```python
result = (
    amazon_rdd
    .filter(lambda x: "Electronics" in x["category"])
    .filter(lambda x: float(x["rating"]) > 4)
    .map(lambda x: x["product_name"])
    .collect()
)
```

This pipeline filters Electronics products with ratings greater than 4 and returns their product names. :contentReference[oaicite:1]{index=1}

---

## 📚 Modules

### loader.py

Loads CSV data into Python dictionaries.

---

### node.py

Represents each transformation as a node inside the execution graph.

---

### dag.py

Stores all transformation nodes and displays the execution order.

---

### executor.py

Executes every transformation sequentially.

Supported operations:

- FILTER
- MAP
- FLATMAP

---

### optimizer.py

Placeholder optimizer that prepares the DAG before execution.

---

### parser.py

Utility functions for cleaning:

- Prices
- Percentages
- Ratings

---

### rdd.py

Implements Spark-like RDD transformations and actions.

---

### utils.py

Displays execution results.

---

## ▶️ Running the Project

Clone the repository:

```bash
git clone https://github.com/yourusername/MiniSparkRDD.git
```

Move into the project:

```bash
cd MiniSparkRDD
```

Run:

```bash
python main.py
```

---

## ✅ Example Output

```
Execution DAG

↓ FILTER
↓ FILTER
↓ MAP

Optimizer Running...

Results

Echo Smart Speaker
Gaming Laptop Pro
Mechanical Keyboard
Wireless Mouse
Tablet Device
```

---

## 🎯 Learning Outcomes

This project demonstrates:

- Spark RDD concepts
- Lazy Evaluation
- DAG Execution
- Functional Programming
- Object-Oriented Design
- Data Processing Pipelines
- Python Collections
- Lambda Functions

---

## 🔮 Future Enhancements

- Reduce operation
- GroupByKey
- Join
- Parallel execution
- Partitioning
- Cache/Persist
- Better query optimizer
- SQL-like API
- Performance benchmarking

---

## 👨‍💻 Author

**Penaiah Joseph**

Mini Project based on Apache Spark RDD architecture using Python.

---

## 📄 License

This project is developed for educational and learning purposes.
