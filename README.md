# **SmartDataFlow: Scalable Clustering & Data Mart on Spark**

**Overview**
SmartDataFlow is an **end-to-end data processing and clustering pipeline** built using **Apache Spark, Scala, Python, and Kubernetes**. The project integrates a scalable clustering model with a unified data mart and an Oracle database, providing seamless data retrieval, pre-processing, and analytics.

This pipeline demonstrates how modern big data tools can be combined for **efficient, modular, and production-ready data solutions**.

---

## **Key Features**

* **Data Clustering:** K-Means clustering implemented on large datasets using PySpark.
* **Unified Data Mart:** Scala-based service offering a standardized protocol for querying and preprocessing data.
* **Database Integration:** Oracle 21c as the main data source (extensible to PostgreSQL, MySQL, HBase, etc.).
* **Containerized Deployment:** Docker and Kubernetes for isolated, scalable environments.
* **End-to-End Workflow:** Model → Data Mart → Database, without direct coupling between components.

---

## **Architecture**


<img width="750" height="512" alt="15a6395f-fbb1-4b6d-9040-6c3e919a3d66" src="https://github.com/user-attachments/assets/2f18b84b-857a-408b-8c24-72771868ffb7" />



* **Oracle DB:** Stores source data and serves as a central repository.
* **Data Mart:** Receives model requests, pre-processes data, and interacts with the database.
* **Spark Model:** Runs clustering tasks on the pre-processed data and returns results.

---

## **Tech Stack**

* **Data Processing:** PySpark, Scala
* **Database:** Oracle 21c
* **Containerization:** Docker
* **Orchestration:** Kubernetes
* **Programming Languages:** Python, Scala

---

## **Project Structure**

```
/src        # PySpark model code
/datamart   # Scala-based data mart service
/kubernetes # Kubernetes deployment manifests
/docker-compose.yml # Orchestrates DB, model, and data mart
```

---

## **Getting Started**

1. **Clone the repository**

```bash
git clone https://github.com/ghfranj/SmartDataFlow.git
cd SmartDataFlow
```

2. **Deploy all services to Kubernetes**

```bash
kubectl apply -f kubernetes/
```

3. **Verify deployments**

```bash
kubectl get deployments
```

*Screenshot included: `deployments_running.png`*

4. **Check services**

```bash
kubectl get services
```

*Screenshot included: `services_running.png`*

5. **Check pods**

```bash
kubectl get pods
```

*Screenshot included: `pods_running.png`*

6. **Access Spark UI**

```
http://localhost:4040
```

7. **Query Data Mart API**

```
http://localhost:9000
```

---

## **Usage Example**

Once the services are running:

1. Send a query to the data mart API to request data for clustering.
2. The Spark model processes the data and returns clustering results.
3. Results are stored back or can be retrieved via the data mart service.

This workflow ensures **clean separation of responsibilities** between the database, data mart, and model.

---

## **Screenshots of Running Services**

**1. Deploy Services to Kubernetes**
*(Command: `kubectl apply -f kubernetes/*.yml`)*
<img width="1055" height="234" alt="Deploy Services to Kubernetes" src="https://github.com/user-attachments/assets/64f0e4d3-20ba-47cf-b1ba-32fb53640fc6" />

**2. Deployments Running**
*(Command: `kubectl get deployments`)*
<img width="881" height="134" alt="deployments running all" src="https://github.com/user-attachments/assets/deafee3f-0f6a-4575-95d3-f4bf2ff5a899" />

**3. Services Running**
*(Command: `kubectl get services`)*
<img width="923" height="135" alt="services with helm" src="https://github.com/user-attachments/assets/3c5c018a-53b5-43e8-bead-2672d012cd40" />

**4. Pods Running**
*(Command: `kubectl get pods`)*
<img width="963" height="158" alt="pods running all together" src="https://github.com/user-attachments/assets/5e4701dd-58d5-440c-9307-fe7600d45fcd" />



