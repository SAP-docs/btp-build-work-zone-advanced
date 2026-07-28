<!-- loiofb5cca52c06949358cc3a0f41fac7118 -->

# Undeploying Content

To undeploy content, you must delete the content from the repository and delete the *app-host* service plan instance.



## Procedure

1.  Open the Cloud Foundry command line interface \(CLI\).

2.  Undeploy the `*.mtar` file using the CLI command: `cf undeploy <mta-id>` and add the `--delete-services` and `--delete-service-keys` options.

    -   Use the `–-delete-services` and `--delete-service-keys` options to delete the `app-host` service plan instance and the application content from HTML5 application repository.

    -   For the `cf undeploy` command, you need the `mta id`. To get the `mta id`, do one of the following:

        -   Call `cf mtas`.

        -   Check the `mtad.yaml ID`.



    Example:

    ```
    cf undeploy acme.crm --delete-services --delete-service-keys
    ```

    > ### Note:  
    > If you don’t want to use the `–-delete-services` and `–-delete-service-keys` options, you can delete the `app-host` service plan instance manually using the CLI command: `cf delete-service SERVICE-NAME`.


