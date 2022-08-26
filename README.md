# NetApp_Volume
Python program that connects to NetApp server using RestAPI, lets user create volume into a specific Storage VM  from NetApp server


### Features
- `CREATE` a StorageVM into a given storage
- Helpful CLI

### Requirements
- Python 3.6 or higher
- ONTAP 9 (NetApp storage system) or higher (untested on earlier versions)
- Install docopt

Check [install docopt](https://pypi.org/project/docopt/) for more information


### Usage Example
## Run the program


1. Creating a Volume

```bash
create_vol.py -s [STORAGE] -vm [SVM] -VN [VOLUME] [SIZE]
```  		

4. HELP
```
create_vol.py -h | --help
```

- [STORAGE] => name of your storage
- [SVM] => name of StorageVM
- [VOLUME] => name of Volume you want to create
- [SVM] => Size of the volume that will be created


##FLOWCHART

```mermaid
flowchart LR
    S([Start]) --> I[/Input:<br>- Storage<br>- StorageVM<br>- Volume name<br>- Size of Volume/]
    I --> C{Check if<br>Volume name is<br> valid}
    C --YES--> Y{Create Volume}
    Y --SUCCESS--> X{Check if Volume<br>already Exist}
    X --YES--> Q>Success]
    X --NO--> W>Volume Already running]
    Y --FAILED-->  N>Failed to create<br>Display ERROR]
    C --NO--> F>Invalid Volume name]
    F --> E([STOP])
    N --> E
    Q --> E
    W --> E



```