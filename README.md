# own-class
# Parent class: Smartphone
class Smartphone:
    def __init__(self, brand, model, price):
        self.brand = brand  # Public attribute
        self.model = model  # Public attribute
        self.__price = price  # Private attribute

    def get_price(self):
        return f"The price of {self.brand} {self.model} is ${self.__price}"

    def set_price(self, new_price):
        if new_price > 0:
            self.__price = new_price
            return f"New price updated to ${self.__price}"
        return "Price must be a positive value."

    def call(self, number):
        return f"Calling {number} from {self.brand} {self.model}... 📞"

# Child class: Smartphone with additional features
class SmartPhonePro(Smartphone):
    def __init__(self, brand, model, price, camera_megapixels):
        super().__init__(brand, model, price)
        self.camera_megapixels = camera_megapixels  # New attribute

    def take_photo(self):
        return f"📷 Taking a {self.camera_megapixels}MP photo with {self.brand} {self.model}!"

# Creating objects
phone1 = Smartphone("Samsung", "Galaxy S22", 999)
phone2 = SmartPhonePro("Apple", "iPhone 15 Pro", 1299, 48)

# Accessing methods
print(phone1.get_price())  # ✅ Output: The price of Samsung Galaxy S22 is $999
print(phone2.get_price())  # ✅ Output: The price of Apple iPhone 15 Pro is $1299

print(phone2.take_photo())  # ✅ Output: 📷 Taking a 48MP photo with Apple iPhone 15 Pro!
print(phone1.call("123-456-7890"))  # ✅ Output: Calling 123-456-7890 from Samsung Galaxy S22... 📞

Activity 2 polymorphism challenge

Create a program that includes animals or vehicles with the same action (like move()). However, make each class define move() differently (for example, Car.move() prints "Driving" 🚗, while Plane.move() prints "Flying" ✈️).
# Parent class
class Entity:
    def move(self):
        pass  # Placeholder method for polymorphism

# Child class: Car
class Car(Entity):
    def move(self):
        return "🚗 The car is driving on the road."

# Child class: Plane
class Plane(Entity):
    def move(self):
        return "✈️ The plane is flying in the sky."

# Child class: Lion
class Lion(Entity):
    def move(self):
        return "🦁 The lion is running in the savanna."

# Child class: Fish
class Fish(Entity):
    def move(self):
        return "🐟 The fish is swimming in the water."

# Creating objects
car = Car()
plane = Plane()
lion = Lion()
fish = Fish()

# Using polymorphism
entities = [car, plane, lion, fish]

for entity in entities:
    print(entity.move())  # Calls the move() method of each class
🚗 The car is driving on the road.
✈️ The plane is flying in the sky.
🦁 The lion is running in the savanna.
🐟 The fish is swimming in the water.
