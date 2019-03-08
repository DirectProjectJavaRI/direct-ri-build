# Direct Project Build
This contains instructions for cloing the DirectProject Java RI projects and building all components including the Stock Assembly.


## Clone repositories
Each module of the Java RI is contained within its own repository.  You can either manually clone each repository, or you could create an automated script to clone all repositories.  If you have access to a Unix based shell, you can run the following command (assuming you have all the command tools installed) to clone all repositories:

`curl -s https://api.github.com/orgs/DirectProjectJavaRI/repos?per_page=200 | jq .[].git_url | xargs -n 1 git clone`

## Build Components
After cloning all repositories, switch to the `direct-ri-build` directory and run the following command to build all components.

`mvn clean install`
