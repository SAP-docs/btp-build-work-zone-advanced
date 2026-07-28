<!-- loiodf89bb34fd84421c945b70856061a1dc -->

# Configuring External Users Authentication

To allow external users to access the system, they should be authenticated. The following configuration steps are required to enable external user authentication.



<a name="loiodf89bb34fd84421c945b70856061a1dc__section_obd_d3y_jqb"/>

## Prerequisites

The following prerequisites should already be configured as apart of the onboarding to SAP Build Work Zone, advanced edition/ SAP SuccessFactors Work Zone.

-   There is a trust between SAP BTP, Cloud Foundry Environment and Identity Authentication.
-   The Identity Authentication service is configured as a source for user provisioning \(or it is configured as a proxy to a corporate IdP, which is configured as a source system for user provisioning\).
-   SAP Build Work Zone, advanced edition or SAP SuccessFactors Work Zone are configured as a target system for user provisioning, and the transformation code handles external users: `'Workzone_User_Type_public'`.



<a name="loiodf89bb34fd84421c945b70856061a1dc__section_pfz_qvb_31c"/>

## Procedure

1.  **Register the Identity Authentication as a SAML Trusted IDP**
    1.  In the *Administration Console*, go to *Authentication & Authorization* \> *SAML Trusted IDPs*.
    2.  Make sure that the Identity Authentication service appears in the list \(it should be following the onboarding configuration\).
    3.  If it's not in the list, click the *Register your SAML Trusted IDP* button and upload the SAML 2.0 metadata file that you've downloaded from Identity Authentication during the onboarding flow. For more information, see [Prerequisites](prerequisites-9e78b62.md).
    4.  To allow creation of external users based on SAML-assertions, enable this option:

        ![Shows the option to enable SAML assertions.](images/Enable_SAML_c126843.png)

    5.  Click *Register*.

2.  **Review the SCIM OAuth Client**

    The required SCIM API OAuth Client should be generated automatically during onboarding to SAP Build Work Zone, advanced edition. In the *Administration Console*, go to the *External Integrations* section, and on the *OAuth Clients* screen, review the details of the `Workzone API Client` OAuth client.

3.  **Configure the Identity Authentication service provider API credentials**

    The Identity Authentication service provider API credentials are needed to allow users to invite external users based on their email address and trigger an Identity Authentication-level invitation for the registration process.


    <table>
    <tr>
    <th valign="top">

    Step
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Generate client credentials in the Identity Authentication service.
    
    </td>
    <td valign="top">
    
    1.  In the SAP Cloud Identity Services, Identity Authentication admin console, open *Applications & Resources* \> *Applications*, and select the SAP Build Work Zone, advanced edition/ SAP SuccessFactors Work Zone application .
    2.  In the *Application APIs* \> *Client Authentication* screen, go to the *Secret* section and click *Add*.
    3.  Enter the *Description*, *Expire in*, and *Scope* details. The *OpenID* scope option isn't required.
    4.  Click *Save*. This will generate client credentials.

        > ### Tip:  
        > Make sure to securely save these credentials \(for example, in a password manager\), as they won't be accessible anymore after clicking OK\).

    5.  Click *OK*.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Enter the client credentials in SAP Build Work Zone, advanced edition.
    
    </td>
    <td valign="top">
    
    1.  In the *Administration Console*, go to *Feature Enablement* \> *Features*.

    2.  Enter the Identity Authentication Client ID and secret:

        ![Shows where to enter the IAS credentials.](images/IAS_Credentials_1388c6e.png)

        > ### Note:  
        > Allowing external users to be created through a workspace invitation email and self-registration is optional. Without it, only existing external users can be invited as members to workspaces.

    3.  Click *Save Changes*.



    
    </td>
    </tr>
    </table>
    
4.  **Configure real-time provisioning**

    Configure real-time provisioning from *Identity Authentication* \> *Identity Provisioning* \> **.

    Without real-time provisioning, new users that performed self-registration would need to wait for the next Identity Provisioning job schedule to happen before they can access SAP Build Work Zone, advanced edition. With the real-time setup, the Identity Authentication service immediately triggers the user provisioning upon successful registration.

    For more information, see: [Real-Time Provisioning: Identity Authentication](https://help.sap.com/viewer/f48e822d6d484fa5ade7dda78b64d9f5/Cloud/en-US/70afd909734842b08ff8f1be5b01bc2a.html)


