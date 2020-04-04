
# Setup on Mac
- Anaconda
- pydotplus
- tensorflow-gpu
- material


## Anaconda
a python dev environment specifically for machine-learning

### Download && Install
1. anaconda.com, download
2. macOS
3. Python3.x version
4. Open installer, continue...continue...
5. Open Terminal (_new terminal_)
6. conda install pydotplus
  - y to continue
7. conda install tensorflow
  - makes deep neural networks
  - y to proceed

### Coure materials
http://sundog-education.com/machine-learning/

### Python Notes
- python syntax overview
  - whitespace matters
  - importing modules ```import mod as m```
  - lists (~js arrays)
    - ```thisArr.length``` ~ ```len(thisArr)```
    - thisArr[:numberHere] returns first numberHere element of list
    - thisArr[numberHere:] return last numberHere elements
    - merge 2 lists using arr1.extend(newArr)
  - Tuples
    - immutable lists
    - handy for functional programming or systems like Apache Spark
    - ```thisTuple = (1,2,3)```
    - ```len(thisTuple)```
    - ```thisTuple[1]```
  - Dictionaries
    - like a map/hashtable/object
    - ```thisDict = {}``` 
    - ```thisDict["animal"] = "dog" ```
   - Functions
	   - lambda are inline nameless fns
	   - ```lambda param: param logic```
	   - USING: ```lambda x: x * x, 3``` should return 9
   - Looping

###Some practice
- make an arr of random numbers
- loop through arr
- if number is even
	- print/log the number

```
# make arr of numbers
thisArr = [8,6,7,5,3,8,9]

# loop through the list
for n in thisArr:
    if n % 2 is 0:
        print(n)
  ```



