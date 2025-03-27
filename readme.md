# **Java Native Library Benchmark: JNA vs ProcessBuilder & More** 🚀  

📌 **A performance benchmark comparing different ways Java can call native code**—starting with **Python**, and planning to expand to **C, Rust, Go, and more!**  

---

## **⚡ Overview**  

This project benchmarks multiple approaches to calling **native functions** in Java, starting with:  

✅ **JNA (Java Native Access)** – Direct memory calls via shared libraries (`.so/.dll`).  
✅ **ProcessBuilder** – Calls external processes (starting with Python).  

🔜 **Upcoming Benchmarks:**  
- **JNI (Java Native Interface)** – Direct C/C++ bindings.  
- **JEP 442 (Foreign Function & Memory API)** – The modern way to call native functions in Java.  
- **Rust FFI** – Leveraging Rust's safety with Java.  
- **Go Shared Library** – Java calling Go functions.  

---

## **📊 Benchmark Results**  

| Approach          | Expected Time (1000 calls) | Notes |  
|------------------|-------------------------|---------------------------|  
| **JNA (Shared Library)** | ⚡ ~5-50 ms | Direct memory calls (fastest) |  
| **ProcessBuilder (Python)** | 🐢 ~500-5000 ms | New process overhead (slow) |  
| **(Planned) JNI (C/C++)** | ⏳ TBD | Likely close to JNA performance |  
| **(Planned) Rust FFI** | ⏳ TBD | Expected to be efficient & safe |  
| **(Planned) Go Shared Lib** | ⏳ TBD | Performance unknown, worth testing |  

---

## **🚀 Getting Started**  

### **1️⃣ Setup Java & Dependencies**  
Make sure you have:  
- **JDK 17+** installed.  
- **JNA library** (for JNA tests).  
- **Python 3+** (for ProcessBuilder tests).  

### **2️⃣ Clone the Repo**  
```sh  
git clone https://github.com/yourusername/java-native-benchmark.git  
cd java-native-benchmark  
```

### **3️⃣ Run the Benchmarks**  

#### **Benchmark JNA (Shared Library)**  
```sh  
javac -cp jna.jar:. BenchmarkJNA.java NativeLib.java  
java -cp jna.jar:. BenchmarkJNA  
```

#### **Benchmark ProcessBuilder (Python)**  
```sh  
javac PythonInvoker.java BenchmarkProcessBuilder.java  
java BenchmarkProcessBuilder  
```

---

## **🛠️ How It Works**  

### **🧩 JNA (Java Native Access)**  
- Calls a shared **C/C++/Rust/Go** library **without JNI**.  
- Requires a `.so` (Linux), `.dylib` (Mac), or `.dll` (Windows).  

### **⚙️ ProcessBuilder (External Process)**  
- Java spawns a **Python subprocess** and reads output.  
- Slower due to **inter-process communication (IPC)**.  

### **🔬 Future Expansion**  
- **Add JNI (C/C++)** for direct native integration.  
- **Rust FFI & Go Shared Libraries** for efficiency.  
- **JEP 442 Foreign Memory API** for a modern alternative.  

---

## **📜 License**  
MIT License - Feel free to use & contribute!  

---

## **💡 Contributing**  
Want to test another native language? Open a PR! 🚀  
