#
print  ("Developer - не только разработчик")

class House:
    def __init__(self, name, number_of_floors):
        self.name = name
        self.number_of_floors = number_of_floors

    def go_to(self, new_floor):
        if (new_floor > self.number_of_floors or new_floor < 1):
            print("Такого этажа не существует")
        else:
            for i in range (1, new_floor+1):
                print(f"Опять сломали лифт в {self.name}, ножками, этаж!  {i} из {new_floor}")
    def __len__(self):
        return   self.number_of_floors

    def __str__(self):
        return 'Название: ' + self.name + ", кол-во этажей " + str(self.number_of_floors)

    def __eq__(self, other):
        if  isinstance (other, House):
            return   self.number_of_floors == other.number_of_floors
        else:
            return False

    def __lt__(self, other):
        if  isinstance (other, House):
            return   self.number_of_floors < other.number_of_floors
        else:
            return False

    def __le__(self, other):
        if  isinstance (other, House):
            return   self.number_of_floors <= other.number_of_floors
        else:
            return False

    def __gt__(self, other):
        if isinstance(other, House):
            return self.number_of_floors > other.number_of_floors
        else:
            return False

    def __ge__(self, other):
        if isinstance(other, House):
            return self.number_of_floors >= other.number_of_floors
        else:
            return False

    def __ne__(self, other):
        if isinstance(other, House):
            return self.number_of_floors != other.number_of_floors
        else:
            return False

    def __add__(self, value):
        if isinstance(value, int):
            self.number_of_floors += value
        return self


# не очень понятно, зачем, но в ТЗ есть
    def __radd__(self, value):
        return __add__(self, value)

    def __iadd__(self, value):
        return __add__(self, value)



h1 = House('ЖК Эльбрус', 10)
h2 = House('ЖК Акация', 20)


print(f"Меньше {h1 < h2}")
print(f"Больше {h1 > h2}")
print(f"Равно {h1 == h2}")
print(f"Не равно {h1 < h2}")
print(f"Меньше или равно {h1 <= h2}")
print(f"Больше или равно {h1 >= h2}")


print(f"Было в {str(h1)}")
h1 = h1 + 3 # достроили три этажа
print(f"Стало в {str(h1)}")




# __str__
#print(h1)
#print(h2)

# __len__
#print(len(h1))
#print(len(h2))
