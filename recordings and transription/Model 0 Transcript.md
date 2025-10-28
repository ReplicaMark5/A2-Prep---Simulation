
In this video we shall model a fast food drive thru outlet. Let's meet our client now. He does not own a farm. He owns a fast food drive through outlet and the customers are waiting and waiting. He considered giving up business but then decided to call the Mask Simulation wonder. Here he is. Thank you. Thank you Donkey. Let's do the model now we shall develop a model of the process and adjust the number of cooks in the kitchen to see if it has an effect on the process. This is how the completed simulation model will look. When you open Technomatics, you go to File Preferences and then on the License tab you select Educational and you click Server and you complete the name, year, license 2stB, Sun, AC ZA. Make sure you type the name correctly, otherwise the license server will not respond. 
S
Speaker 1
01:03
Once you have done that, close Technomatics and open it again. You can see here we have what we call a canvas, this white area. And here at the bottom we have different frames. The main frame is this one and you can see here on the left hand side the class library and we have a toolbar here. If you don't see these, go to window and make sure you enable Class library and the toolbox. We drag and drop the objects here on the toolbar, on the canvas or on the frame to develop our model to give you an overview. These objects here form the arrival of the cars, the ordering, the payment at the casual and the collection of the final order. The object here at the bottom model the kitchen. So we have a buffer for the kitchen. 
S
Speaker 1
01:49
We have the kitchen object itself and then a buffer where the orders that are completed will wait. In this model, when the order is being placed, we will create an entity that goes to the buffer in the kitchen or the queue to resemble the order. Once the order is finished, it will queue here in the completed area and it will then be assembled with the waiting car here in the collection resource. So that's the overview of the model. Let's start with a clean canvas. When you open Technomatics, you click on Create a new model and select 2D. Conceptually we have two entities arriving in the system, that is the car and the order that emerges from the car. In Technomatics we call them moving entities. MU's. 
S
Speaker 1
02:37
We want to create moving units for this model and although we can use existing ones, let's have fun and create our own. We right click on part under MU's and we click on Duplicate. An instance of the part object will be formed under User Objects. We can double click on it and we rename it order. The order needs a number because we shall assign this same number to the car that brings it into the model. And we shall use the order number to give it to the correct car on exit. So we click on the tab user defined and we add an attribute order number. Remember, it is one word, the type is integer and the initial value is 0. Click OK and OK again. So now we have defined the first mu. A transporter is a car. 
S
Speaker 1
03:32
So we duplicate the parent Object Transporter under MU's and name it car. We need to define an attribute for the car which is also the order number. Whenever a car arrives, we shall assign a value to the attribute order number. To define the attribute, look at the tabs, then scroll to the right until you see the tab named user defined. Click on it and click New. Then enter the same name order number. The type again is integer and you can leave all the other settings as is. Click OK and ok. Now we have the car and the order. We can now start with the model on the canvas. So on the Material flow tab, go to the object source, click on it and drop it somewhere on the canvas. Double click on the source to edit it. 
S
Speaker 1
04:40
We see that the inter arrival times are specified here. You can also specify starting and stopping time. Change the time between arrivals to be negatively exponential distributed with a mean of 5 minutes. Type 5 Colonial, enter 0. In technomatics we indicate the time elements with colon. So the format is day, colon, hour, colon, minute, colon, second and so on. So if you do it like this, five colon zero, it means zero seconds and five minutes. This means that every five minutes on average there is an arrival to start. Means we can offset the arrivals with a certain time period. Suppose we open the shop at 8 o' clock and the first customer usually comes only after 15 minutes. Then we specify the arrival times, otherwise we leave it. We can also stop the arrival entities. 
S
Speaker 1
05:32
So this object called source will create entities and will inject them into the model. Click ok. At this point we want to create car so we can drag the car and drop it on the object. You will see a little arrow that forms there. When you double click on source, you will see at mu it says userobjects car. We could also select it here by clicking on the ellipse and select object and select Car. It does not matter which way you do it. Now the cars must queue at the ordering window. To model queue, we use a buffer object from the Material flow tab, place the buffer next to the source, open it and rename it to buffer ordering. Make the Capacity minus one, which means it is infinite, so the arrival queue is infinite. Click ok. The ordering window is a resource. 
S
Speaker 1
06:39
So drag a station from the Material Flow tab and place it next to the buffer. Rename it to Ordering and set the processing time to negative exponential. The time it takes to process is about three minutes. Leave all the other requirements in their default state. So in all following videos, if nothing is said about a field in the dialog, leave it as is. Click ok. Now customers can queue and order. To model the payment window, place a buffer from the Material Flow tab and name it Buffer Casual. The capacity of this buffer is 3 when entering the 3 there. It means that from the ordering window you can only proceed to the casual if there are less than three cars in front of you. To model the casual, add the station to the right of the buffer casier and rename it to Casier. 
S
Speaker 1
07:59
Set the processing time again to negative exponential and the time is 1.5 minutes. Now click OK. Now add another buffer and name it Buffer Collect. Its capacity is 2. Add another station and name it Collect. The processing time is negative exponential with a mean of one minute. This is where the customer collects the order that will be forwarded by the kitchen. Place a drain object to the right of Collect. This is where entities exit the model. Make the processing time constant for two minutes. This is not necessary, but it will help you later when you want to inspect entities that are leaving. We now model the kitchen. For the kitchen, we also model a queue. So we drag and drop a buffer on the canvas and call it Buffer Kitchen. 
S
Speaker 1
09:09
We make the capacity infinity because you can place as many orders as you want at the kitchen. It is not guaranteed that they will be executed, but you can still do it. Click ok. It's a good time to save your model. Then, of course we have a resource in the kitchen. For the kitchen, we place a parallel station and we call it Kitchen. It has dimensions X and Y. This means that you have 2x2 service station here, which means you actually have four resources. We want a parallel resources system. So we leave the x dimension at 2 and change the y dimension to 1. This means we have two cooks working in parallel. 
S
Speaker 1
09:50
If x equals 2 and y 2, for example, it means the entity must be processed by one service channel that is one of the X's, and it has to be processed by two resources in sequence in the Y dimension. So keep Y at one. Later we shall change the X dimension to a point more cooks or less cooks and see what the effects are. Now click the Times tab and Specify the time as negative exponential with a mean of 12 minutes. Click OK. To the right of the kitchen object, place another buffer, name it Buffer orders completed. It has infinite capacity. Once the cook has completed the order, it will be placed here. Click the Times tab and enter the dwell time as constant, which is one minute. Now place a station and name it Cycle. 
S
Speaker 1
10:55
The processing time is constant and very short, so we enter. The reason for this station will be explained later. Save your model again. So far so good. You now need to connect the object, so click on the connector in the Material Flow tab. Because you want to connect many objects, you can hold down the control button and click on the first source, then on the buffer and so on. Make sure that you connect the objects as shown on the canvas. Sometimes students click the first object and miss the second one and then click the third one. Also connect the kitchen objects, click the end of the cycle station and connect it to the beginning or the entrance of the buffer or this complete object. When done, press Escape. The model is complete. 
S
Speaker 1
12:01
In terms of objects, we need to refine some processes with custom code to realize the real world process. First we need to define two variables. From the Information Flow tab, add two variables on the canvas. Double click on the first and name it numcooks. Its type is integer and we can initialize it to 3 for the moment. We shall later vary the value of this variable to increase or decrease the number of cooks in the model. Click OK and double click the second variable and name it Count ordernum. Its initial value should be zero. We shall increment the value of this variable each time a car arrives. Then assign that value as its order number. You can thus see that the order numbers will grow sequentially. To increment the variable value, we need to write code. 
S
Speaker 1
13:05
We do this using the built in code of Dictumatics called symtorg. We can embed the code into objects on the canvas or write the code in methods that are placed on the canvas. Then we attach the methods to the objects. Let's write our first piece of code in a method. From the Information Flow tab, drag a method object and place it on the canvas. Right click on it and rename it to mincrement order number. I start the names of all my methods with an M. Double click on the method and enter the code as shown. The first line increments the variable countordernum. Note that we assign values to variables using a colon and an equal sign. 
S
Speaker 1
14:03
While we use only an equal sign when comparing, that symbol refers to the current entity or mu so we assign the variable value to the attribute of this the current entity. The next entity, when it arrives, will receive a different value for order number, and that is exactly what we want. The entity will stay here in the code unless we tell it to move. To compile the code, press F7 or click the green check mark on the right of the ribbon at the top of the main TPS window, then close the method. You may also leave it open. Doesn't matter. To attach the method to an object, we double click the source object, then click the Controls tab. And we want to invoke the method when the entity leaves the object. 
S
Speaker 1
14:51
So type the name of the method in the line labeled exit, or click on the ellipses. Choose Select Object and choose a name from the list. You will have only one name to pick from at the moment. Click ok. Each time an entity exits the source object, it will be stamped with a unique order number by means of this code. Next, we transfer the number of cooks to the kitchen parallel station. You can say we configure as we like. TPS offers at least two useful standard methods named INIT and nsim. When one calls init, it executes the code in the init method before the model starts to execute, while intsim executes when the model ends execution. These methods are optional. We need an init, so drag another method from you know where and rename it to initial. 
S
Speaker 1
15:53
You will see the name changes to red. Because it is a standard method, pause the video and add the following code. We adjust the xterm attribute of the kitchen object to num cooks, which we specified. Of course, correct sparing is recommended here. TPS offers autocomplete, so when you see the name you need, press Ctrl and spice bar. Spacebar is where astronauts hang out. The collect exit locked closes the collect object so that the car cannot leave the model. In other code, we shall make it true. Once the car has received its order, you can view it as a boom. We lower, and when a car can leave, we lift the boom, press F7 and close the method. There are two major things to do now. First, we need to duplicate an arriving entity and make the duplicate an order entity. 
S
Speaker 1
16:43
This entity must be sent to the kitchen buffer, so whenever a car has placed its order, the order must enter the kitchen queue, not sooner and not later. The second task is to ensure that an order and its correct customer are joined. This is a major validation issue, and when we do not attend to it carefully, customers and orders will be mixed up. There are two possibilities to take in mind, the first is a car may proceed through the processes after the collect resource and its order is still being processed. The car thus has to wait and it cannot collect any completed orders, if there are any. The second possibility is that an order may be completed, but the car is still in the process, so it is delayed at the casier. 
S
Speaker 1
17:30
This order must thus be held back until its car enters the collect resource. Imagine the scenario where you are in the process with one car in front of you. It is possible that your order is completed, but that of the car in front of you is not. So the car in front of you must wait until its order is completed before you can collect yours. The synchronization of cars and orders is very important. When an order is taken, you have to inform the kitchen, so I want to show you how to use extra code to achieve that. Double click on Ordering and go to the Controls tab. You can see that it is possible to model an entity's entrance, exit and setup. You might model setup times here. 
S
Speaker 1
18:11
For example, when you process a product on a machine for this model, it is not necessary. We want to create an order and send it to the kitchen when an entity has finished its ordering. So click in the exit field and press F4 to go to the syntalk editor. Each entity that exits this object will first execute the code. We will enter here, pause the video and complete the code as shown. The code will now be explained. We indicate comments in symtalk with two hyphens. You can also place comments next to a line of code. The object p is a variable that points to a new order created. When we create an mu, we need to tell Technomatics where to place it. So in this case we specify buffer kitchen. 
S
Speaker 1
19:03
We then tell this mu, which has an attribute order number to assume the value of the attribute order number of the active entity. Remember, we refer to the active entity with the symbol before we close this window. We need to apply these changes again by pressing F7 or clicking on Apply Changes in the Edit Ribbon. If you want to return to this embedded piece of code, you click in the exit field again and then press F2 to open the code. Remember, you pressed F4 to create it. You can click OK. Next we write code to ensure that the right order and car are associated. Place another method on the canvas and name it M Order Move. Open it and add the following code. Remember to F7 the code. The code is explained as follows. The wait until statement does what it says. 
S
Speaker 1
20:13
It will wait until the condition becomes true. In this case, we check if there are any entities in collect. The attribute num mu is number of MU's and TPS changes it when an entity enters and exits an object. So the order entity in the buffer orders completed object when it arrives will check if there is at least one car waiting. Note that it is not guaranteed that it is this order's car. If there is a car, the order entity will proceed to the next line of code and check if its order number is the same as that of the car at collect. The term collect cont order number refers to the contents of collect, I.e. The mu and the dot order number refers to the attribute order number of that mu. 
S
Speaker 1
21:00
So you can see that we refer to the number of the car in the collect object. Note that there can be only one car at the time present in the collect because it is a single station. If the order numbers agree, the code will move the entity in buffer orders completed, which is executing this code to the contents of collect, that is it will merge with the car. Beautiful. Open the buffer orders completed object and click the Controls tab. Associate this method with the entrance event. The buffer order's completed object has a dwell time of one minute. Then it moves to the cycle process where it is delayed for a short time. This happens to an order that could not find its R. This trick allows for TPS to take the order entity out of the active state and tend to other entities. 
S
Speaker 1
21:57
Otherwise an infinite loop will result. The order is sent to the buffer order completed object again and it tries to access its car again. We must now code the collect object so that it accepts its order. Drag another method on the canvas and rename it to mmerge. Order, car and Order. Open it and enter the following code. We open the guide here. Remember we closed it in the init method. The question mark refers to the current object, I.e. Collect. Remember the add refers to the active entity and it waits until there is an entity joining it. The car and other leave and lock the exit again. F7 the code, close the method and associate it with the entrance of the collect object. Now let's run the model for some time. First open the event controller and click on the Settings tab. 
S
Speaker 1
23:31
We shall run the model for six hours, so at the end line we type six and two columns. When you press Apply, you can see that the zeros are filled in, which represent hours, minutes and seconds. Ignore the other options for the moment, click ok. Go to the event controller bar on the roam on the ribbon which is currently set on full blast and make it slower here. Let's see what happens when we run the code. There is the ordering object with a car waiting there. And here are the orders entering the buffer kitchen and staying here in the kitchen. You can see there are currently three orders being processed. And we have three cooks in the kitchen. This poor entity is looking for its car. If we hover on this car, its details are shown. 
S
Speaker 1
24:40
We can also see the little square which is our package with unhealthy tasteless food by clear. So it's named order and this is named car. You can see the car has number five and the order is number five. Here you can see the car is four and the order is four. That's why we added a two minute delay on the drains so that you can see the correct order and car are merged. You can see count order number is currently at 35. We want to experiment with the simulation model and create scenarios. Remember, we use simulation to answer what if questions. For example, what will happen if we change the number of cooks here at the kitchen to four? What will be the effect on the time it takes or the number of orders being processed? 
S
Speaker 1
25:27
When we run it again, we can make it faster and see that the six hour process can be executed in a few seconds. But first let's define our experiment. We want to change the number of cooks in the kitchen in order to see how many oars we can process in six hours. So we shall count the number of cars that exit the model. To make this easier for ourselves, we have already written the code in Method Init to change the number at the kitchen's X dimension. Let's see if it works. We reset the model and take one step. So if you open the kitchen you will see that the X dimension is set to 3. Let's make it 1, 2, 3 and make nunclks. For example 14. We reset the model and we step again. 
S
Speaker 1
26:32
If you open the kitchen, you can see the X dimension has been set to 14, which is the num cooks variable there. So this process works. So your question can be why don't I just change the value here at kitchen instead of changing it at Numcrooks? Well, this takes us to the next step. We shall define the number of experiments. Go to the tools tab and drag and drop the experiment manager on the canvas. We want to count how many cars exit through the drain so we know how many customers we service per six hours. To see what statistics the drain can give us, we select the drain and press F8. Technomatics gives us all the statistics and Properties of the drain. We can see here all the stats available and if we scroll down we see the stat NUM out. 
S
Speaker 1
27:33
This is the statistic for the number of moving units that leave this object. Close this dialog. Now back to the experiment manager. Double click it, then click Define Output Values. And our output value would be the drain statnumelp. Click Apply and ok. This is case insensitive. You can make a description here, but you can also leave it blank. And you can see that you can add many more output values. For the moment we only study this one output value. To select the input values, we select the tick box and we click Define Input Variables. It is a variable we want to experiment with. We can type NUM cooks here, or you can simply drag and drop numcooks here. 
S
Speaker 1
28:32
In this field click Apply and ok. Now you can see that we can change the number of cooks and it will show me what the number of entities was that exited the drain. So we define the experiments. So we have one cook for the first, experiment, two for the second, and so on. Click ok. Technomatics will now automatically run the five experiments and each time changes to Num Cooks, which will be adjusted again then by the INIT method. Let's make the observations per experiment 10 for the moment. Now click on the Evaluation tab, make sure you have selected the confidence interval option here and click Apply. Click Reset, then start. The run has been completed and you can see we executed five experiments and ten observations per experiment. We can now look at the output report. 
S
Speaker 1
29:42
So Technomatics shows your model here and it also shows the plot of the confidence intervals with the point estimators as dots in the middle. So from left to right it is experiment 1, 2, 3, 4 and 5. Here is a table of the detail of the output. So in the first column it shows you the point estimators, then the standard deviations, the minimum and maximum observations and importantly the left and right interval bounds of the confluence intervals. You can use these to determine your instar. Also shown is the P table and you can clearly see that experiment two is the cheapest that we should implement. Let's go back to the experiment manager because I want to show you the individual observations per experiment. Again click on the Evaluation tab and then click on Detailed Results. 
S
Speaker 1
30:34
We'll see the same table as in the report, but the last column contains the detailed observations. If I open table one for experiment one, you can see the detail observations per replications. If you take the average of these values, you should get the same average as Technomatics for this experiment. In this way, we can inspect individual observations. If we change the observations per experiment to 100, for example, click apply reset and start. The experiments are executed and the observations per experiment are made. So let's look at the results. The confidence intervals are much smaller because we made 100 observations instead of 10. If we look at the ptable, you can analyze it and see that experiment three is now the clear winner. So with ten observations, we concluded that experiment two is the winner. 
S
Speaker 1
31:42
It shows you that we need sufficient observations to make valid conclusions from the simulation results. The work of the mask simulation wonder is now complete. So what happens next? You will ride off into the sunset and find a place to light a fire. 