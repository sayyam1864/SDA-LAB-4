# Pipe and Filter Architecture - Cube Numbers Filter  

## **Overview**  
The **Pipe and Filter** architecture is a design pattern used to process data through a sequence of independent transformation steps called filters. Each filter performs a specific operation on the input data and passes the result to the next filter in the pipeline.  

This project demonstrates the **Pipe and Filter** architecture in Java, with multiple filters applied sequentially. A new filter, **cubeNumbers**, has been added to enhance data transformation.  

---

## **Newly Added Filter: Cube Numbers**  

### **Description**  
The `cubeNumbers` filter computes the cube of each number in the input list. This transformation is useful for scenarios requiring cubic calculations, such as mathematical computations and data processing applications.  

### **Implementation**  
```java
private static List<Integer> cubeNumbers(List<Integer> input) {
    return input.stream()
            .map(n -> n * n * n)
            .collect(Collectors.toList());
}
```

### **Functionality**  
- Accepts a list of integers as input.  
- Computes the cube (`n³`) of each number.  
- Returns a new list containing the cubed values.  

### **Example Input & Output**  

#### **Input List:**  
```java
List<Integer> input = List.of(1, 2, 3, 4, 5);
```

#### **Processing through `cubeNumbers` Filter:**  
```java
List<Integer> output = cubeNumbers(input);
```

#### **Output List:**  
```
[1, 8, 27, 64, 125]
```

This filter is applied in the pipeline, transforming numbers before passing them to subsequent filters.  

---

## **Other Filters in the Pipeline**  

### **1. Filter Even Numbers**  
- **Purpose:** Keeps only even numbers from the input list.  
- **Example:** `[1, 2, 3, 4, 5]` → `[2, 4]`  

### **2. Square Numbers**  
- **Purpose:** Computes the square of each number.  
- **Example:** `[2, 4]` → `[4, 16]`  

### **3. Filter Numbers Greater Than 10**  
- **Purpose:** Removes numbers less than or equal to 10.  
- **Example:** `[4, 16]` → `[16]`  
