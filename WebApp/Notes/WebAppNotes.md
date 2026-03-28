# Web Applications - Comprehensive Lecture Notes

## Table of Contents
1. [Module 0: Module Introduction](#module-0-module-introduction)
2. [Module 1: HTML5](#module-1-html5)
3. [Module 2: CSS](#module-2-css)
4. [Module 3: Introduction to ASP.NET](#module-3-introduction-to-aspnet)
5. [Module 4: Introduction to ADO.NET](#module-4-introduction-to-adonet)
6. [Module 5: Website Design Method (WSDM)](#module-5-website-design-method-wsdm)
7. [Module 6: Web Accessibility](#module-6-web-accessibility)
8. [Module 7: Servers and Security](#module-7-servers-and-security)
9. [Module 8: Evaluation of Web Pages](#module-8-evaluation-of-web-pages)
10. [Module 9: Web HCI and Usability](#module-9-web-hci-and-usability)

---

## Module 0: Module Introduction

### Course Overview

| Aspect | Details |
|--------|---------|
| **Course Code** | CT050-3-2 |
| **Course Title** | Web Applications |
| **Module Credit Value** | 3 |
| **Total Learning Hours** | Guided: 56 hours (Tutorial: 28h, Lab: 28h) + Independent: 41 hours |

### Course Learning Outcomes (CLOs)

| CLO | Description | Bloom's Level | PLO |
|-----|-------------|---------------|-----|
| CLO1 | Explain important concepts and their application in designing and developing web applications | C5 (Evaluating) | PLO2 |
| CLO2 | Construct a web application connected to a well-designed database using server and client-side scripting based on current web standards | P4 (Analyzing) | PLO3 |

### Course Content

| Topic | Description |
|-------|-------------|
| Introduction to Web Development | Overview of web development concepts |
| Methods for Web Page Design | Design methodologies and approaches |
| Front-end Development | Client-side technologies and scripting |
| Back-end Development | Server-side programming |
| Web Database | Database integration and management |
| Web HCI and Usability | Human-Computer Interaction principles |
| Web Servers and Security | Server technologies and security measures |
| Web Accessibility | Making web pages accessible to all users |
| Evaluation of Web Pages | Criteria for evaluating web quality |

### Assessment Method

| Component | Weightage |
|-----------|-----------|
| Group Assignment | 100% |

### Expected Student Behavior

| Requirement | Details |
|-------------|---------|
| Attendance | Compulsory (medical certificates/parent letters required for absences) |
| Attire | Proper attire required |
| Language | No speaking of dialects |
| Punctuality | Three lateness = one absence |
| Mobile Devices | All phones must be turned off during lectures |

### Reference Materials

| Resource | Author | ISBN |
|----------|--------|------|
| Essential ASP.NET Web Forms Development | Robert E. Beasley (2021) | 978-1484257838 |
| HTML CSS and JavaScript | Hanumanth L. (2021) | 9798488815360 |
| Learn C# Programming | Marius Bancila et al. (2020) | 978-1789805864 |
| Programming C# 10 | Ian Griffiths (2020) | 978-1098117818 |

### Outcomes Based Education (OBE)

| Characteristic | Description |
|----------------|-------------|
| Focus | What students can actually do after being taught |
| Expectation | All learners successfully achieve particular level of knowledge and abilities |
| Philosophy | NOT "What we want to teach" but "What You should learn" |

---

## Module 1: HTML5

### Key Terms

| Term | Definition |
|------|------------|
| HTML | HyperText Markup Language - coded format for creating hypertext documents on WWW |
| HTML5 | Current version of HTML with new elements and features |

### HTML5 Structure

| Element | Description | Example |
|---------|-------------|---------|
| `<!DOCTYPE html>` | Document type declaration (simplified in HTML5) | `<!DOCTYPE html>` |
| `<html>` | Root element | `<html>...</html>` |
| `<head>` | Head section (metadata) | `<head>...</head>` |
| `<body>` | Body section (content) | `<body>...</body>` |

### HTML5 Features

| Feature | Description |
|---------|-------------|
| Canvas element | For drawing graphics |
| Video/audio elements | For media playback |
| Local offline storage | Better support for storing data locally |
| New semantic elements | `<article>`, `<footer>`, `<header>`, `<nav>`, `<section>` |
| New form controls | Calendar, date, time, email, URL, search |

### HTML5 Rules

| Rule | Description | Example |
|------|-------------|---------|
| Case insensitivity | `<b>` and `<B>` are the same | Both work identically |
| Nesting (not crossing) | Elements must be properly nested | `<b><i>text</i></b>` ✓, `<b><i>text</b></i>` ✗ |
| Attribute values | May be case sensitive | `src="test.gif"` ≠ `src="TEST.GIF"` |

### Headers

| Tag | Level | Usage |
|-----|-------|-------|
| `<h1>` | Level 1 | Main heading (most important) |
| `<h2>` | Level 2 | Section heading |
| `<h3>` | Level 3 | Subsection heading |
| `<h4>` | Level 4 | Minor heading |
| `<h5>` | Level 5 | Less important heading |
| `<h6>` | Level 6 | Least important heading |

### Linking

| Element | Attribute | Purpose | Example |
|---------|-----------|---------|---------|
| `<a>` | `href` | Link destination | `<a href="http://www.google.com">Google</a>` |
| `<a>` | `mailto:` | Email link | `<a href="mailto:name@email.com">Email me</a>` |
| `<strong>` | - | Bold text (emphasis) | `<strong>Important text</strong>` |
| `<br>` | - | Line break | `Text<br/>More text` |

### Images

| Attribute | Description | Example |
|-----------|-------------|---------|
| `src` | Image file location | `<img src="princess.jpg">` |
| `width` | Image width in pixels | `<img width="640">` |
| `height` | Image height in pixels | `<img height="360">` |
| `alt` | Alternative text description | `<img alt="Princess">` |

### Popular Image Formats

| Format | Full Name | Characteristics |
|--------|-----------|-----------------|
| GIF | Graphics Interchange Format | Supports animation, 256 colors |
| JPEG | Joint Photographic Experts Group | Compressed, good for photos |
| PNG | Portable Network Graphics | Lossless compression, supports transparency |

### Special Characters

| Character | Entity Code | Display |
|-----------|-------------|---------|
| Half | `&frac12;` | ½ |
| Quarter | `&frac14;` | ¼ |
| Copyright | `&copy;` | © |
| Less than | `&lt;` | < |
| Greater than | `&gt;` | > |
| Ampersand | `&amp;` | & |

### Text Formatting Tags

| Tag | Purpose | Example |
|-----|---------|---------|
| `<del>` | Strike-through text | `<del>deleted text</del>` |
| `<sup>` | Superscript | H₂O (with `<sup>`) |
| `<sub>` | Subscript | 3.14 x 10² |
| `<hr>` | Horizontal rule | `<hr/>` |

### Lists

| List Type | Tag | Description | Example |
|-----------|-----|-------------|---------|
| Unordered | `<ul>` | Bulleted list | `<ul><li>Item</li></ul>` |
| Ordered | `<ol>` | Numbered list | `<ol><li>Item</li></ol>` |
| List Item | `<li>` | Individual item in any list | `<li>Content</li>` |

### Nested Lists

| Concept | Description |
|---------|-------------|
| Hierarchy | Represents relationships between items |
| Implementation | List inside another list |
| Visual | Different bullet/number styles for different levels |

### Tables

| Element | Attribute | Purpose |
|---------|-----------|---------|
| `<table>` | `border` | Specifies border width in pixels |
| `<table>` | `summary` | Describes table contents |
| `<caption>` | - | Table title/description |
| `<thead>` | - | Header section |
| `<tbody>` | - | Body section |
| `<tfoot>` | - | Footer section |
| `<tr>` | - | Table row |
| `<th>` | - | Header cell |
| `<td>` | - | Data cell |

### Table Formatting

| Attribute | Element | Values | Description |
|-----------|---------|--------|-------------|
| `rowspan` | `<th>`, `<td>` | Number | Merges multiple rows |
| `colspan` | `<th>`, `<td>` | Number | Merges multiple columns |
| `valign` | `<th>`, `<td>` | top, middle, bottom, baseline | Vertical alignment |
| `align` | `<col>` | left, right, center | Horizontal alignment |
| `span` | `<col>` | Number | Number of columns to format |

### Forms

| Element | Attribute | Purpose | Example |
|---------|-----------|---------|---------|
| `<form>` | `action` | URL of processing script | `<form action="process.php">` |
| `<form>` | `method` | How data is sent | `method="post"` or `method="get"` |
| `<input>` | `type` | Input type | `type="text"`, `type="password"`, etc. |
| `<input>` | `name` | Field name | `name="username"` |
| `<input>` | `maxlength` | Maximum characters | `maxlength="30"` |
| `<input>` | `size` | Display width | `size="25"` |
| `<input>` | `value` | Default/submit value | `value="Submit"` |

### Input Types

| Type | Purpose | Example |
|------|---------|---------|
| `text` | Single-line text input | `<input type="text">` |
| `password` | Password field (masked) | `<input type="password">` |
| `submit` | Submit button | `<input type="submit">` |
| `reset` | Reset form button | `<input type="reset">` |
| `checkbox` | Checkbox option | `<input type="checkbox">` |

### Complex Form Elements

| Element | Attributes | Purpose |
|---------|------------|---------|
| `<textarea>` | `rows`, `cols` | Multiline text input |
| `<select>` | - | Dropdown list |
| `<option>` | - | Items in dropdown list |

---

## Module 2: CSS

### Key Terms

| Term | Definition |
|------|------------|
| CSS | Cascading Style Sheet - separates structure from presentation |
| Style Sheet | Document containing instructions for displaying HTML elements |

### CSS Types

| Type | Location | Scope | Example |
|------|----------|-------|---------|
| Inline | Within HTML element | Single element only | `<p style="color: blue;">` |
| Embedded/Internal | In `<head>` section | Entire document | `<style>...</style>` |
| External | Separate .css file | Multiple documents | `<link href="style.css">` |

### CSS Priority (Cascade Order)

| Priority | Type | Description |
|----------|------|-------------|
| 1 (Highest) | Inline Style | Affects single HTML element; overrides all others |
| 2 | Embedded Style Sheet | Affects one HTML document; overrides external |
| 3 | External Style Sheet | Affects multiple documents |
| 4 (Lowest) | Browser Default | Default browser styling |

### Inline Styles

| Syntax | Example | Limitations |
|--------|---------|-------------|
| `style="property: value;"` | `<p style="font-size: 20pt; color: #0000ff">` | Not separating content from presentation |

### Embedded Style Sheets

| Component | Description | Example |
|-----------|-------------|---------|
| `<style>` tag | Contains CSS rules | `<style type="text/css">...</style>` |
| MIME type | `text/css` | Specifies file content type |
| Selector | HTML element to style | `h1`, `p`, `.special` |
| Property | CSS attribute | `font-family`, `color` |
| Value | Property setting | `arial`, `blue` |

### Embedded Style Example

```css
em { background-color: #8000ff; color: white }
h1 { font-family: arial, sans-serif }
p { font-size: 14pt }
.special { color: blue }
```

### External Style Sheets

| Benefit | Description |
|---------|-------------|
| Uniform look | Consistent appearance across entire site |
| Easy maintenance | Update all pages by changing one file |
| Smaller files | Pages load faster (style info in one file) |
| Bandwidth savings | Cached by browser after first load |

### Linking External Style Sheets

| Attribute | Value | Purpose |
|-----------|-------|---------|
| `href` | stylesheet.css | Path to CSS file |
| `rel` | stylesheet | Relationship type |
| `type` | text/css | MIME type |

```html
<link href="stylesheet.css" rel="stylesheet" type="text/css" />
```

### HTML Selectors

| Selector | Description | Example |
|----------|-------------|---------|
| Element selector | Controls specific HTML tag behavior | `h1 { font-family: arial; }` |
| Tag name | Text part of HTML tag | `p`, `h1`, `body` |

### Class Selectors

| Syntax | Description | Example |
|--------|-------------|---------|
| `.classname` | User-defined selector for any tag | `.userDefineName { color: blue; }` |
| `class="classname"` | Apply to HTML element | `<p class="userDefineName">Text</p>` |

### Conflicting Styles Rules

| Situation | Result |
|-----------|--------|
| Different attributes | Browser displays all attributes from both styles |
| Conflicting attributes | Innermost style (closest to text) takes precedence |
| HTML vs CSS formatting | HTML formatting overrides CSS formatting |
| Different browsers | May implement CSS differently - test in multiple browsers |

---

## Module 3: Introduction to ASP.NET

### Key Terms

| Term | Definition |
|------|------------|
| ASP.NET | Microsoft's server-side technology that dynamically builds documents in response to client requests |
| Classic ASP | Microsoft's previous server-side scripting technology (now called ASP 3.0) |

### The Microsoft .NET Framework Components

| Component | Description | Examples |
|-----------|-------------|----------|
| **Programming Languages** | Languages that work with .NET | C#, Visual Basic .NET, J# |
| **Server/Client Technologies** | Technologies for building applications | ASP.NET, Windows Forms, Compact Framework |
| **Development Environments** | IDEs for development | Visual Studio .NET, Visual Web Developer |

### ASP.NET vs Classic ASP

| Aspect | Classic ASP | ASP.NET |
|--------|-------------|---------|
| Compatibility | Last version: ASP 3.0 | Entirely new technology |
| Framework | Not part of framework | Major part of .NET Framework |
| Backward Compatibility | - | Not backward compatible with classic ASP |
| Development | Code-oriented | Application framework |

### Static vs Dynamic Web Pages

| Characteristic | Static Pages | Dynamic Pages |
|----------------|--------------|---------------|
| Content | Same every time | Changes each time retrieved |
| Creation | HTML only | Program generates HTML |
| Flexibility | Limited | High (can generate different content) |

### Browser and Web Server

| Component | Description | Examples |
|-----------|-------------|---------|
| **Client** | Web browser on user's computer | Internet Explorer, Firefox, Chrome |
| **Server** | Software hosting web application | IIS (Internet Information Services) |
| **Requirements** | .NET Framework must be installed on server | Required for ASP.NET applications |

### ASP.NET File Characteristics

| Characteristic | Description |
|----------------|-------------|
| Format | Same as HTML file |
| Content | Can contain HTML, XML, and scripts |
| Script Execution | Scripts executed on server |
| File Extension | `.aspx` |
| Output | Returned as plain HTML to browser |

### How ASP.NET Works

| Step | Process |
|------|---------|
| 1 | Browser requests ASP.NET file |
| 2 | IIS passes request to ASP.NET engine |
| 3 | ASP.NET engine reads file line by line |
| 4 | Scripts in file are executed |
| 5 | File returned to browser as plain HTML |

### Language Support

| Language | Description | Characteristics |
|----------|-------------|-----------------|
| **C#** | Pronounced "C-Sharp" | Similar to Java syntax, designed for .NET |
| **Visual Basic .NET** | Modern version of Basic | Powerful language, originally for beginners |
| **J#** | Microsoft's version of Java | Not widely used for ASP.NET development |

### Object-Oriented Programming

| Feature | Benefit |
|---------|---------|
| Object Orientation | Similar to C++ or Java |
| Library Access | Access to .NET Framework class library |
| Predefined Classes | Vast library of reusable components |

### Windows and IIS Dependence

| Requirement | Details |
|-------------|---------|
| Operating System | Must be recent version of Windows |
| Server Software | Must use IIS (Internet Information Services) |
| Platform Limitation | Only works on Microsoft Windows-based servers |

### Scripting Delimiters

| Delimiter | Purpose | Example |
|-----------|---------|---------|
| `<% %>` | Wraps C# or VB.NET code | `<% Response.Write("Hello"); %>` |
| `@ Page` | Page directive for CLR | `<%@ Page Language="C#" %>` |
| `runat="server"` | Indicates server-side processing | `<form id="form1" runat="server">` |

### Simple ASP.NET Example

```asp
<%@ Page Language="C#" %>
<!DOCTYPE html>
<html>
<head runat="server">
    <title>A Simple ASP.NET Example</title>
</head>
<body>
    <strong>A Simple ASP.NET Example</strong><br />
    <%
        Response.Write("ASP.NET programming is fun!!!");
        Response.Write("<br />");
        Response.Write("This page was loaded at: " + DateTime.Now.ToString());
    %>
</body>
</html>
```

### Visual Studio

| Feature | Description |
|---------|-------------|
| Integrated Development Environment (IDE) | Combines editor, debugger, and tools |
| Components | Web-page editor, code editor, debugger |
| Benefits | Simplifies ASP.NET Web application creation |

### Web Forms

| Component | Description |
|-----------|-------------|
| `<form>` tag | Designates ASP.NET Web Form |
| Web Controls | Form-like controls (text boxes, drop-down lists) |
| Validation Controls | Validate user input |

### ASP.NET Controls

| Control Type | Examples | Syntax |
|--------------|----------|--------|
| Text/Graphics | Label, Button, TextBox, Image | `<asp:Label ID="Label1" runat="server">` |
| List Controls | RadioButtonList, DropDownList | `<asp:DropDownList runat="server">` |

### Validation Controls

| Control | Purpose |
|---------|---------|
| Required Field Validator | Ensures field is not empty |
| Range Validator | Checks value within specified range |
| Other validators | Various validation types |

### Event-Aware Controls

| Event | Description |
|-------|-------------|
| Load | Page load event |
| Click | Button click event |
| Change | Value change event |

```csharp
<asp:Button ID="Button1" runat="server" Text="Button" OnClick="Button1_Click" />
protected void Button1_Click(object sender, EventArgs e)
{
    // Code to handle click event
}
```

### Code-Behind Approach

| File Type | Extension | Purpose |
|-----------|-----------|---------|
| Markup File | `.aspx` | Defines appearance of Web page |
| Code-Behind File | `.aspx.cs` (C#) or `.aspx.vb` (VB) | Contains code and event handlers |

### Visual Studio Project Structure

| Container | Purpose |
|-----------|---------|
| **Project** | Holds all files for single ASP.NET application |
| **Solution** | Container for one or more related projects |

### Creating ASP.NET Applications

| Step | Action |
|------|--------|
| 1 | File → New → Web Site |
| 2 | Choose ASP.NET Web Site template |
| 3 | Enter location for web site |
| 4 | Click OK |
| 5 | Right Click Website → Add New Item |
| 6 | Select Web Form, enter name, click Add |
| 7 | Drag and drop controls from toolbox |
| 8 | Add code for control events |
| 9 | Press F5 or click Start Debugging |

### Simple Calculator Application

| Component | Purpose |
|-----------|---------|
| TextBox1 | Input for first number |
| TextBox2 | Input for second number |
| Button1 | Submit button to calculate |
| Label4 | Display result |

```csharp
protected void Button1_Click(object sender, EventArgs e)
{
    double result = 0.0;
    result = Convert.ToDouble(this.TextBox1.Text)
            + Convert.ToDouble(this.TextBox2.Text);
    this.Label4.Text = "The result is: " + result.ToString();
}
```

---

## Module 4: Introduction to ADO.NET

### Key Terms

| Term | Definition |
|------|------------|
| SQL | Structured Query Language - standard for querying databases |
| ADO.NET | Microsoft's .NET framework technology for database access |

### Relational Database Model

| Concept | Description |
|---------|-------------|
| Database | Organized collection of data |
| DBMS | Database Management System - stores, organizes, retrieves, modifies data |
| RDBMS | Relational DBMS - most popular type today |
| Table | Stores data in rows and columns |
| Row | Represents a record |
| Column | Represents an attribute/field |
| Primary Key | Unique value identifying each row |

### Popular DBMS

| DBMS | Type |
|------|------|
| Microsoft SQL Server | Commercial |
| Microsoft Access | Desktop |
| MySQL | Open Source |
| PostgreSQL | Open Source |
| Oracle | Commercial |
| Sybase | Commercial |
| FrontBase | Commercial |

### SQL Statements

| Statement | Purpose | Syntax |
|-----------|---------|-------|
| SELECT | Retrieve data | `SELECT columns FROM table WHERE condition` |
| INSERT | Add new row | `INSERT INTO table (cols) VALUES (values)` |
| UPDATE | Modify data | `UPDATE table SET col=val WHERE condition` |
| DELETE | Remove rows | `DELETE FROM table WHERE condition` |

### SELECT Statement

| Component | Description | Example |
|-----------|-------------|---------|
| Basic form | `SELECT * FROM TableName` | `SELECT * FROM Members` |
| Specific columns | `SELECT col1, col2 FROM table` | `SELECT FirstName, LastName FROM Members` |
| WHERE clause | Filter results | `WHERE LastName LIKE 'D%'` |
| ORDER BY | Sort results | `ORDER BY LastName DESC` |

### WHERE Clause Operators

| Operator | Purpose | Example |
|----------|---------|---------|
| `<` | Less than | `WHERE Age < 25` |
| `>` | Greater than | `WHERE Salary > 50000` |
| `<=` | Less than or equal | `WHERE Price <= 100` |
| `>=` | Greater than or equal | `WHERE Score >= 60` |
| `=` | Equal | `WHERE Status = 'Active'` |
| `<>` | Not equal | `WHERE ID <> 0` |
| `LIKE` | Pattern matching | `WHERE Name LIKE 'A%'` |

### LIKE Pattern Matching

| Wildcard | Meaning | Example |
|----------|---------|---------|
| `%` | Any sequence of characters | `WHERE LastName LIKE 'D%'` (starts with D) |
| `_` | Any single character | `WHERE LastName LIKE '_I%'` (second letter is I) |

### ORDER BY Clause

| Option | Description | Example |
|--------|-------------|---------|
| ASC | Ascending order (default) | `ORDER BY Name ASC` |
| DESC | Descending order | `ORDER BY Name DESC` |
| Multiple columns | Sort by multiple criteria | `ORDER BY LastName, FirstName` |

### INNER JOIN

| Purpose | Description |
|---------|-------------|
| Merging tables | Join rows from two tables with matching values |
| Basic syntax | `SELECT cols FROM table1 INNER JOIN table2 ON table1.col = table2.col` |

### INSERT Statement

| Component | Description |
|-----------|-------------|
| Basic form | `INSERT INTO TableName (cols) VALUES (values)` |
| Strings | Use single quotes `'` |
| Escaping quotes | Use two single quotes `''` for one quote |

### UPDATE Statement

| Component | Description |
|-----------|-------------|
| Basic form | `UPDATE TableName SET col=val WHERE condition` |
| Warning | Without WHERE, updates ALL rows |

### DELETE Statement

| Component | Description |
|-----------|-------------|
| Basic form | `DELETE FROM TableName WHERE condition` |
| Warning | Without WHERE, deletes ALL rows |

### ADO.NET Object Model

| Namespace | Purpose | Key Classes |
|-----------|---------|-------------|
| `System.Data` | Root namespace for ADO.NET API | - |
| `System.Data.SqlClient` | SQL Server database access | SqlConnection, SqlCommand, SqlDataReader |
| `System.Data.OleDb` | Access/OleDB database access | OleDbConnection, OleDbCommand, OleDbDataReader |

### ADO.NET Core Objects

| Object Type | Purpose | Example |
|-------------|---------|---------|
| **Connection** | Represents connection to database | `SqlConnection`, `OleDbConnection` |
| **Command** | Represents SQL command to execute | `SqlCommand`, `OleDbCommand` |
| **DataReader** | Reads data from database | `SqlDataReader`, `OleDbDataReader` |
| **DataAdapter** | Retrieves info and places in DataSet | `SqlDataAdapter`, `OleDbDataAdapter` |
| **DataSet** | Set of data with tables | - |

### Connecting to Database

| Step | Description |
|------|-------------|
| 1 | Create Connection object (`SqlConnection` or `OleDbConnection`) |
| 2 | Create Command object with SQL query and connection |
| 3 | Execute command using `ExecuteReader()` |
| 4 | Read data using DataReader |
| 5 | Or use DataAdapter to fill DataSet |

### App_Data Folder

| Purpose | Description |
|---------|-------------|
| Location | Store database files in this folder |
| Benefit | Secure location for application data |

### Data Binding

| Concept | Description |
|---------|-------------|
| Definition | Technique tying GUI controls to data sources |
| AccessDataSource | For Access databases |
| SqlDataSource | For SQL Server databases |
| ConnectionString | Indicates database connection |

### Data Source Controls

| Control | Purpose |
|---------|---------|
| **ObjectDataSource** | Work with business objects/middle-tier objects |
| **SqlDataSource** | Work with SQL Server, OLE DB, ODBC, Oracle databases |
| **AccessDataSource** | Work with Microsoft Access database |
| **XmlDataSource** | Work with XML files (good for TreeView, Menu) |
| **SiteMapDataSource** | Used with ASP.NET site navigation |

### GridView Control

| Feature | Description |
|---------|-------------|
| Purpose | Display data in tabular format |
| Formatting | Set colors using Auto Format |
| Capabilities | Querying, sorting, paging, filtering, updating, deleting, inserting |

---

## Module 5: Website Design Method (WSDM)

### Key Terms

| Term | Definition |
|------|------------|
| WSDM | Web Site Design Method - pronounced "wisdom" |
| Audience-driven | Design method focused on user needs |

### Web Development Challenges

| Area | Challenges |
|------|------------|
| Web Engineering | Managing complexity of web-based systems |
| Hypertext | Non-linear navigation and linking |
| Information Engineering | Organizing large amounts of information |
| Requirements Engineering | Gathering and managing user requirements |
| System Analysis and Design | Creating system architecture |
| Multimedia | Integrating various media types |
| Human-Computer Interaction | Creating usable interfaces |
| Testing | Ensuring quality across platforms |
| Project Management | Coordinating development teams |
| Software Engineering | Applying engineering principles |
| Public Relations | Marketing and communication |

### WSDM Overview

| Aspect | Details |
|--------|---------|
| Origin | Developed at Vrije Universiteit Brussel (1998) |
| Developer | Prof. Dr. Olga De Troyer |
| Research Group | Web & Information System Engineering (WISE) |
| Evolution | From kiosk websites to semantic web design method |
| Features | Functionality, localization, accessibility, semantic annotation, adaptivity |

### WSDM Phases

| Phase | Purpose |
|-------|---------|
| 1. Mission Statement Specification | Define purpose, subject, target audience |
| 2. Audience Modeling | Identify and characterize user groups |
| 3. Conceptual Design | Model tasks, information, and navigation |
| 4. Implementation Design | Site structure, presentation, data design |
| 5. Implementation | Generate actual implementation |

### Phase 1: Mission Statement Specification

| Question to Answer | Purpose |
|--------------------|---------|
| What is the purpose? | Define site goals |
| What is the subject? | Specify content scope |
| Who are target audience(s)? | Identify users |

| Element | Description |
|---------|-------------|
| Purpose | What the site achieves |
| Subject | Content focus |
| Target Users | Who will use the site |
| Borders | Scope of design process |
| Validation | Check if goals are achieved |
| Format | Natural language description |

### Example Mission Statement (University Department)

| Aspect | Content |
|--------|---------|
| **Purpose 1** | Enhance communication between students and lecturers by providing detailed course information |
| **Purpose 2** | Provide program information to potential students to attract more students |
| **Target Audiences** | Students, lecturers, potential students |
| **Subject** | Courses and programs |

### Phase 2: Audience Modeling

| Sub-Phase | Purpose |
|-----------|---------|
| Audience Classification | Group users with similar requirements |
| Audience Characterization | Specify characteristics for each group |

### Audience Classification

| Concept | Description |
|---------|-------------|
| Audience Classes | Groups of users with same requirements |
| Audience Subclass | When one class's requirements are subset of another |
| Audience Hierarchy | Classification based on subclass relationships |
| Navigation/Usability Requirements | Specified for each class |

### Audience Classification Process

| Step | Action |
|------|--------|
| 1 | Look at organization activities |
| 2 | Decompose activities related to site purpose/subject |
| 3 | Identify people involved in activities (potential users) |
| 4 | Group users with similar requirements into audience classes |
| 5 | Decompose activities into sub-activities if needed |
| 6 | Refine audience classes based on decomposition |

### Example Activity Diagram

| Activity | Sub-Activities | Involved People |
|----------|----------------|-----------------|
| Provide Education | Provide Graduate Education, Provide Master Education | Lecturers, enrolled students, potential students, staff members |

### Audience Characterization

| Concept | Description |
|---------|-------------|
| Characteristics | User attributes affecting presentation/usability |
| Audience Class Variants | Subgroups within a class with different characteristics |
| Different Representation | Same information shown differently to different users |

### Example Audience Variants (Enrolled Students)

| Variant | Characteristics | Requirements |
|---------|-----------------|--------------|
| Local Students | Age 18-28, familiar with jargon/rules, prefer local language | Same information needs, different usability |
| Exchange Students | All communication in English, not familiar with jargon/customs | Same information needs, different usability |

### Phase 3: Conceptual Design

| Sub-Phase | Purpose |
|-----------|---------|
| Task & Information Modeling | Model tasks and formalize data/functionality |
| Navigational Design | Define conceptual structure and navigation |

### Task & Information Modeling

| Concept | Description |
|---------|-------------|
| Purpose | Model tasks users need to perform |
| Task Definition | Based on requirements from audience classification |
| CTT | Concurrent Task Trees for task decomposition |
| Elementary Tasks | Basic tasks that cannot be decomposed further |
| Temporal Relationships | Order of task execution (sequential, parallel, etc.) |
| Object Chunks | Formal description of information/functionality needed |
| OWL | Web Ontology Language for modeling |

### Object Chunk

| Component | Description |
|-----------|-------------|
| Purpose | Describe information/functionality for elementary task |
| Technology | Originally ORM, now OWL for semantic web |
| Benefit | Enables semantic website generation |

### Navigational Design

| Concept | Description |
|---------|-------------|
| Purpose | Define conceptual structure and navigation |
| Audience Track | Sub-site for each audience class |
| Components | Conceptual navigation entities (nodes) |
| Links | Connections between components |

### Navigation Structures

| Structure Type | Description |
|----------------|-------------|
| Hierarchical | Tree-like organization |
| Grid | Matrix organization |
| Linear | Sequential organization |
| Network | Interconnected nodes |

### Phase 4: Implementation Design

| Sub-Phase | Purpose |
|-----------|---------|
| Site Structure Design | Group components into pages |
| Presentation Design | Define look, feel, and layout |
| Logical Data Design | Create data schema |

### Site Structure Design

| Decision Factor | Description |
|-----------------|-------------|
| Page Grouping | How to organize components into pages |
| Audience Characteristics | Consider different user needs |
| Default | One component per page |
| Options | Multiple components per page, split components across pages |
| Multiple Structures | Support different devices/contexts/platforms |

### Presentation Design

| Component | Description |
|-----------|-------------|
| Look and Feel | Visual appearance and style |
| Layout | Positioning of page elements |
| Templates | Reusable page designs for consistency |
| Page Types | Homepage, title page, leaf page, etc. |
| Grid | Positioning mechanism (rows with cells) |
| High-level Concepts | Menu, table, bulleted-list |
| Style | Cascading Style Sheets (CSS) |
| Labels | Text for navigation elements |

### Logical Data Design

| Scenario | Action |
|----------|--------|
| No existing data storage | Create logical data schema from conceptual schema |
| Existing data store | Define mapping between reference ontology and data store |

| Schema Type | Examples |
|-------------|---------|
| Relational | Database schema |
| XML | XML schema |
| RDF | RDF schema |
| OWL | OWL schema |

| Concept | Description |
|---------|-------------|
| Reference Ontology | Conceptual schema for site data |
| Mapping | Connection between ontology and logical schema |
| CASE-tool | Automated tool for schema creation and mapping |

### Phase 5: Implementation

| Concept | Description |
|---------|-------------|
| Generation | Automatic from design models |
| Models Used | Navigational, site structure, page, logical data models |
| Outcome | Working web application |

---

## Module 6: Web Accessibility

### Key Terms

| Term | Definition |
|------|------------|
| Accessibility | Level of usability for people with disabilities |
| WAI | Web Accessibility Initiative - W3C's accessibility improvement effort |

### Accessibility Importance

| Reason | Description |
|--------|-------------|
| User Base | More people with disabilities using Internet |
| Regulations | Federal requirements for accommodation |
| Disabilities | Hearing, vision, speech, mobility impairments |
| Challenges | Language barriers, hardware/software inconsistencies |
| Difficulty | High level of accessibility hard to achieve |

### Web Accessibility Initiative (WAI)

| Aspect | Details |
|--------|---------|
| Organization | World Wide Web Consortium (W3C) |
| Purpose | Improve website accessibility |
| Website | www.w3.org/WAI |
| Current Status | Most websites considered inaccessible |

### User Agents

| Type | Purpose | Examples |
|------|---------|---------|
| Screen Readers | Read web pages aloud | JAWS, NVDA |
| Braille Displays | Convert pages to braille | Refreshable braille devices |
| Text Browsers | Display text only | Lynx |

### Alt Attribute

| Element | Purpose | Benefit |
|---------|---------|---------|
| `<img>` | Describe image content | Accessibility for visually impaired |
| `<input>` | Describe input purpose | Accessibility |
| User Agents | Interpret page without images | Better understanding |
| Search Engines | Image description | SEO benefit |
| Mobile Devices | Slow connections | Option to skip images |

### Maximizing Readability

| Factor | Guideline |
|--------|-----------|
| Reading Level | Match audience level |
| Language | Avoid slang and non-traditional language |
| Structure | Use semantic tags appropriately |
| Headings | Use `<h1>`-`<h6>` correctly (not for formatting) |

### Tag Usage

| Tag | Correct Use | Incorrect Use |
|-----|-------------|---------------|
| `<h1>` | Major section head | Making text large and bold |
| Semantic | According to XHTML specs | For aesthetic purposes |

### Accessibility in Tables

| Problem | Solution |
|---------|----------|
| Screen reader difficulty | Use proper table structure |
| Linear reading | Screen readers read left-to-right, top-to-bottom |
| Layout tables | Use CSS instead of tables for layout |

### HTML Table Accessibility Features

| Attribute | Element | Purpose |
|-----------|---------|---------|
| `headers` | `<td>` | Reference to header cell(s) |
| `id` | `<th>` | Unique identifier for header |
| `summary` | `<table>` | Description of table contents |
| `caption` | `<caption>` | Table title/description |

### Accessible Table Example

| Feature | Description |
|---------|-------------|
| Caption | "Price of Fruit" |
| Summary | Explains use of TH, ID, and HEADERS attributes |
| Headers | Fruit column has ID |
| Cells | Use HEADERS attribute to reference headers |
| Screen Reader Output | "Fruit: Apple, Price: $0.25" |

### Accessibility Checklist

| Category | Questions |
|----------|-----------|
| **General** | Does site load quickly? Can you move around easily? Is site still there next time? |
| **Text Alternatives** | Is there text-only alternative? Are ALT tags used with images? |
| **Structure** | Are pages in logical sequence? Are directories organized by use? |
| **Navigation** | Do pages have consistent look/feel? Is information 1-2 clicks away? Would site map help? |
| **Visual** | Do images enhance content? Is there enough white space? Is identifying information at top left? |
| **Technology** | Is left side navigation provided? Can content be found on right side? Are new technologies used appropriately? |

---

## Module 7: Servers and Security

### Key Terms

| Term | Definition |
|------|------------|
| Authentication | Process verifying user identity |
| Authorization | Process granting user access to permitted resources |
| ASP.NET | Microsoft web development platform |
| J2EE | Java 2 Enterprise Edition - component model for web apps |

### Server Technology

| Technology | Type | Description |
|------------|------|-------------|
| .NET Framework | Product | Microsoft's platform for building applications |
| J2EE | Standard | Component model for enterprise applications |
| ASP.NET | .NET component | Web application development |
| EJB | J2EE component | Enterprise Java Beans |

### Microsoft .NET Framework

| Component | Description |
|-----------|-------------|
| Runtime | Layer of functionality and classes |
| ASP.NET | Web application area of framework |
| Platform | Runs on IIS (Internet Information Server) |
| Scalability | Multi-user applications with middle-tier servers |
| Database | Separate database servers common |

### J2EE

| Aspect | Details |
|--------|---------|
| Type | Not a product, but a set of containers and agreements |
| Language | Implemented in Java |
| Design | Component model for application servers |
| Platform | Runs on multiple platforms |

### ASP.NET vs J2EE Comparison

| Feature | J2EE | .NET |
|---------|------|------|
| **Type of Technology** | Standard | Product |
| **Middleware Vendors** | 30+ | Microsoft |
| **Interpreter** | JRE | CLR |
| **Dynamic Web Pages** | JSP | ASP.NET |
| **Middle-Tier Components** | EJB | Managed Components |
| **Database Access** | JDBC | ADO.NET |
| **SOAP, WSDL, UDDI** | Yes | Yes |
| **Implicit Middleware** | Yes | Yes |

### ASP.NET Advantages

| Advantage | Description |
|-----------|-------------|
| Language Independence | Support for C#, VB.NET, J# |
| Single Platform | Easier support and development |
| Performance | Slight performance advantage over J2EE |
| Integration | Tightly integrated with Windows OS |

### J2EE Advantages

| Advantage | Description |
|-----------|-------------|
| Platform Independence | Runs on multiple platforms |
| Industry Backing | Supported by Oracle, IBM, Nokia |
| Proven Track Record | Scalable and reliable over years |
| Language Standardization | Java only - consistent expertise |

### Platform Independence

| Technology | Platform | Considerations |
|------------|----------|----------------|
| J2EE | Multiple | Greater choice of hardware/software, more complicated support |
| .NET | Microsoft Windows | Limited choices, easier support, OS-specific optimizations |

### Language Independence

| Technology | Languages | Flexibility |
|------------|-----------|------------|
| .NET | C#, VB.NET, J# | Choose based on skills, broader skill targeting |
| J2EE | Java only | Standardized code, shared expertise |

### Web Servers

| Definition | Description |
|------------|-------------|
| **Software** | Application managing web pages |
| **Hardware** | Machine running web server software |
| **Purpose** | Make resources available over network |

### Web Server Types

| Type | Environment | Example |
|------|-------------|---------|
| Local | Server and browser on same machine | Development |
| Shared Internal | Internal network access | Corporate intranet |
| Public Internet | Separate machines for server and browser | Public websites |

### Popular Web Servers

| Server | Platform | ASP.NET Support |
|--------|----------|-----------------|
| IIS | Windows | Yes (required) |
| Apache | Cross-platform | Limited |
| Tomcat | Cross-platform | Java-based |

### Internet Information Services (IIS)

| Feature | Description |
|---------|-------------|
| Availability | Windows 2000+, Windows Server |
| Requirement | .NET Framework for ASP.NET applications |
| Function | Stores ASPX files, compiles when needed, serves to browsers |
| Production | Heavy-duty web server for production use |

### Visual Studio Development Server

| Feature | Description |
|---------|-------------|
| Type | Personal web server |
| Scope | Serves pages on localhost only |
| Use | Development only, not production |
| Technology | Run and forget |

### Requesting Documents (Static)

| Step | Process |
|------|---------|
| 1 | HTML files created and stored |
| 2 | User requests page |
| 3 | Server locates page and creates HTML stream |
| 4 | Server sends to client |
| 5 | Browser renders the HTML |

### Requesting Documents (Dynamic)

| Step | Process |
|------|---------|
| 1-5 | Same as static |
| 6 | ASP.NET compilation check and execution |
| 7 | Code executed on server |
| 8 | HTML stream returned to browser |

### Web Application Security

| Level | Measures |
|-------|----------|
| **Hardware** | Physical location, access control |
| **Network** | Firewalls, proxy servers, DNS |
| **Application** | Authentication, authorization |

### Security Model - User Levels

| Level | Description | Permissions |
|-------|-------------|-------------|
| Anonymous Users | No identification required | Browse products, view information |
| Registered Users | Identified and verified | Create accounts, make purchases |
| Administrators | Full system access | Manage data, user accounts, global settings |

### Anonymous Users

| Characteristic | Details |
|---------------|---------|
| Identification | No information required |
| Access | Limited to public resources |
| Business Model | Browse products, create cart, register to purchase |
| Benefits | Attract potential customers, protect sensitive info |

### Registered Users

| Characteristic | Details |
|---------------|---------|
| Identification | Personal information provided |
| Trust Level | Developed trust but not complete |
| Registration | Varies by application (credit card, personal details) |
| Access | Enhanced features and functionality |

### Administrators

| Characteristic | Details |
|---------------|---------|
| Authority | Freedom to act within system boundaries |
| Capabilities | Add/Edit/Update data, manage user accounts |
| Scope | May be limited by job requirements |
| Example | Banking admin cannot adjust account balances |

### Authentication

| Definition | Details |
|------------|---------|
| Purpose | Verify user is who they claim to be |
| Methods | Username/password, secret questions |
| Validation | Check against valid authority (database) |
| Process | User submits credentials, system validates |

### Authorization

| Definition | Details |
|------------|---------|
| Purpose | Grant access to permitted resources |
| Distinction | NOT the same as authentication |
| Timing | After authentication is successful |
| Scope | Based on user role/permissions |

### ASP.NET Authentication Types

| Type | Description | Browser Support | Use Case |
|------|-------------|-----------------|----------|
| **Forms Authentication** | Custom ASPX form | All browsers | Flexible, customizable interface |
| **Integrated Windows Authentication** | Windows integration | IE 5.0+ only | Windows environment only |
| **Passport Authentication** | Centralized Microsoft service | All browsers | Multiple sites, one set of credentials |

### Forms Authentication

| Feature | Description |
|---------|-------------|
| Implementation | ASPX form included in website |
| Browser Support | Cross-browser compatible |
| Flexibility | Custom authentication logic |
| Interface | Customizable design |
| Developer Control | High level of control over process |

### Why Use Forms Authentication

| Reason | Details |
|--------|---------|
| Network Independence | No need for Windows network/server |
| Simplicity | Easier to implement with standard web technology |
| Control | Greater control over user interface |
| Flexibility | Works across all browsers |

---

## Module 8: Evaluation of Web Pages

### Key Terms

| Term | Definition |
|------|------------|
| Evaluation Criteria | Standards for assessing web page quality |
| Evaluation Procedure | Process for systematically evaluating web pages |

### Web Page Evaluation Criteria

| Category | Key Questions |
|----------|---------------|
| **Audience** | Is content appropriate for audience? Is reading level appropriate? Is age/developmental level appropriate? |
| **Appropriateness & Relevance** | Is content accurate, complete, well-written? Is content relevant to topic? Does page download quickly? Does it look good when printed? Do page names make sense? |
| **Accuracy** | Is information up-to-date? Can you tell last update date? Are there dead links? Is there difference between creation and update dates? |
| **Clarity** | Is information clearly presented? Is text neat, legible, formatted for easy reading? Do graphics add or distract? Do advertisements interfere? Are pages well organized? Are there spelling/word usage mistakes? |
| **Accessibility** | Does site load quickly? Can you move around easily? Is site still there next time? Is there text-only alternative? Are ALT tags used with images? |
| **Information Flow** | Are pages in logical sequence? Are directories organized by primary use? |
| **Navigation** | Do pages have consistent look/feel? Is information 1-2 clicks away? Would site map be useful? |
| **Text/Graphics/Background/Color** | Would text graphics (logotype) be useful? Would background add or take away? Will images display well across platforms/browsers? |
| **Page Layout** | Do images give visual cues? Is there enough white space? Is content clear and enhanced by graphics? Are there too many canned graphics? Is identifying information at top left? Is left side navigation provided? Can content be found on right side? Does page overuse new technology? Would tables/images/frames help layout? |

### Web Page Evaluation Procedure

| Step | Action | Details |
|------|--------|---------|
| 1 | Identify Page Type | Determine: Advocacy, business/marketing, informational, news, personal, entertainment |
| 2 | Use Checklist | Answer questions with "Yes" or "No" |
| 3 | Determine Quality | Based on checklist criteria, more "Yes" answers = higher quality |

### Page Types

| Type | Description |
|------|-------------|
| Advocacy | Promotes a cause or opinion |
| Business/Marketing | Sells products or services |
| Informational | Provides factual information |
| News | Reports current events |
| Personal | Individual's personal site |
| Entertainment | Provides entertainment content |

### Evaluation Checklist Summary

| Area | Evaluation Points |
|------|-------------------|
| Content Quality | Accuracy, relevance, completeness, currency |
| User Experience | Navigation, speed, consistency, usability |
| Visual Design | Layout, graphics, color, typography |
| Accessibility | ALT tags, text alternatives, compatibility |
| Technical | No dead links, proper functioning |
| Organization | Logical structure, clear hierarchy |

---

## Module 9: Web HCI and Usability

### Key Terms

| Term | Definition |
|------|------------|
| HCI | Human-Computer Interaction - relationship between computers and users |
| User-Centered Design | Design philosophy focusing on user needs |
| Usability | Ease of learning and using a system |

### Human-Computer Interaction (HCI)

| Concept | Description |
|---------|-------------|
| Scope | Relationship between computers and people |
| Range | PCs to global networks |
| Goal | Create user-friendly, easy-to-learn, easy-to-use designs |
| Developer Objective | Maximize usability and user satisfaction |

### User-Centered Design Principles

| Principle | Action |
|-----------|--------|
| Understand Business Functions | Know underlying business requirements |
| Maximize Graphical Effectiveness | Use graphics effectively |
| Profile Users | Understand system users |
| Think Like User | Adopt user perspective |
| Use Prototyping | Create and test prototypes |
| Design Comprehensive Interface | Plan entire interface |
| Continue Feedback | Ongoing user feedback process |
| Document Design | Document interface design decisions |

### User Interface Design Guidelines

| Category | Guidelines |
|----------|------------|
| **Ease of Learning** | Label controls clearly, select understandable images, provide logical instructions, show all links in menu, make navigation easy |
| **Efficiency** | Organize pages/functions in groups, create hierarchical menus, provide shortcuts, use default values, use natural language |
| **Help & Error Handling** | Ensure help/FAQ always available, provide direct route from help, include contact info, require confirmation before deletion, use hypertext links |
| **Data Input** | Minimize input problems, provide validation checks, display event-driven messages, establish predefined values, build data integrity rules, use input masks/templates |
| **Feedback** | Provide feedback, display messages logically, alert to delays, keep messages long enough to read, indicate success/failure, use specific/professional messages |
| **Layout & Design** | Create attractive design, use appropriate colors, use special effects sparingly, use hyperlinks, group related objects, keep displays uncluttered, display titles/messages consistently, use consistent terminology, ensure commands have same effect, confirm data entry |
| **Familiarity** | Use familiar terms/images, stick to patterns, use familiar operations, provide similar look/feel, avoid complex terms/jargon |

### User Interface Controls

| Control Type | Examples | Purpose |
|--------------|----------|---------|
| **Menu Bars** | - | Command access |
| **Toolbars** | - | Quick command access |
| **Dialog Boxes** | - | Modal interactions |
| **Text Boxes** | - | Text input |
| **Toggle Buttons** | - | On/off states |
| **List Boxes** | - | Selection from list |
| **Scroll Bars** | - | Navigate content |
| **Drop-down Lists** | - | Compact selection |
| **Option Buttons** | Radio buttons | Single selection |
| **Check Boxes** | - | Multiple selections |
| **Command Buttons** | - | Trigger actions |
| **Progress Bars** | - | Show progress |
| **Calendars** | - | Date selection |

### Input Design

| Objective | Description |
|-----------|-------------|
| 1. Select suitable method | Choose appropriate input technique |
| 2. Reduce input volume | Only input necessary data |
| 3. Design attractive screens | Create appealing data entry screens |
| 4. Use validation checks | Reduce input errors |
| 5. Design source documents | Create effective paper forms |
| 6. Develop effective controls | Implement input controls |

### Input Volume Guidelines

| Guideline | Details |
|-----------|---------|
| Input necessary data only | Avoid unnecessary data entry |
| Don't input retrievable data | Use system files instead |
| Don't input calculated data | Compute from other data |
| Don't input constant data | Store once, reuse |
| Use codes | Use codes instead of full values (M/F, Y/N) |

### Effective Screen Design Guidelines

| Guideline | Details |
|-----------|---------|
| Form filling | Most effective online data entry method |
| Restrict access | Limit access to data entry locations |
| Provide captions | Descriptive labels for every field |
| Show sample format | Display example format when needed |
| Display default values | Use for constant entries |
| Show acceptable values | List valid options for fields |
| Allow exit without saving | Cancel/Reset functionality |
| Confirm accuracy | Opportunity to verify input |
| Standard field order | Use TabIndex for tab order |
| Match source document | Layout matches paper form |
| Add/Change/Delete/View | Full CRUD operations |
| Search capability | Allow searching for information |

### Input Error Validation

| Check Type | Purpose |
|------------|---------|
| Existence Checks | Ensure required fields are filled |
| Data Type Checks | Verify correct data type entered |
| Range Checks | Ensure values within acceptable range |
| Validity Checks | Verify data against business rules |

### Form Layout Guidelines

| Guideline | Details |
|-----------|---------|
| Sufficient Space | Allow enough space between elements |
| Clear Instructions | Provide explicit guidance |
| Logical Organization | Arrange fields logically |
| Effective Captions | Use titles effectively |

### Output Design Issues

| Output Type | Description |
|-------------|-------------|
| E-mail | Electronic mail delivery |
| Printer | Printed reports and documents |
| Screen | On-screen display |
| Printed Reports | Convenient and sometimes necessary |

### Site Structure

| Guideline | Description |
|-----------|-------------|
| Organization | Organize files into functional folders |
| Images | Put all images in one folder |
| Documents | Put all documents in one folder |
| Benefits | Easier maintenance, better organization |

### Navigation

| Principle | Description |
|-----------|-------------|
| Essential Aspect | Critical for any website |
| Natural Way | Incorporate content and layout to guide users |
| Efficiency | Enable quick and easy browsing |
| Clarity | Users should never wonder where links go |
| Consistency | Consistent navigational bar throughout site |
| "Don't Make Me Think" | Rule of usability - make it obvious |

### Navigation Best Practices

| Practice | Description |
|----------|-------------|
| Short Links | Brief, to-the-point link text |
| Consistent Bar | Same navigation on all pages |
| Discovery | Users find destination without returning to top |
| Drill-down | Avoid excessive clicking through sections |

### Page Necessities

| Information | Purpose | Location |
|-------------|---------|----------|
| Creator/Sponsor | Who created/sponsored page | Upper left (logos) |
| Contact | Email for contact person | Anywhere prominent |
| Content | What page contains | Title and heading |
| Last Modified | When content was last updated | Visible location |
| Location | Where page resides (physical address) | On page |
| Plug-ins | Required software for viewing | Text description + download URL |

### Web-Safe Color

| Era | Situation |
|------|----------|
| Mid 1990s | 8-bit video cards, 256 colors |
| Current | Most users have millions of colors |

| Concept | Details |
|---------|---------|
| Palette | 216 unique colors that don't dither |
| Purpose | Ensure colors display correctly on all platforms/browsers |
| Current Status | Justification diminished for modern systems |
| Importance | Historical significance, built-in to applications |
| Resource | http://www.lynda.com/hexv.html |

### Color Schemes

| Principle | Description |
|-----------|-------------|
| Background Colors | Used with text-heavy content for comfort |
| Color Contrast | Important for readability (luminosity) |
| Example | Black text on white background (extreme contrast) |
| Goal | Prevent colors from interfering with content access |

### Size Considerations

| Element | Consideration |
|---------|---------------|
| Thumbnails | Small preview images for navigation |
| Full-size | Larger images for detailed viewing |
| Bandwidth | Consider file size and download time |
| Resolution | Optimize for various screen sizes |

---

## Summary

### Course Learning Outcomes Achievement

| CLO | Module(s) | Key Topics |
|-----|-----------|------------|
| **CLO1: Explain concepts** | All modules | HTML5, CSS, ASP.NET, ADO.NET, WSDM, Accessibility, Security, HCI |
| **CLO2: Construct web application** | Modules 1, 2, 3, 4 | HTML5/CSS (front-end), ASP.NET (back-end), ADO.NET (database) |

### Technology Stack Summary

| Layer | Technology |
|-------|------------|
| **Front-end** | HTML5, CSS, JavaScript |
| **Back-end** | ASP.NET (C# or VB.NET) |
| **Database** | SQL Server or Access |
| **Server** | IIS (Internet Information Services) |
| **Development** | Visual Studio |
| **Design** | WSDM methodology |

### Key Development Principles

| Principle | Application |
|-----------|-------------|
| **Accessibility** | WAI guidelines, alt tags, semantic HTML |
| **Usability** | HCI principles, user-centered design |
| **Security** | Authentication, authorization, secure coding |
| **Design** | WSDM methodology, audience-driven approach |
| **Quality** | Evaluation criteria, testing, validation |

---

## References

| Resource | Author | Year | ISBN |
|----------|--------|------|------|
| Essential ASP.NET Web Forms Development | Robert E. Beasley | 2021 | 978-1484257838 |
| HTML CSS and JavaScript | Hanumanth L. | 2021 | 9798488815360 |
| Learn C# Programming | Marius Bancila et al. | 2020 | 978-1789805864 |
| Programming C# 10 | Ian Griffiths | 2020 | 978-1098117818 |

### Online Resources

| Resource | URL |
|----------|-----|
| W3C Markup Validation | http://validator.w3.org |
| Web Accessibility Initiative | http://www.w3.org/WAI |
| WSDM Overview | http://wsdm.vub.ac.be/Research/overview.php |
| Web-Safe Color Palette | http://www.lynda.com/hexv.html |

---

*End of Comprehensive Lecture Notes for CT050-3-2 Web Applications*
