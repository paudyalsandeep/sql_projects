# Universe Database

The Universe Database is a PostgreSQL project designed to model celestial bodies such as galaxies, stars, planets, and moons. This project includes tables with various attributes and relationships to represent the structure of the universe.

## Database Schema

The database contains the following tables:

1. **Galaxy**: Stores information about different galaxies.
   - `galaxy_id` (Primary Key)
   - `name` (Unique, Not Null)
   - `description`
   - `galaxy_type`
   - `distance_from_earth` (NUMERIC)
   - `has_life` (BOOLEAN)

2. **Star**: Stores information about stars within galaxies.
   - `star_id` (Primary Key)
   - `name` (Unique, Not Null)
   - `galaxy_id` (Foreign Key referencing `galaxy`)
   - `star_type`
   - `age_in_millions_of_years` (INT)
   - `is_spherical` (BOOLEAN)

3. **Planet**: Stores information about planets orbiting stars.
   - `planet_id` (Primary Key)
   - `name` (Unique, Not Null)
   - `star_id` (Foreign Key referencing `star`)
   - `planet_type`
   - `has_life` (BOOLEAN)
   - `distance_from_star` (NUMERIC)

4. **Moon**: Stores information about moons orbiting planets.
   - `moon_id` (Primary Key)
   - `name` (Unique, Not Null)
   - `planet_id` (Foreign Key referencing `planet`)
   - `has_life` (BOOLEAN)
   - `is_spherical` (BOOLEAN)
   - `age_in_millions_of_years` (INT)

5. **Spacecraft**: Stores information about spacecraft.
   - `spacecraft_id` (Primary Key)
   - `name` (Unique, Not Null)
   - `mission`
   - `launch_date` (DATE)
   - `is_operational` (BOOLEAN)
