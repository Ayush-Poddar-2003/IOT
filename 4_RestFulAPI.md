This is a 10-mark theory + coding question from your exam paper. Here's a full answer, broken into two parts: **Theory + Python Code using Flask**, perfectly suitable for your IOT exam.

---

## ✍️ **Q. Describe the steps to design a RESTful API, including defining endpoints, HTTP methods (GET, POST, PUT, DELETE), and response formats (JSON). Provide a Python example using Flask to create a simple RESTful API for managing IoT devices.**

---

### ✅ **Part 1: Steps to Design a RESTful API (Theory)**

| **Step**                       | **Description**                                                                                                            |
| ------------------------------ | -------------------------------------------------------------------------------------------------------------------------- |
| **1. Identify Resources**      | Define what you're managing — e.g., `IoT devices`. Each device can be a resource.                                          |
| **2. Define Endpoints (URIs)** | Create endpoints like:<br> `/devices` – list or add devices<br> `/devices/<id>` – get, update, or delete a specific device |
| **3. Choose HTTP Methods**     | - `GET`: Retrieve data<br> - `POST`: Create new data<br> - `PUT`: Update existing data<br> - `DELETE`: Remove data         |
| **4. Use JSON Format**         | All input/output should be in **JSON** – it’s lightweight and widely used in REST APIs.                                    |
| **5. Handle Status Codes**     | Return HTTP status codes like `200 OK`, `201 Created`, `404 Not Found`, etc.                                               |
| **6. Use Flask/Framework**     | Choose a web framework like **Flask** to implement API logic.                                                              |

---

### ✅ **Part 2: Python Example using Flask (Code)**

```python
from flask import Flask, jsonify, request

app = Flask(__name__)

# Sample in-memory data store
devices = [
    {"id": 1, "name": "Sensor A", "status": "active"},
    {"id": 2, "name": "Camera B", "status": "inactive"}
]

# GET - Retrieve all devices
@app.route('/devices', methods=['GET'])
def get_devices():
    return jsonify(devices)

# POST - Add new device
@app.route('/devices', methods=['POST'])
def add_device():
    new_device = request.get_json()
    devices.append(new_device)
    return jsonify(new_device), 201

# PUT - Update existing device
@app.route('/devices/<int:id>', methods=['PUT'])
def update_device(id):
    updated_data = request.get_json()
    for device in devices:
        if device["id"] == id:
            device.update(updated_data)
            return jsonify(device)
    return jsonify({"error": "Device not found"}), 404

# DELETE - Remove device
@app.route('/devices/<int:id>', methods=['DELETE'])
def delete_device(id):
    for device in devices:
        if device["id"] == id:
            devices.remove(device)
            return jsonify({"message": "Device deleted"})
    return jsonify({"error": "Device not found"}), 404

if __name__ == '__main__':
    app.run(debug=True)
```

---

### ✅ **Output Format**

All responses will be in **JSON**, e.g.:

```json
{
  "id": 1,
  "name": "Sensor A",
  "status": "active"
}
```

---

### 🏁 **Summary**

* RESTful APIs use **HTTP methods** to manipulate **resources**
* Data is exchanged in **JSON**
* `Flask` makes it easy to build simple, testable APIs

Let me know if you want this as a PDF or handwritten notes version — or if you want a React frontend to call this API (great practice for your MERN stack too)! 🧠🚀
