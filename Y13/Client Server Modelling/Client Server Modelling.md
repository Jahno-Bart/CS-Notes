
# Client–server technologies

Most of the services that you use on the internet are based on client–server architecture. In this model, there are client applications that make requests for services and servers that send a response to each request.

### Client–server model
The **client–server model** is how most things work on the internet.

- **Server**  
  - The computer/program that **provides** the resource (web page, email, file, video, etc.)  
  - Runs 24 hours a day, 7 days a week  
  - Listens quietly on a specific **port** (e.g. port 80 for normal web pages using HTTP)  
  - Is **passive** — it waits for someone to ask for something  
  - When it gets a request → it sends back the requested resource  
  - If the server stops working → nobody can access the websites/emails/services it hosts

- **Client**  
  - The computer/program that **asks** for the resource  
  - Examples:  
    - Web browser (Chrome, Firefox, Safari) → asks for web pages  
    - Email app (Outlook, Gmail app, Thunderbird) → asks for emails  
  - Sends a correctly formatted request to the server  
  - Waits for the server to send the answer back

**Very simple flow**  
Client → sends request → Server (listening) → receives request → sends resource back → Client shows/uses it

- - -

## Client-side processing
**Client-side processing** = anything done on the **client** computer (not on the server).

Almost every web interaction includes some work done by the client.

## Main example: Web browser
- The browser is the client software.
- What it does:
  - Takes HTML (structure) and CSS (styling) from the server → turns it into a nice-looking webpage.
  - Runs **JavaScript** code (scripts) sent by the server.
- JavaScript can do things like:
  - Check if a form is filled in correctly (validation)
  - Make parts of the page change without reloading (dynamic features, e.g. dropdown menus, image sliders, live updates)

## Why do processing on the client?
- Saves server work → server doesn’t have to do everything
- Uses less internet bandwidth → client handles some tasks locally
- Can use local data, e.g.:
  - **Cookies** stored on your computer → personalise the page (remember login, theme, shopping cart)
<br>

## Security points
**Risks**:
- Malicious JavaScript can be sent (just like good JavaScript)
- Bad code could try to harm your computer

**How browsers protect you**:
- Scripts run in a **sandbox** — a safe, locked box
- Sandbox rules:
  - Cannot touch your operating system
  - Very limited access to files (only cookies and similar small things)
  - Can only read/write data for its own website (same-origin policy)
- Cannot do dangerous things outside its own little world

>**Very important rule**:
>- Always keep your browser **up to date**
>- Browser companies quickly fix security holes when found
>- Old/outdated browsers = one of the easiest ways hackers attack your computer
- - -
<br>

# Server-side processing

**Server-side processing** = all the work done on the **server** computer (not on the user's device).

The server creates or changes content before sending it to the client.

## Main role: Web server
- Builds custom webpages using data from:
  - Databases (products, prices, user info)
  - Files
  - Other systems
- Examples:
  - Shows your personalised shopping cart
  - Displays current stock and special offers
  - Logs you in and shows your account details

## Server-side languages & tools
Common languages used on the server ("back-end"):
- PHP
- ASP.NET
- Python (very popular with frameworks like Django or Flask)
- Node.js (JavaScript on server)
- Ruby, Java, etc.

**Web frameworks** (like Django, Laravel, Express):
- Make it faster and easier to build dynamic websites
- Handle common jobs (connecting to database, routing requests, security basics)

- - -

## How server-side processing works (simple example: placing an order online)

1. You fill in an order form on the website  
   (Browser might do quick checks using JavaScript – client-side)

2. You click "Submit"  
	- Browser sends the form data to the server (using HTTP POST request)

3. Server sees it's a "dynamic" request  
	- Passes the data to the right server-side program (e.g. PHP script or Python code)

4. Server-side script runs:
   - Checks the data
   - Saves the order to the database (SQL query)
   - Creates a new HTML page (e.g. "Thank you! Your order #1234 is confirmed")
   - May also:
     - Reduce stock levels
     - Send you a confirmation email
     - Tell the warehouse system about the order

5. Server sends the freshly created HTML page back to your browser  
   (With status 200 = success, or an error code if something failed)

6. Your browser shows the confirmation page

- - -

## Why developers prefer server-side processing

Advantages:
- **Full control** — developer knows exactly what software/versions are on the server
- **Code is hidden** — users cannot see or copy the server scripts
  → Protects business logic, algorithms, security code
  → Harder for hackers to find weaknesses
- **Powerful hardware** — servers can handle heavy tasks (database queries, calculations, file processing) much better than phones/laptops
- **Central security** — easier to keep data safe, validate everything properly, prevent cheating

In short:  
Server does the important, secret, heavy work → sends only the finished, safe result to the browser.

- - -
<br>
## CRUD and REST APIs

REST (Representational State Transfer) is an architecture style for developing web services that specify the use of distinct Hypertext Transfer Protocols for all four CRUD (Create/Retrieve/Update/Delete) operations. A web application is defined as RESTful when it adheres to the REST standard. It should be noted that the standard is far wider than just using the correct HTTP method.

The table can be extended to include the Hypertext Transfer Protocol that map to the four basic operations:

|**Operation**|**SQL**|**HTTP method**|
|---|---|---|
|Create|INSERT|POST|
|Retrieve|SELECT|GET|
|Update|UPDATE|PUT|
|Delete|DELETE|DELETE|

If you have previously done some web development, you may have used the GET and POST methods. Many students use these two methods interchangeably with little regard for their documented purpose (and this is possible as you will have coded both the client and server end of the process). It is likely that many of you have not used the PUT or DELETE methods at all.

The important thing about RESTful applications is that they allow client and server to be programmed independently, yet interact successfully without either knowing the implementation details on the other side. In a RESTful system, the client sends a request that the server performs a particular action (such as updating a resource). The request must contain all of the information necessary for the server to be able to process the request. Once the server has performed the action, it sends a response (often in XML or JSON format).

This RESTful approach has been widely adopted for many APIs (Application Programme Interfaces) where the use of standards has resulted in APIs that are easier to provide, use, document, and support.

### CRUD

CRUD is an acronym that represents the four basic operations relating to persistent data (i.e. data stored in files or databases). When you develop an application, you must always consider whether you have implemented the functionality to allow all four operations. For example, if you are making an online revision tool: will the teacher be able to CREATE new questions? Will the teacher be able to UPDATE questions if they need to be changed? Will the teacher be able to DELETE questions that are no longer needed? Will the teacher be able to RETRIEVE a specific set of questions?

SQL maps neatly to CRUD as shown in the table below.

| **Operation** | **SQL** |
| ------------- | ------- |
| Create        | INSERT  |
| Retrieve      | SELECT  |
| Update        | UPDATE  |
| Delete        | DELETE  |
- - -
<br>
## Thin client vs thick client

### Thin client

Most processing and data storage occurs on the server.
Client mainly handles input/output and display.
**Examples:** web applications in a browser, terminal services.

- Advantages:
  - Lower hardware requirements for client devices.
  - Centralised updates, security, and maintenance.
  - Easier to manage large numbers of clients.

- Disadvantages:
  - Requires constant network connection.
  - Performance depends heavily on network speed and server capacity.

### Thick client (fat client)

Significant processing and possibly local data storage on the client.
Client performs much of the computation and only requests specific data/services.
**Examples:** desktop applications (e.g. word processors with local files), some games.

- Advantages:
  - Can function offline or with limited connectivity.
  - Faster response times for local tasks.
  - Reduced network traffic for some operations.

- Disadvantages:
  - Higher hardware requirements for clients.
  - More difficult to update software across many clients.
  - Security patches and data consistency harder to manage.

## Advantages of client–server networks
- Centralised management of data, security, user accounts, and backups.
- Strong access control and authentication (e.g. login systems).
- Data consistency - only one copy of files/databases to maintain.
- Easy to scale by upgrading the server or adding more servers.
- Allows access to resources from any authorised client device.
- Suitable

- - -
<br>
# The use of standards (and protocols) on the internet

The internet only works because everyone follows the **same rules** — these are called **standards** and **protocols**.

Without agreed standards, computers, phones, servers, and browsers couldn’t understand each other → the internet would stop working.

## Two main types of standards

### 1. De jure standards  
("by law" / official standards)

- Created and managed by **official organisations** or expert groups.
- Formally approved and regulated.
- Everyone must follow them for things to work properly.

Examples:
- **ICANN** — controls domain names (like .com, .org) and IP addresses  
  → makes sure every website address is unique and works everywhere
- **JPEG** (Joint Photographic Experts Group)  
  → official standard for compressing photos (created 1992, still updated today)  
  → almost every photo on the web uses JPEG because it’s the agreed standard

### 2. De facto standards  
("in fact" / unofficial but widely used)

- Not forced by any official body.
- Became standard just because **most people/companies started using it**.
- You can ignore them — nothing will stop you — but things might look/work worse if you do.

Examples:
- Using **sans-serif fonts** (Arial, Helvetica, etc.) for most web text  
  → it’s become the normal choice for readability on screens  
  → but you can use fancy fonts like Garamond or Comic Sans — nobody will block you, it just might look strange or hard to read
- Many web design habits (e.g. blue underlined links for visited pages) started as common practice, not official rules

## Why standards matter

- **Interoperability** — any browser can open any website, any email app can send/receive from any server
- **Consistency** — images look the same everywhere, websites behave predictably
- **Innovation** — new devices and software can join the internet easily because they follow the same rules
- **Prevents chaos** — without standards, every company would do things differently → nothing would connect properly

In short:  
**De jure** = official, enforced rules (must follow for core internet to work)  
**De facto** = popular habits that everyone copies (you can break them, but it’s usually better not)

- - -
<br>
# JSON and XML

JSON and XML are both popular **standards** for sending and storing data between systems (data interchange).

## JSON (JavaScript Object Notation)

- Stands for **JavaScript Object Notation**
- Managed by **ECMA** (official standards group)
- Name includes "JavaScript" but it is **language-independent** — works with Python, Java, C#, etc.
- **Open source** and free to use

### Main features
- **Human-readable** (easy to read and write)
- Built on two simple structures:
  - Ordered **lists** of values (arrays)
  - **Name/value pairs** (like a dictionary or object)
- Very **compact** — short and clean
- Easy and **fast** for computers to read/write (parse/generate)
- Clearly separates numbers (1) from text ("1")
- Supports basic types: strings, numbers, booleans, arrays, objects, null

### Example (colour palette)
```json
{
  "palette": [
    {
      "name": "red",
      "code": "#ff0000",
      "rgb": {"red": 255, "green": 0, "blue": 0}
    },
    {
      "name": "orange",
      "code": "#ffa500",
      "rgb": {"red": 255, "green": 165, "blue": 0}
    }
    // ... more colours
  ]
}

```  

### Advantages
- Short and simple
- Fast to process
- Widely used (almost every modern web API uses JSON)  

### Disadvantage
- Only supports a few basic data types (no dates, no binary data natively)  

<br><br>

## XML (Extensible Markup Language)

- Stands for Extensible Markup Language
- Alternative to JSON for moving data around

### Main features

- Uses tags like HTML (<tag>content</tag>)
- Every opening tag needs a matching closing tag
- More verbose (longer) than JSON
- Very strict structure

### Example (same colour palette)
```xml
{
  <palette>
    <code>#ff0000</code>
    <name>red</name>
    <rgb>
      <red>255</red>
      <green>0</green>
      <blue>0</blue>
    </rgb>
    
    <code>#ffa500</code>
    <name>orange</name>
    <rgb>
      <red>255</red>
      <green>165</green>
      <blue>0</blue>
    </rgb>
    <!-- ... more colours -->
  </palette>
}
```

### XML Schema (rules for the data)

- You can write a schema (like a blueprint)
- Defines:
  - Which tags must exist
  - Order of elements
  - Data types (string, integer, etc.)
  - Required or optional fields
  - Default values

- Checks that the XML follows the rules → catches mistakes early

### Example (simple schema snippet)
```xml
{
  <xs:schema>
    <xs:element name="palette">
      <xs:complexType>
        <xs:sequence>
          <xs:element name="name" type="xs:string"/>
          <xs:element name="code" type="xs:string"/>
          <xs:element name="rgb">
            <xs:complexType>
              <xs:sequence>
                <xs:element name="red" type="xs:integer"/>
                <xs:element name="green" type="xs:integer"/>
                <xs:element name="blue" type="xs:integer"/>
              </xs:sequence>
            </xs:complexType>
          </xs:element>
        </xs:sequence>
      </xs:complexType>
    </xs:element>
  </xs:schema>
}
```
### Quick comparison: JSON vs XML

| Feature              | JSON                                      | XML                                       |
|----------------------|-------------------------------------------|-------------------------------------------|
| Readability          | Very easy and clean                       | More wordy (lots of opening + closing tags) |
| File size            | Smaller and more compact                  | Larger (more text due to tags)            |
| Speed to process     | Faster (simpler structure)                | Slower (more parsing needed)              |
| Data types           | Basic only (string, number, boolean, array, object, null) | Can define very strict types with schema  |
| Structure rules      | No built-in strict validation             | Schema provides strong rules and validation |
| Human editing        | Very friendly and quick                   | More typing and verbose                   |
| Main use today       | Web APIs, modern apps, configuration files | Older systems, SOAP services, documents needing strict structure |
| Namespace support    | No native support                         | Excellent support for namespaces          |
| Comments             | No official comments                      | Supports <!-- comments -->                |
| Attributes           | No attributes (everything is key-value)   | Supports attributes on elements           |


```XML
<planets>
	<planet>
		<name>Mars</name>
		<distanceFromSunKM>227900000</distanceFromSunKM>
		<gravityMS2>3.71</gravityMS2>
	</planet>
	<planet>
		<name>Earth</name>
		<distanceFromSunKM>149600000</distanceFromSunKM>
		<gravityMS2>9.798</gravityMS2>
	</planet>
</planets>
```