# Функция для расчета погрешности
def calculate_error(m1, m2):
    return abs(m1 - m2)

# Расчет процента погрешности
def calculate_percentage_error(error, m1):
    return (error / m1) * 100

# Функция для проверки погрешности
def is_within_limit(m1, m2, limit_percentage=4):
    error = calculate_error(m1, m2)
    percentage_error = calculate_percentage_error(error, m1)
    return error, percentage_error, percentage_error <= limit_percentage

# Пример значений
m1 = float(input("Введите значение m1: "))
m2 = float(input("Введите значение m2: "))

# Проверка 
error_value, percentage_error, is_within = is_within_limit(m1, m2)

# Вывод 
print(f"\nВеличина погрешности: {error_value:.2f}")
print(f"Процент величины погрешности: {percentage_error:.2f}%")
if is_within:
    print("Погрешность находится в пределах 4%.")
else:
    print("Погрешность превышает 4%.")
