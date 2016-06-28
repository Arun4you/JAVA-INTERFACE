                            #INTERFACE
#	Interface can be impelemented in classes by the keyword “IMPLEMENTS”
#	If a class implements interface, it should have all methods used in the interface. override heyword is used to overide the methods in classes.
#	Interface used for passing the object to other methods:
    public static void saveObject(ISaveable objectToSave) {
        for(int i=0; i<objectToSave.write().size(); i++) {
            System.out.println("Saving " + objectToSave.write().get(i) + " to storage device");
        }
    }

    public static void loadObject(ISaveable objectToLoad) {
        ArrayList<String> values = readValues();
        objectToLoad.read(values);
    }
In above method, ISaveable is an interface. The reason behind using like below,
public static void saveObject(ISaveable objectToSave)
is to call the methods in the interface class. write() method is called directly using the object as “i<objectToSave.write()” is by defining the object “objectToSave” as interface. The interface “ISaveable” has only two methods, read() and write().
#	All the instances in the class can be passed to the methods by passing through the object created for initialising the class.
Player tim = new Player("Tim", 10, 15);
saveObject(tim);
#	The instances passed through the object can be retrieved by using for loop as below.
public static void saveObject(ISaveable objectToSave) {
        for(int i=0; i<objectToSave.write().size(); i++) {
            System.out.println("Saving " + objectToSave.write().get(i) + " to storage device");
        }
    }

