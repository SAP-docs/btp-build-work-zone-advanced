<!-- loio499e40c908d7468b97f7dd8e22946bb7 -->

# Setting Up a Custom Domain for SAP Build Work Zone Advanced Mobile App

You can set up a dedicated custom domain for the SAP Build Work Zone Advanced mobile app.



If you are using a custom domain, you can set up a dedicated custom domain for the SAP Build Work Zone Advanced mobile app.

To set up this custom domain, do the following steps:

1.  Create a CNAME record in the Domain Name Service \(DNS\) that points to the appropriate service endpoint provided by your SAP Build Work Zone, advanced edition configuration. An example would be `connect-mobile.capcx.com`.

2.  Create a custom SaaS route in the Custom Domain service.

3.  Update the QR code. Replace the default QR code with your custom mobile domain QR code using a custom CSS. This QR code is essential for mobile client connections.


For more information about setting up a custom domain, see [Set Up a Custom Domain](set-up-a-custom-domain-50bcb51.md)



### Example:

-   **Default Domain:**

    -   **Regular:** https://\[subaccount domain\].workzone\*.cfapps.\[data center\].hana.ondemand.com
    -   **Mobile:** https://\[subaccount domain\].mobile.workzone\*.cfapps.\[data center\].hana.ondemand.com

    **Note:** \* `workzone` for SAP Build Work Zone, advanced edition and `workzonehr` for SAP SuccessFactors Work Zone.

-   **Custom Domain - mycompany.com:**

    -   **Regular:** workzone.mycompany.com
    -   **Mobile:** workzone.**mobile**.mycompany.com

    **Note:** the custom domain for mobile must follow the same top-level domain that is defined for SAP Build Work Zone, advanced edition, with “mobile” in the second position per the example above.




### QR Codes Updates:

-   The 2 “Install” QR Codes for iOS & Android can remain unchanged.
-   The “Registration” QR Code is the same across both platforms but needs to be adjusted to reflect the new custom mobile domain, instead of the default one.

    This change can be applied via custom CSS using the UI Theme Designer.


