- **Big Data is an application area for modern computer science.**
	- Describe what Big Data is, using examples to illustrate your description
	- Explain some of the challenges that Big Data brings with it and the approaches that can be taken to overcome these, in relation to programming hardware
	- Consider some of the ethical and legal issues that might arise in applications that store data, particularly data about people
<br>


```
Big data is a term for datasets which are so large or complex that they cannot be processed or stored using traditional data management tools. It can be divided into 3 properties, Volume, Velocity and Variety. Volume representing the fact that the data is too large to fit on a singular server, Velocity reffering to the speed of the data being generated and Variety reffering to the fact that the data is represented in many forms. 

The problems with Big Data are as follows: Storage, Processing speed, scalabilty and fault tolerance. I'll begin by expanding on the first point, Storage, which attracts the idea that the data may span enourmous amounts of data which all needs to be stored somewhere that has even greater capacity. The next point is, Processing speed, in which analysing data needs to be incredibly fast in order to stay usefull and this can be difficult with singular machines. Furthermore data must grow as the data grows and this makes a huge demand on storage and processing speed etc. Lastly at such scale hardware failures become a matter of when and not if and in many case data cannot be lost. The approaches that can be taken to overcome these challenges are using more computers; spreading the processing across multiple machines which work in parallel. Cloud computing can be used so that there isnt such a dependency on physical hardware.

Some of the ehtical issues that can arise are due to privacy. Personal data such as names, addresses, emails and medical records must be kept private as many users expect the organisation that thye ar eusing to protect their data and not expose it to third parties. The issue with this is that a if a data breach were to occur many peoples data could be stolen and used with malicious intent. Another ethical and legal issue is constent. Users must know what data is being collected and they must agree to it requiring the organisation to provide clear privacy policies and ask for permission. The issue with this is companies collecting or selling user data without the knowledge of the user. Another issue is that considering how much resources that is required for Big Data it leads onto the thought that the power draw from places such as data centres will be immense
```
<br><br>
- - -

## What are the features of functional programming which make it useful for working with Big Data distributed across multiple servers?

```
One feature of funtional programming that makes it useful for working with Big Data is statelessness, this is because functions do not rely on data. Each function depends only on its input and always produces the same output.

Another feature is the fact that they are immutable, where once created, data cannot be changed which eliminates the side effects caused by shared, mutible state.

Another feature is high order functions bcause of the fact that we can take in a function as a parameter rather then the data. This enables concise and re-usable data transfomations.

Lastly another one is order of execution can be determined at runtime. You can change the order that the functions are run as they only take one thing and return one thing so the order can be changed.
```