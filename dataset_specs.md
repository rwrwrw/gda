### d-01 (.csv) Input parameters

```
"input name" (str), input value (float)
..., ...
```

### d-02 (.3dm) Base geometry

Rhino file with all base geometry.

Layer structure:
- circulation - separate polylines indicating all vertical circulation routes

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
```

### d-04 (.json) Amenity space matrix

```
{ "amenity name" (str) :
    { "quantity" : int,
      "size" : float
    },
    ...
}
```

### d-05 Floor mesh

Quad mesh representing walkable surface of design across two floors.

### d-06 Amenity polylines

Polyline outlines of amenity spaces.

### d-07 Desk center points

```
[ 
    { "coords" : [x, y, z],
      "dir" : [x, y, z],
      "neighborhood" : int
    },
    ...
]
```

### d-08 Daylight grid

```
[
    { "pos" : [x, y, z],
      "val" : float
    },
    ...
]
```

### d-09 Graph assignment data

```
{   
    "neighborhoods" :
        { 
            neighborhood id (int) : [graph node id for desks (int), ...],
            ...
        },
    "amenities" :
        {
            "amenity name" (str) : [graph node ids (int), ...],
            ...
        }
}
```

### d-10 Graph data

```
{ "nodes" :
      [
          { "coords" : [x, y, z] },
          ...
      ]
  "edges" :
      {
          start node index (int) : { 
              end node index (int) : edge cost (float),
              ...
          },
          ...
      }
}
          
```

### d-11 Team assignment data

```
{
    "manager name" (str) : [ graph node id for desks (int), ...],
    ...
}
```

### d-12 Amenity location data

```
{
    "name of amenity" (str) : [ [ x, y, z ], ... ],
    ...
}
```

### d-13 Node traversal data

```
{
    graph node id (int) : number of traversals (int),
    ...
}
```

### d-14 Edge traversal data

```
{
    graph node id (int) : {
        graph node id (int) : number of traversals (int),
        ...
    },
    ...
}
```

### d-15 Distraction data

```
{
    graph node id for desk (int) : score (float),
    ...
}
```

### d-16 Buzz graph

```
{ "nodes" :
      [
          { "id" : node id in full graph (int),
            "coords" : [x, y, z], 
            "traversal": number of traversals (int) 
          },
          ...
      ]
  "edges" :
      {
          ( start node index (int), end node index (int) ) (tup) : number of traversals (int),
          ...
      }
}
          
```
