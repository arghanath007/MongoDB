Instructions Link -> https://docs.mongodb.com/manual/tutorial/install-mongodb-on-ubuntu/

# Steps:(This are specific to the Ubuntu Init System. I have 'systemd' as my init system. For other init systems the commands may vary. )

1)Start MongoDB -> sudo systemctl start mongod
2)Verify if it is running -> sudo systemctl status mongod
3)Stop MongoDB -> sudo systemctl stop mongod
4)Restart MongoDB -> sudo systemctl restart mongod
5)Begin using MongoDB -> type **mongosh** in terminal. We can use MongoDB Compass as a GUI to connect to the MongoDB server/database.
