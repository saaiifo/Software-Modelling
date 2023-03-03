# Software-Modelling
Assignment 1 ICS220

# Code

import datetime
from enum import Enum

class Gender(Enum):
    Female = 1
    Male = 2

class Nationality(Enum):
    Emirati = 1
    Omani = 2
    Saudi = 3

class customer:
    def __init__(self, f_name: str, l_name: str, gender: Gender, phone_num: str, nationality: Nationality):
        self.first_name = f_name
        self.last_name = l_name
        self._gender = gender
        self._phone_num = phone_num
        self._nationality = nationality
        
    def getfirst_name(self):
        return self.first_name
    
    def setfirst_name(self, value):
        self.first_name = value
    
    def getlast_name(self):
        return self.last_name
    
    def setlast_name(self, value):
        self.last_name = value
    
    def get_gender(self):
        return self._gender
    
    def set_gender(self, value):
        self._gender = value
    
    def get_phone_num(self):
        return self._phone_num
    
    def set_phone_num(self, value):
        self._phone_num = value
    
    def get_nationality(self):
        return self._nationality
    
    def set_nationality(self, value):
        self._nationality = value
        
    def print_customer_details(self):
        print(f"Name: {self.getfirst_name()} {self.getlast_name()}", f"\nGender: {self.get_gender().name}",f"\nPhone number: {self.get_phone_num()}",f"\nNationality: {self.get_nationality().name}")
        
customer1 = customer(f_name='Saif', l_name='Alkatheeri', gender=Gender.Male, phone_num='0502874652', nationality=Nationality.Emirati)
customer2 = customer(f_name='Khalid', l_name='Alkatheeri', gender=Gender.Male, phone_num='0500192854', nationality=Nationality.Emirati)

customer1.print_customer_details()
print('\n\n')
customer2.print_customer_details()

from enum import Enum

class Make(Enum):
    toyota = 1
    lexus = 2
    nissan = 3

class Model(Enum):
    avalon = 1
    lx570 = 2
    m4 = 3

class Service:
    class Type(Enum):
        oil = 1
        tire = 2
        brake = 3
    
    def __init__(self, service_type, cost, duration, availability, mechanic):
        self.service_type = service_type
        self.cost = cost
        self.duration = duration
        self.availability = availability
        self.mechanic = mechanic

class Car:
    def __init__(self, make: Make, model: Model, year: int, color: str, ID: str, service: Service):
        self._make = make
        self._model = model
        self._year = year
        self._color = color
        self._ID = ID
        self._service = service
        
    def get_make(self):
        return self._make
    
    def get_model(self):
        return self._model
    
    def get_year(self):
        return self._year
    
    def get_color(self):
        return self._color
    
    def get_ID(self):
        return self._ID
    
    def get_service(self):
        return self._service
    
    def set_make(self, value):
        self._make = value
        
    def set_model(self, value):
        self._model = value
        
    def set_year(self, value):
        self._year = value
        
    def set_color(self, value):
        self._color = value
        
    def set_ID(self, value):
        self._ID = value
        
    def set_service(self, value):
        self._service = value

    def print_details(self):
            print(f"Make: {self._make.name}")
            print(f"Model: {self._model.name}")
            print(f"Year: {self._year}")
            print(f"Color: {self._color}")
            print(f"ID: {self._ID}")
            print(f"Service: {self._service.service_type.name}")

car1 = Car(make=Make.toyota, model=Model.avalon, year=2020, color='pearl white', ID='232FGT23', service=Service(Service.Type.oil, 100, 60, 'Mon-Sat', 'Shamnaz'))
car2 = Car(make=Make.lexus, model=Model.lx570, year=2009, color='silver', ID='454JPT45', service=Service(Service.Type.tire, 200, 90, 'Mon-Fri', 'Shamnaz'))

print('\n\n')
car1.print_details()
print('\n\n')
car2.print_details()
print('\n\n')

class Receipt:
    def __init__(self, customer: customer, car: Car, service: Service, total: float):
        self.customer = customer
        self.car = car
        self.service = service
        self.total = total
    
    def print_receipt(self):
        print(f"Customer Name: {self.customer.getfirst_name()} {self.customer.getlast_name()}")
        print(f"Cell Phone Number: {self.customer.get_phone_num()}")
        print(f"Date: {datetime.date.today()}")
        print(f"Mechanic Name: {self.car.get_service().mechanic}")
        print(f"Vehicle Type: {self.car.get_make().name} {self.car.get_model().name}")
        print(f"Vehicle Color: {self.car.get_color()}")
        print(f"Vehicle ID: {self.car.get_ID()}")
        print(f"Service: {self.service.service_type.name}")
        print(f"Total: {self.total}")



receipt1 = Receipt(customer=customer1, car=car1, service=car1.get_service(), total=100)
receipt1.print_receipt()

print('\n\n')

receipt2 = Receipt(customer=customer2, car=car2, service=car2.get_service(), total=200)
receipt2.print_receipt()
