classDiagram

class BaseModel {
    +UUID id
    +datetime created_at
    +datetime updated_at
    +save()
    +update()
    +delete()
}

class User {
    +string first_name
    +string last_name
    +string email
    +string password
    +boolean is_admin
    +register()
    +update_profile()
    +delete_user()
}

class Place {
    +string title
    +string description
    +float price
    +float latitude
    +float longitude
    +create_place()
    +update_place()
    +delete_place()
}

class Review {
    +int rating
    +string comment
    +create_review()
    +update_review()
    +delete_review()
}

class Amenity {
    +string name
    +string description
    +create_amenity()
    +update_amenity()
    +delete_amenity()
}

BaseModel <|-- User
BaseModel <|-- Place
BaseModel <|-- Review
BaseModel <|-- Amenity

User "1" --> "0..*" Place : owns
User "1" --> "0..*" Review : writes
Place "1" --> "0..*" Review : receives
Place "0..*" -- "0..*" Amenity : has
