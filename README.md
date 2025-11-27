# FunCap – Updated for IDA Pro 9.x
*A modernized fork of the original FunCap function call capture tool*

## 📌 Overview
**FunCap** is a debugging-time function call capture script originally written by **deresz** under the **GPL-2.0** license.  
It records function calls, arguments, register states, stack values, and annotates the IDA disassembly with runtime information.

This fork updates FunCap to work reliably with **IDA Pro 9.1** and modern Python 3.x, addressing API changes that caused crashes in the original version.

Original repository:  
👉 [https://github.com/deresz/funcap](https://github.com/deresz/funcap)

## 🛠️ Changes in This Fork (IDA 9.1 Compatibility)
### ✔ Updated for IDA 9.1 debugger API
- Replaced deprecated or removed APIs (e.g., `get_inf_structure()`).
- Adapted SWIG-backed debug hooks to the current IDA 9.x model.

### ✔ Fixed crashes during stack argument analysis
- Patched `get_num_args_stack()` to avoid `NoneType` arithmetic errors.
- Added safe fallback behavior when IDA cannot determine frame size.
- Ensures reliable call/ret handling even when IDA analysis is incomplete.


## 🚀 Usage
1. Copy `funcap.py` into your IDA script or plugin directory.
2. Load it in IDA:
   ```
   File → Script File… → funcap.py
   ```
3. Ensure a debugger is selected.
4. Turn FunCap ON:
   ```python
   d.on()
   ```

### Hook calls in the current function:
```python
d.hookFunc()
```

### Hook calls in the current segment:
```python
d.hookSeg()
```


## 🧑‍💻 Credits
**Original Author:** deresz  
**IDA 9.1 Patch:** ashley-920

## 📜 License
GPL-2.0, identical to the original project.


