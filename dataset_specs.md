### d-01 (.csv) Input parameters

```
"input name" (str), input value (float)
..., ...
```

### d-02 (.3dm) Base geometry

Rhino file with all base geometry.

Layer structure:

### d-03 (.json) Team preference

```
{ "manager name" (str) : 
  { "division" : str, 
    "interns" : int,
    "size" : int,
    "acoustic preference" : int,
    "acoustic importance" : int,
    "light preference" : int,
    "light importance" : int,
    "adjacency-amenity" : 
      { "high" : [str, str, ...] (names of amenities),
        "med" : [str, str, ...],
        "low" : [str, str, ...]
      }
    "adjacency-team" : 
      { "high" : [str, str, ...] (names of team managers),
        "med" : [str, str, ...],
        "low" : [str, str, ...]
      }
  },
  ...
}

### d-04 (.json) Amenity space matrix

