## 🐾 Animal Shelter CRUD app

A backend REST API application for managing an animal shelter. Built with Java and Spring Boot, following a classic layered architecture (controller → service → repository) with a dedicated mapping layer between entities and DTOs.

The project exposes CRUD (Create, Read, Update, Delete) operations for three main resources:

- **Animals** — each with an assigned species (Species)
- **Animal Keepers** — people responsible for the animals
- **Zones** — areas/enclosures that animals are assigned to

  **Architecture**
```
com.animal.animalShelter
├── controllers/        # REST controllers (AnimalController, AnimalKeeperController, ZoneController)
├── domain/
│   ├── dto/            # Data Transfer Objects (AnimalDto, AnimalKeeperDto, ZoneDto, ErrorResponse)
│   └── entities/        # JPA entities (Animal, AnimalKeeper, Zone, Species)
├── mappers/            # Mapper interfaces and implementations (entity ↔ DTO)
├── repositories/       # Data access layer (Spring Data JPA)
└── services/           # Business logic
```

**Tests**
- AnimalControllerIntegrationTest, AnimalKeeperIntegrationTest, ZoneControllerIntegrationTest - REST layer tests
- AnimalEntityIntegrationTest, AnimalKeeperEntityIntegrationTest, ZoneEntityIntegrationTest - repository layer tests
- AnimalShelterApplicationTests - Spring application context test
- TestData - helper/test fixture data

**API Endpoints**

GET
/animals
/zones
/keepers
/animals/zone/{id}
/animals/keeper/{id}
/animals/{id}

POST
/animals/{zone_id}/{keeper_id}
