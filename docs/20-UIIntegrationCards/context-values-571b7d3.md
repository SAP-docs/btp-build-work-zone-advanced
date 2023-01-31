<!-- loio571b7d3a34bc4dc982da37187cecd7a0 -->

# Context Values

Using *getContextValue* from *sap.ui.integration.Host* resolves the value for a given path in the context of the host. Contexts can be used to configure cards with information available in the host environment.

**Context Structure**:

> ### Example:  
> > ### Sample Code:  
> > ```
> > { 
> > "sap.workzone": 
> > { 
> > "currentUser: 
> > { 
> > "id": 
> > { 
> > "label": "Id of the Work Zone user", "placeholder": "Work Zone user id", "description": "The value will change based on the logged on user" 
> > } 
> > } 
> > } 
> > ... 
> > }
> > ```

**Path to the Current userid of the Context**:

> ### Example:  
> `sPath = "sap.workzone/currentUser/id" parameter: { userId: { value: "{context>sap.workzone/currentUser/id}" resolves to UserId } }`

For more information, see [Cards Documentation](https://sapui5.hana.ondemand.com/#/api/sap.ui.integration.Host%23events/Summary).

> ### Example:  
> > ### Sample Code:  
> > ```
> > oSelect = this.byId('brandCombobox'),
> > oCard = oComponent.oCard
> > oCard.getHostInstance().getContextValue("sap.cardcontextexample/brand").then(function(value){
> >     oSelect.setSelectedKey(value);
> > });
> > 
> > ```

