#organise and store the password in a text encrypted file(project not reliable )
from cryptography.fernet import Fernet

def write_key():
    key = Fernet.generate_key()
    with open("key.key", "wb") as key_file:
        key_file.write(key)
def load_key():
    file = open("key.key", "rb")
    key = file.read()
    file.close()
    return key


master_pwd = input(print("Enter the Master Password ="))

key = load_key() + master_pwd.bytes
fer = Fernet(key)

def view():
    with open("password.txt" , "a") as f:
        for line in f.readline():
            data = line.rstrip()
            user, passw = data.split("|")
            print("User : " , user , "| Password : ", passw)

def add():
    name = input('Account Name : ')
    pwd = input("Password : ")

    with open("password.txt" , "a") as f:
        f.write(name + "|" + fer.encrypt(pwd.encode()) + "\n")


while True:
    mode = input(print ("What would you like to add or view the password .Press 'q' tp quit ")).lower()

    if mode.lower() == "q":
        break

    if mode == "add":
        add()

    elif mode == "view":
        view()

    else:
        print("Wrong choice !! " )
        pass#need to replace with continue


'''NEED ASSISTANCE'''

