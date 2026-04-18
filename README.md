# Degree-Notes
just a collection for degree notes

# To make the ASP.NET do validation without a JQuery

## In Web.config (global)
ADD:
```
<appSettings>
  <add key="ValidationSettings:UnobtrusiveValidationMode" value="None" />
</appSettings>
```

## In .aspx.cs (local)
Under Page_Load ADD:
```
this.UnobtrusiveValidationMode = UnobtrusiveValidationMode.None;
```

## In .aspx file 
In the first tag (<% Page... %>) ADD
```
UnobtrusiveValidationMode="None"
```
