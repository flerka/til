C# naive implementation
```cs
public class Solution
 {
        /// <summary>
        /// Input is the grid where int is vertex weight.
        /// We start at the up left grid vertex.
        /// We need to find shortest path to the bottom right grid vertex. 
        /// </summary>
        public static int Solve(List<List<int>> input)
        {
            Dictionary<(int, int), bool> visited = new();
            Dictionary<(int, int), int> distances = new();
            for (int i = 0; i < input.Count; i++)
            {
                for (int k = 0; k < input.Count; k++)
                {
                    distances[(k, i)] = int.MaxValue;
                }
            }

            distances[(0, 0)] = 0;
            var last = (0, 0);
            while (last != (input.Count - 1, input.Count - 1))
            {
                visited[last] = true;
                var neighbors = GetNeighbors(last, (input.Count, input.Count));
                foreach (var neighbor in neighbors)
                {
                    if (distances[neighbor] > distances[last] + input[neighbor.Item2][neighbor.Item1])
                    {
                        distances[neighbor] = distances[last] + input[neighbor.Item2][neighbor.Item1];
                    }
                }

                var distance = int.MaxValue;
                foreach (var key in distances.Keys)
                {
                    if (!visited.ContainsKey(key) && distances[key] < distance)
                    {
                        distance = distances[key];
                        last = key;
                    }
                }
            }

            return distances[(input.Count - 1, input.Count - 1)];
        }
}
```

C# heap implementation
```cs
public class Solution
 {
        /// <summary>
        /// Input is the grid where int is vertex weight.
        /// We start at the up left grid vertex.
        /// We need to find shortest path to the bottom right grid vertex. 
        /// </summary>
        public static int Solve(List<List<int>> input)
        {
            var data = new Dictionary<(int, int), int>();

            Dictionary<(int, int), int> distances = new();
            for (int i = 0; i < input.Count; i++)
            {
                for (int k = 0; k < input.Count; k++)
                {
                    data[(k, i)] = input[i][k];
                    distances[(k, i)] = int.MaxValue;
                }
            }

            Dictionary<(int, int), bool> visited = new();
            distances[(0, 0)] = 0;

            var pq = new PriorityQueue<(int, int), int>();
            pq.Enqueue((0, 0), 0);
            while (pq.Count > 0)
            {
                var last = pq.Dequeue();
                visited[last] = true;
                var neighbors = GetNeighbors(last, (input.Count, input.Count));
                foreach (var neighbor in neighbors)
                {
                    if (visited.ContainsKey(neighbor))
                    {
                        continue;
                    }

                    if (distances[neighbor] > distances[last] + data[neighbor])
                    {
                        distances[neighbor] = distances[last] + data[neighbor];
                        pq.Enqueue(neighbor, distances[last] + data[neighbor]);
                    }
                }
            }

            return distances[(input.Count - 1, input.Count - 1)];
        }
}
```