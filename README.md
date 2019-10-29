# project-with-classes-not-finished

import json
class hotelbook:
    def __init__(self):
        with open("hotels.json") as data_file:
            self.data = json.load(data_file)

    def find_by_phone(self, phone_number):
        for i in self.data:
            if i["phone"] == phone_number:
                return i["hotel_name"]

    def find_by_star(self, star):
        for i in self.data:
            if i["star_rating"] == star:
                return i["hotel_name"]

    def per_night(self, money):
        for i in self.data:
            if i["single_room_price"] == money:
                return i["hotel_name"]

def main():
    print("This app is for finding hotels")
    flag = True
    Hotel = hotelbook()
    while flag:
        action = int(input(
            "Please input what you want (1 - for search based on PhoneNumber, 2 - For gettingthe best hotel based on money, 3 - for search based on stars): "))
        if action == 1:
            phonenumber = input('Please input your phone number')
            data = Hotel.find_by_phone(phonenumber)
            print(data)
            # object = Hotel(data)
            # method that takes out needed data from object
        elif action == 2:
            money = Hotel.user_input_money()
            data = Hotel.getMoney(money)
            # object = Hotel(data)
            # method that takes out needed data from object

        elif action == 3:
            money = Hotel.user_input_money()
            desiredStars = Hotel.user_input_desiredStar()
            data = Hotel.getStars(money, desiredStars)
            # object = Hotel(data)
            # method that takes out needed data from object

        else:
            print(" Wrong action")
    while True:
        phone = input('please input the phone number')
        name_of_hotel = Hotel.find_by_phone(phone)
        print(name_of_hotel)

main()
