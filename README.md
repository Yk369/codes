import random
def equation(x):
    return -(x**2) + 4*x 
def hill_climbing(func, start, step_size=0.1, max_iterations=1000):
    current_solution = start
    current_value = func(current_solution)
    for _ in range(max_iterations):
        neighbor_solution = current_solution + random.choice([-1, 1]) * step_size
        neighbor_value = func(neighbor_solution)
        if neighbor_value > current_value:
            current_solution = neighbor_solution
            current_value = neighbor_value
    return current_solution, current_value
 
start_point = random.uniform(-10, 10)  
max_solution, max_value = hill_climbing(equation, start_point)
 
print(f"Maximized solution: {max_solution}")
print(f"Maximized value: {max_value}")
