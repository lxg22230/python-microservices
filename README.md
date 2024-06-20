### Key Components of the Project

1. **Django Admin App**:
   - Built using Django and Django REST Framework.
   - Handles product management (CRUD operations).
   - Uses MySQL for the database.
   - Communicates with the Flask app via RabbitMQ.

2. **Flask Main App**:
   - Built using Flask.
   - Handles user interactions and product likes.
   - Uses MySQL for the database.
   - Receives events from the Django app via RabbitMQ.

3. **RabbitMQ**:
   - Used for event-driven communication between the Django and Flask apps.
   - Events include product creation, updates, and deletions.

4. **Docker**:
   - Both apps are containerized using Docker.
   - Docker Compose is used to manage multi-container applications.

### Suggested README Structure

#### Project Title
```
# Python Microservices with Django, Flask, and RabbitMQ
```

#### Description
```
This project demonstrates a microservices architecture using Python, Django, Flask, and RabbitMQ. The system consists of two main services: an admin service built with Django for managing products and a main service built with Flask for user interactions. The services communicate through RabbitMQ, enabling an event-driven architecture.
```

#### Table of Contents
```
- [Installation](#installation)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [Endpoints](#endpoints)
- [Event-Driven Architecture](#event-driven-architecture)
- [Docker Setup](#docker-setup)
- [Contributing](#contributing)
- [License](#license)
```

#### Installation
```
## Installation

1. **Clone the repository**:
   ```bash
   git clone https://github.com/scalablescripts/python-microservices.git
   cd python-microservices
   ```

2. **Set up the environment**:
   Ensure you have Docker and Docker Compose installed on your machine.

3. **Build and run the containers**:
   ```bash
   docker-compose up --build
   ```

4. **Run database migrations**:
   For Django:
   ```bash
   docker-compose exec backend python manage.py makemigrations
   docker-compose exec backend python manage.py migrate
   ```

   For Flask:
   ```bash
   docker-compose exec flask python manager.py db init
   docker-compose exec flask python manager.py db migrate
   docker-compose exec flask python manager.py db upgrade
   ```
```

#### Usage
```
## Usage

1. **Access the Django Admin App**:
   Open your browser and navigate to `http://localhost:8000/admin`.

2. **Access the Flask Main App**:
   Open your browser and navigate to `http://localhost:8001`.

3. **Testing APIs**:
   Use tools like Postman to test the API endpoints.
```

#### Project Structure
```
## Project Structure

```
- `admin/`: Django admin app for managing products.
- `main/`: Flask main app for user interactions.
- `docker-compose.yml`: Docker Compose configuration file.
- `Dockerfile`: Dockerfile for building the Docker images.
- `requirements.txt`: Python dependencies for both apps.
```

#### Endpoints
```
## Endpoints

### Django Admin App
- `GET /api/products/`: List all products.
- `POST /api/products/`: Create a new product.
- `GET /api/products/<id>/`: Retrieve a product.
- `PUT /api/products/<id>/`: Update a product.
- `DELETE /api/products/<id>/`: Delete a product.

### Flask Main App
- `GET /api/products/`: List all products.
- `POST /api/products/like`: Like a product.
```

#### Event-Driven Architecture
```
## Event-Driven Architecture

The Django and Flask apps communicate through RabbitMQ. Events such as product creation, updates, and deletions are published by the Django app and consumed by the Flask app to maintain data consistency across services.
```

#### Docker Setup
```
## Docker Setup

The project uses Docker to containerize the applications. Docker Compose is used to manage the multi-container setup.

### Building and Running Containers
```bash
docker-compose up --build
```

### Stopping Containers
```bash
docker-compose down
```
```

#### Contributing
```
## Contributing

Contributions are welcome! Please open an issue or submit a pull request for any improvements or bug fixes.
```

#### License
```
## License

This project is licensed under the MIT License. See the LICENSE file for details.
```
