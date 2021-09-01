# Spring REST

* In order to properly use new dependencies in your project, you might need to run `mvn clean package`.
* Return `id` of entity in all response DTOs.
* Remember about [REST resource-naming convention](https://restfulapi.net/resource-naming/).
* In your mappers prefer setters over big constructors while converting entity to dto and vice versa.
* Use Stream API while working with lists in your mappers.
* In your MovieSessionRequest/ResponseDtos, we don't need to pass the whole information about Movie and CinemaHall - 
their ids will be enough.
* When creating a MovieSession, if you need to accept `LocalDateTime` in request body - 
add `jackson-datatype-jsr310` dependency to be able to parse it into MovieSessionRequestDto.
* Your method names in controllers and mappers should have uniform names.

Bad example:
```
public MovieResponseDto createMovie(@RequestBody MovieRequestDto movieRequestDto) { ... } 
// better just use `create()`

public List<MovieResponseDto> getAll() { ... }
```

Another bad example for mapper:
```
public CinemaHallResponseDto parse(CinemaHall cinemaHall) { ... }
// better use `parse()` name for both methods or `toDto()` for this method

public CinemaHall toModel(CinemaHallRequestDto cinemaHallRequestDto) { ... }
```
* When deleting a MovieSession on dao layer, double-check that you are not opening another Session
in your currently opened Session.
