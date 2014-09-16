# Adding Red Hat Repositories

OK, once the manifest is imported we can look at enabling the Red Hat repositories to be downloaded to the Satellite server

The hammer command for enabling these Red Hat repositories is

```hammer repository-set  ```

There are a large number of repositories available, as can be seen by doing

```
hammer repository-set  list --product "Red Hat Enterprise Linux Server" \
--organization  "Example Org"
```

To get us started we shall only enable three Red Hat repositories - these are enough to enable us to perform provisioning

```
# hammer repository-set enable  --organization "Example Org" \
--product "Red Hat Enterprise Linux Server" \
--name "Red Hat Enterprise Linux 6 Server (Kickstart)" \
--releasever "6.5" --basearch "x86_64"

# hammer repository-set enable  --organization "Example Org" \
--product "Red Hat Enterprise Linux Server" \
--name "Red Hat Enterprise Linux 6 Server (RPMs)" \
--releasever "6.5" --basearch "x86_64"

# hammer repository-set enable  --organization "Example Org" \
--product "Red Hat Enterprise Linux Server" \
--name "Red Hat Enterprise Linux 6 Server - RH Common (RPMs)" \
--basearch "x86_64"
```

So now you have enabled s few repositories, but they are not syncronised. See the next section for this