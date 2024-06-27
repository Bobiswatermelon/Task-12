grid = [
    ["-", "-", "-", "#", "#"],
    ["-", "#", "-", "-", "-"],
    ["-", "-", "#", "-", "-"],
    ["-", "#", "#", "-", "-"],
    ["-", "-", "-", "-", "-"]
]

size_x = len(grid)
size_y = len(grid[0])

# Print the initial grid
for i in range(0, size_x):
    print(grid[i])

grid2 = grid

for i in range(0, size_x):
    for j in range(0, size_y):
        count = 0
        for a in [i-1, i, i+1]:
            for b in [j-1, j, j+1]:
                if a >= 0 and b >= 0:
                    if a < size_x and b < size_y:
                        if grid[a][b] == '#':
                            count += 1
        if grid[i][j] == '#':
            count -= 1
        print(i, j, ':', count)
        grid2[i][j] = count

# Print the updated grid with bomb counts
for i in range(0, size_x):
    print(grid2[i])

    # Check if all cells in the row have zero bomb counts
    if all(cell == 0 for cell in grid2[i]):
        print("-")

