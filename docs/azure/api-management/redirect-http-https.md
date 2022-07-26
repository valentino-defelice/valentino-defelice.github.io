# Redirect all HTTP trafic to HTTPs

To do that, we'll need to enable both trafics from api config (HTTPS(s)) and add a policy into "Inbound" section to override incoming url to HTTPS

### Policy:
```
<inbound>
...
<choose>
    <when condition="@(context.Request.OriginalUrl.Scheme.Equals("http"))">
        <return-response>
            <set-status code="302" reason="Requires SSL" />
                <set-header exists-action="override" name="Location">
                    <value>@("https://" + context.Request.OriginalUrl.Host + context.Request.OriginalUrl.Path)</value>
                </set-header>
        </return-response>
    </when>
</choose>
...
<base />
</inbound>
```

Credits: https://dipolimene.medium.com/enforcing-all-requests-to-apim-over-https-2e8f4b7e03e2
