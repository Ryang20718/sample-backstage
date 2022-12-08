# Sub Module

```
# Accept a set of points as input
points = [(1, 2), (3, 4), (5, 6), (7, 8), (9, 10)]

# Iterate over the set of points and calculate the distances between each pair of points
distances = []
for i in range(len(points)):
  for j in range(i+1, len(points)):
    x1, y1 = points[i]
    x2, y2 = points[j]
    distance = ((x1 - x2)**2 + (y1 - y2)**2)**0.5
    distances.append((distance, (x1, y1), (x2, y2)))

# Sort the distances in ascending order
distances.sort()

# Identify the three pairs of points with the smallest distances
nearest_points = distances[:3]

# Plot the coordinates of the three points on a graph and connect them with lines to form a triangle
import matplotlib.pyplot as plt
for distance, point1, point2 in nearest_points:
  x1, y1 = point1
  x2, y2 = point2
  plt.plot([x1, x2], [y1, y2], 'k-')

# Show the graph
plt.show()
```