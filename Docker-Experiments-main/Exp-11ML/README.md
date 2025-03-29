<<<<<<< HEAD
## EXP-1: *Streamlit Spiral Visualization App with Docker*

Welcome to the *Streamlit Spiral Visualization App*! This project demonstrates a simple and interactive Python application built with **Streamlit** to visualize a spiral. You can customize the spiral’s characteristics using adjustable sliders and view the changes in real-time. The app is Dockerized for easy deployment and consistency across environments.

## 🌟 *Features*
- *Interactive Controls*: Use sliders to adjust the number of points and turns in the spiral.
- *Dynamic Visualization*: Watch the spiral change dynamically in response to slider adjustments.
- *Dockerized Application*: The app is packaged within a Docker container, ensuring portability and easy deployment.

## 🚀 *Technologies Used*
- *Python 3*: The core programming language for this app.
- *Streamlit*: A framework for building interactive and beautiful web applications.
- *Altair*: A declarative statistical visualization library for Python used for rendering the spiral.
- *Docker*: Containerizes the app for consistent behavior across different environments.
- *Pandas*: Used for data manipulation and handling data frames.

## ⚙ *Prerequisites*
Before running the application, ensure you have the following installed on your local machine:

- *Docker*: To build and run the app inside a container.
- *Git*: To clone the repository.

If you don't have *Docker* installed, follow the instructions in the official [Docker Installation Guide](https://docs.docker.com/get-docker/).

## 🛠 **Getting Started**
Follow these steps to set up and run the application either locally or inside a Docker container:

### Step 1: **Clone the Repository**
Clone the repository to your local machine by running:

```bash
git clone https://github.com/Aditya5757raj/Docker_Practices

cd Docker_Practices
```

### Step 2: **Create a `requirements.txt` File**
Ensure the project directory includes a `requirements.txt` file containing the necessary dependencies:

```txt
streamlit
altair
pandas
```

### Step 3: **Build the Docker Image**
Build the Docker image from the project directory:

```bash
docker build -t streamlit .
```

This will use the `Dockerfile` to build the image named `streamlit`.

#### **Check If the Image is Built**
After building the image, you can check if it has been created by either:

- **Using Docker Desktop**: Go to the **Images** section to verify if the `streamlit` image is listed.
  
- **Using the Command Line**: Run the following command to list all Docker images:

  ```bash
  docker images
  ```

  This command will display all available images, including the `streamlit` image if it has been successfully built.

### Step 4: **Run the Docker Container**
Start the app inside a Docker container by running:

```bash
docker run -p 8501:8501 streamlit
```

This command will map port `8501` inside the container to port `8501` on your local machine.

### Step 5: **Access the Streamlit App**
After running the container, open your browser and go to:

=======
# 🚢 **Titanic Survival Predictor: Containerized Streamlit App**

## 📌 **Overview**
The **Titanic Survival Prediction Model** is a machine learning application that predicts whether a passenger would have survived the Titanic disaster based on various input features. This project is built using **Python**, **scikit-learn**, **pandas**, and **Streamlit** for a user-friendly web interface. To ensure seamless deployment and portability, **Docker** is used to containerize the application.

---

## 📂 **Project Structure**

```bash
Titanic-Prediction-Model/
│── Dockerfile
│── requirements.txt
│── main.py
│── titanic_model.py
│── titanic_model.pkl
```

### **📜 Description of Files:**
- **`main.py`** → The Streamlit-based web application for user interaction.
- **`titanic_model.py`** → Script to train and save the Titanic survival prediction model.
- **`titanic_model.pkl`** → The serialized machine learning model used for making predictions.
- **`requirements.txt`** → A list of dependencies required to run the application.
- **`Dockerfile`** → Configuration file to containerize the application using Docker.

---

## 🤖 **Model Training (`titanic_model.py`)**
The model is trained using a **Random Forest Classifier** from `scikit-learn`, based on Titanic dataset features. After training, the model is saved as **`titanic_model.pkl`** using `joblib`, ensuring efficient storage and easy loading in the web application.

### **Steps in `titanic_model.py`**
1. **Load the Titanic dataset**.
2. **Preprocess missing values** and encode categorical data.
3. **Train the Random Forest Model**.
4. **Save the trained model** as `titanic_model.pkl`.

---

## 🎨 **Streamlit Application (`main.py`)**
The Streamlit app provides a clean and interactive interface for users to input passenger details and predict survival chances.

### **✨ Features:**
✔️ **User-friendly UI with enhanced CSS**
✔️ **Live prediction updates** using the trained `.pkl` file
✔️ **Interactive sliders and dropdowns** for input selection

---

## 🐳 **Docker Setup**
To containerize the application, a **Dockerfile** is created.

### **📄 `Dockerfile`**
```dockerfile
# Use Python 3.12 slim as base image
FROM python:3.12-slim

# Set working directory
WORKDIR /app

# Copy necessary files
COPY requirements.txt requirements.txt
COPY main.py main.py
COPY titanic_model.pkl titanic_model.pkl

# Install dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Expose the application port
EXPOSE 8501

# Run the Streamlit app
CMD ["streamlit", "run", "main.py", "--server.port=8501", "--server.address=0.0.0.0"]
```

---

## 🚀 **Running the Application with Docker**
Follow these steps to build and run the containerized application:

### **1️⃣ Navigate to the Project Directory**
```bash
cd Titanic-Prediction-Model
```

### **2️⃣ Build the Docker Image**
```bash
docker build -t titanic-prediction .
```

### **3️⃣ Run the Docker Container**
```bash
docker run -p 8501:8501 titanic-prediction
```

### **4️⃣ Access the Application**
Open your browser and navigate to:
>>>>>>> 54d595f (Commit)
```
http://localhost:8501
```

<<<<<<< HEAD
The Streamlit app should now be visible, allowing you to interactively adjust the spiral’s number of points and turns.

## 🌀 **How the App Works**

### **Sliders for Customization**
- **Number of points in spiral**: Controls the number of points that form the spiral.
- **Number of turns in spiral**: Adjusts how many full turns the spiral makes.

### **Real-Time Visualization**
As you adjust the sliders, the spiral is dynamically updated in real-time.

### **Under the Hood**
The app generates the spiral points based on polar coordinates. The `x` and `y` positions are calculated using mathematical functions, and the results are rendered using **Altair** charts in the Streamlit app.

## 🖼 **Results**
Here is an example of the Streamlit Spiral Visualization App in action:

![Running App](image.jpg)

## 💻 **Code Explanation**
- **NamedTuple for Points**: The spiral points are stored as `Point` objects (with `x` and `y` coordinates) using Python’s `namedtuple`.
  
- **Generating Spiral Data**: The total number of points and turns are used to calculate the spiral coordinates. The angle for each point is derived using the polar coordinate system.

- **Streamlit Visualization**: The data is passed to **Altair** for visualization, and the spiral is displayed as a scatter plot, with each point represented as a circle.

## 🛠 **Troubleshooting**
If you encounter any issues, here are a few tips:

1. **Check Docker Logs**: If the container fails to start, use the following command to check the logs:

   ```bash
   docker logs <container_id>
   ```

2. **Ensure Dependencies are Installed**: If there are errors related to missing packages, make sure the `requirements.txt` is correctly copied into the Docker image, and the `pip install` command runs successfully during the Docker build.

## 🤝 **Contributing**
We welcome contributions to improve this project! Here’s how you can contribute:

1. Fork the repository.
2. Create a new branch for your changes.
3. Make the necessary changes and commit them.
4. Push your changes to your forked repository.
5. Open a pull request to merge your changes into the main repository.

---

### Happy Coding! 🎉
=======
---

## 🎯 **Conclusion**
This project demonstrates the deployment of a **machine learning model** using **Streamlit** and **Docker**. The model predicts Titanic survival outcomes based on user input, and the **Dockerized environment** ensures easy portability and deployment.

### 🔥 **Next Steps:**
- 🚀 **Deploy the containerized app** to **AWS, GCP, or Vercel**.
- 🎨 **Enhance the UI** with advanced **Streamlit widgets & visualizations**.
- 🧠 **Improve model accuracy** with additional **feature engineering**.

⚡ **Happy Coding & Containerizing!** 🐳🚢
>>>>>>> 54d595f (Commit)
