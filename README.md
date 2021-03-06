# Spring Boot React
The application has a react frontend and a Spring Boot Rest API, packaged as a single module Maven application.
You can start the application (`make local-deploy`) and call the API by using the following curl (shown with its output):

---

### Local Test
```bash 
curl -v -u greg:turnquist localhost:8080/api/employees/
```

### Production Test

```bash 
curl -v -u greg:turnquist <domain_name>/api/employees/
```

json payload should look like below
```json
{
    "firstName": "Frodo",
    "lastName": "Baggins",
    "description": "ring bearer",
    "manager": {
        "name": "greg",
        "roles": [
            "ROLE_MANAGER"
        ]
    },
"links": {
        "self": {
            "href": "http://localhost:8080/api/employees/1"
        }
    }
}
```

### Cloud Integration
You should have a CI/CD pipeline to iteratively improve the project.
To deploy it on AWS by using `CDK` see the following repository in [here](https://github.com/umutykaya/cdk-spring-pipeline).

---

To see the frontend, navigate to http://localhost:8080. You are immediately redirected to a login form. Log in as `greg/turnquist`
