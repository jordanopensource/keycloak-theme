# JOSA Keycloak Theme

A custom Keycloak theme for JOSA ID.

# Development

For development, there is a `Dockerfile.dev` that can be built and run locally to shorten the feedback loop.

For development, you can do the following:

```
docker build -f Dockerfile.dev -t josa-theme .

docker run -d --rm --name josa-theme -v (pwd)/josa_theme:/opt/jboss/keycloak/themes/josa_theme -p 8080:8080 -e KEYCLOAK_USER=admin -e KEYCLOAK_PASSWORD=admin -e KEYCLOAK_IMPORT=/tmp/josa-realm.json josa-theme
```

Then, after waiting for the service to start, connect to the url http://localhost:8080/auth/realms/JOSA/account/

You can make changes to the theme and refresh in your browser to see the updates. You need to do a hard refresh (e.g., Shift-Refresh on Safari) or ensure the cache is disabled to see your changes.

## Structure

To understand the structure of the content, you may need to consult the source code for the theme.

Download the source for the release that is used (https://github.com/keycloak/keycloak/releases/tag/11.0.3) and then look in the `themes/src/main/resources/theme` folder for the `base` and `keycloak` templates. Official theme examples are found in `examples/themes/src/main/resources/theme` folder.

