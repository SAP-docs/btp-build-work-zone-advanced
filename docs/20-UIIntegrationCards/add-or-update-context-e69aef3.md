<!-- loioe69aef3fb6f448d084ce601ebf4555da -->

# Add or Update Context

Card actions provide a mechanism to make elements interactive. Card actions are either attached by the card developer to the desired element \(card header, content, list item, etc.\), or built into the element. Upon user interaction, a corresponding event is dispatched for handling. If there is a predefined behavior for the action \(for example, for Navigation\) it will be executed. To add or update a context, you need to use a customized SAP UI5 Card action named *updateContext*.

The *updateContext* action is used to send a context value, and all cards in the page will be refreshed after the context is updated with the new context value. For more information, see [Card Features](https://ui5.sap.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/features).



<a name="loioe69aef3fb6f448d084ce601ebf4555da__section_f1r_m4k_4sb"/>

## Action Properties


<table>
<tr>
<th valign="top">

Property



</th>
<th valign="top">

Type



</th>
<th valign="top">

Default Value



</th>
<th valign="top">

Required



</th>
<th valign="top">

Description



</th>
</tr>
<tr>
<td valign="top">

type



</td>
<td valign="top">

CardActionType



</td>
<td valign="top">

 



</td>
<td valign="top">

Yes



</td>
<td valign="top">

The type of the action. Predefined types are *Navigation* and *Submit*. Custom defined type for update context is *updateContext*.



</td>
</tr>
<tr>
<td valign="top">

enabled



</td>
<td valign="top">

boolean



</td>
<td valign="top">

true



</td>
<td valign="top">

No



</td>
<td valign="top">

If the action is enabled.



</td>
</tr>
<tr>
<td valign="top">

parameters



</td>
<td valign="top">

Object



</td>
<td valign="top">

 



</td>
<td valign="top">

No



</td>
<td valign="top">

The parameters of the action.



</td>
</tr>
</table>



<a name="loioe69aef3fb6f448d084ce601ebf4555da__section_nxq_bpk_4sb"/>

## Parameters for Action of Type *updateContext*


<table>
<tr>
<th valign="top">

Property



</th>
<th valign="top">

Type



</th>
<th valign="top">

Default Value



</th>
<th valign="top">

Required



</th>
<th valign="top">

Description



</th>
</tr>
<tr>
<td valign="top">

namespace



</td>
<td valign="top">

string



</td>
<td valign="top">

 



</td>
<td valign="top">

Yes



</td>
<td valign="top">

The namespace of context, namespaces are used to identify context values from different card developers.



</td>
</tr>
<tr>
<td valign="top">

context



</td>
<td valign="top">

Object



</td>
<td valign="top">

 



</td>
<td valign="top">

Yes



</td>
<td valign="top">

If the action is enabled.



</td>
</tr>
</table>



<a name="loioe69aef3fb6f448d084ce601ebf4555da__section_cdt_lpk_4sb"/>

## Reserved Namespace

There are some reserved namespaces for system environment context or other uses:

-   Namespace: *sap.workzone*

    **Context**:

    > ### Code Syntax:  
    > ```
    > "currentUser": {
    >     "id", ID of current user
    >     "name", Name of current user
    >     "firstName", First name of current user
    >     "lastName", Last name of current user
    >     "email" Email of current user
    >     "global_uuid" SAP global UUID
    >     "user_type" Whether this user is internal or external
    >     "time_zone" Time zone used by current user
    > },
    > "currentWorkspace": {
    >     "id", ID of a workspace where the card is added by a page administrator
    >     "name" Name of a workspace where the card is added by a page administrator
    >     },
    > "currentCompany": {
    >     "id", ID of the company where the card is added by a page administrator
    >     "name", Name of the company where the card is added by a page administrator
    >     "web_host" The host name of your Work Zone system
    > }
    > 
    > ```

-   Namespace: *sap.successfactors*

    **Context**:

    > ### Code Syntax:  
    > ```
    > "currentUser": {
    >     "id", The user ID of connected Success Factors system
    > },
    > "currentCompany": {
    >     "id", The company ID of connected Success Factors system
    >     "web_host" The hostname of the connected Success Factors systems
    > }
    > 
    > ```


> ### Example:  
> > ### Sample Code:  
> > ```
> > ...                
> >            "actions": [
> >                     {
> >                         "type": "updateContext",
> >                         "parameters": {
> >                             "namespace": "sap.cardcontextexample",
> >                             "context": {
> >                                 "user": {
> >                                    "id": "1",
> >                                   "name": "Nick"
> >                                 }
> >                             }
> >                         }
> >                     }
> >                 ]
> >          handleChange: function (oEvent) {
> >             var oComponent = this.getOwnerComponent(),
> >                 oCard = oComponent.oCard,
> >                 brand = oEvent.mParameters.value;
> > 
> >             oCard.triggerAction({
> >                 type: "updateContext",
> >                 parameters: {
> >                     "namespace": "sap.cardcontextexample",
> >                     "context": {
> >                         "brand": brand
> >                     }
> >                 }
> >             });
> >         }
> >  
> > 
> > ```

