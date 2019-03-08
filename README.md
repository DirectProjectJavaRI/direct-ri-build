# Direct Project Build
This contains instructions for cloing the DirectProject Java RI projects and building all components including the Stock Assembly.

## Tools

The following tools are needed to perform the full build

* Maven
* Git
* JDK 8
* Ant
* Unzip
* Tar
* JQ (optional: for automated clone of all repositories)


## Clone repositories
Each module of the Java RI is contained within its own repository.  You can either manually clone each repository, or you could create an automated script to clone all repositories.  If you have access to a Unix based shell, you can run the following command (assuming you have all the command tools installed) to clone all repositories:

`curl -s https://api.github.com/orgs/DirectProjectJavaRI/repos?per_page=200 | jq .[].git_url | xargs -n 1 git clone`

If you want to build from the developement branch, specify that branch using the following command:

`curl -s https://api.github.com/orgs/DirectProjectJavaRI/repos?per_page=200 | jq .[].git_url | xargs -n 1 git clone -b develop`

## Build Components
All project using maven pom.xml files for the build lifecyle.  After cloning all repositories, switch to the `direct-ri-build` directory and run the following command to build all components.

`mvn clean install`
