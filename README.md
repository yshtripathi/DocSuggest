[DocSuggest.postman_collection.json](https://github.com/user-attachments/files/20241627/DocSuggest.postman_collection.json)# 🩺 DocSuggest – Doctor Suggestion Platform

DocSuggest is a backend system developed using Spring Boot (v3) that allows doctors to register their profiles and enables patients to find the right doctors based on their symptoms and location. This application fulfills the requirements outlined in the **Java Technical Assignment by Xcelore**.

---

## 🚀 Features

- ✅ Add and remove doctors with specialization and limited city values
- ✅ Add and remove patients with predefined symptoms
- ✅ Suggest doctors based on patient’s symptom and city
- ✅ Validation for all input fields
- ✅ RESTful APIs with Swagger documentation

---

## 🛠️ Tech Stack

- **Spring Boot 3**
- **Hibernate/JPA**
- **H2 / MySQL Database**
- **Swagger (OpenAPI)**
- **Lombok**
- **Postman** (for API testing)

---

## 📁 Project Structure

```
DocSuggest/
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   └── com.example.docsuggest/
│   │   │       ├── controller/
│   │   │       ├── entity/
│   │   │       ├── repositories/
│   │   │       ├── services/
│   │   │       ├── util/
│   │   │       └── DocSuggestApplication.java
│   │   └── resources/
│   │       ├── application.properties
├── README.md
├── postman_collection.json
└── pom.xml
```

---

## ✅ API Endpoints

### 🔹 Doctor APIs

- `POST /api/doctors` – Add new doctor  
- `DELETE /api/doctors/{id}` – Remove doctor    

### 🔹 Patient APIs

- `POST /api/patients` – Add new patient  
- `DELETE /api/patients/{id}` – Remove patient   

### 🔹 Suggestion API

- `GET /api/suggest-doctor?patientId={id}` – Suggest doctor(s) based on patient’s symptom and city

---

## 📌 Validations

| Field         | Rule                                 |
|---------------|--------------------------------------|
| Name          | At least 3 characters                |
| City          | Max 20 characters                    |
| Email         | Must be valid email format           |
| Phone Number  | At least 10 digits                   |
| Doctor City   | Only Delhi, Noida, Faridabad allowed |
| Speciality    | One of: Orthopaedic, Gynecology, Dermatology, ENT |
| Patient Symptom | Must map to known categories        |

---

## ❗ Edge Cases

- **Outside Supported City:**  
  ➤ Response: *“We are still waiting to expand to your location”*

- **No Doctor for Symptom in Location:**  
  ➤ Response: *“There isn’t any doctor present at your location for your symptom”*

---

## 📸 Screenshots

```md
![Add Doctor](https://github.com/user-attachments/assets/387b3420-7e55-4dfe-9fc5-8e178b040cb0)
![Delete Doctor](https://github.com/user-attachments/assets/3a442268-7ae0-4153-b1fd-7bba3a56ea9b)
![Add Patient](https://github.com/user-attachments/assets/7f0636e9-7c48-42ab-ab75-5bfbc1c00815)
![Delete Patient](https://github.com/user-attachments/assets/303f7e11-bdb9-4f38-9157-2013bc1ff48c)
![Edge Case 1](https://github.com/user-attachments/assets/b9cc25e9-acf8-4022-a8c9-1a73eb708853)
![Edge Case 2](https://github.com/user-attachments/assets/614c68fb-42b5-4d6b-b188-609248176e8f)
```

---

## 🔗 Postman Collection
[Uploa{
	"info": {
		"_postman_id": "8d6e7e8d-f840-4f58-b26d-62219c6f6ece",
		"name": "DocSuggest",
		"schema": "https://schema.getpostman.com/json/collection/v2.1.0/collection.json",
		"_exporter_id": "42761692"
	},
	"item": [
		{
			"name": "Patient",
			"item": [
				{
					"name": "Add Patient",
					"request": {
						"method": "POST",
						"header": [],
						"url": {
							"raw": "http://localhost:8080/patients",
							"protocol": "http",
							"host": [
								"localhost"
							],
							"port": "8080",
							"path": [
								"patients"
							]
						}
					},
					"response": []
				},
				{
					"name": "Delete Patient",
					"request": {
						"method": "DELETE",
						"header": [],
						"url": {
							"raw": "http://localhost:8080/patients/1",
							"protocol": "http",
							"host": [
								"localhost"
							],
							"port": "8080",
							"path": [
								"patients",
								"1"
							]
						}
					},
					"response": []
				}
			]
		},
		{
			"name": "Doctor",
			"item": [
				{
					"name": "Add Doctors",
					"request": {
						"method": "POST",
						"header": [],
						"url": {
							"raw": "http://localhost:8080/doctors",
							"protocol": "http",
							"host": [
								"localhost"
							],
							"port": "8080",
							"path": [
								"doctors"
							]
						}
					},
					"response": []
				},
				{
					"name": "Delete Doctor",
					"request": {
						"method": "DELETE",
						"header": [],
						"url": {
							"raw": "http://localhost:8080/doctors/1",
							"protocol": "http",
							"host": [
								"localhost"
							],
							"port": "8080",
							"path": [
								"doctors",
								"1"
							]
						}
					},
					"response": []
				}
			]
		},
		{
			"name": "New Request",
			"request": {
				"method": "GET",
				"header": [],
				"url": {
					"raw": "http://localhost:8080/patients/suggest-doctor/1",
					"protocol": "http",
					"host": [
						"localhost"
					],
					"port": "8080",
					"path": [
						"patients",
						"suggest-doctor",
						"1"
					]
				}
			},
			"response": []
		}
	]
}ding DocSuggest.postman_collection.json…]()



---

## 🧪 How to Run

1. Clone the repo  
   ```bash
   git clone https://github.com/your-username/DocSuggest.git
   cd DocSuggest
   ```

2. Run the Spring Boot application  
   ```bash
   mvn spring-boot:run
   ```

3. Access Swagger UI (if enabled):  
   [http://localhost:8080/swagger-ui.html](http://localhost:8080/swagger-ui.html)


**Note:** This project was created as part of the **Java Technical Assignment for Xcelore.**
