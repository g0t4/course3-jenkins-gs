# Getting Started with Jenkins (3rd Edition)

## Sample Repos

- `spring-petclinic` fork [g0t4/course3-jenkins-gs-spring-petclinic](https://github.com/g0t4/course3-jenkins-gs-spring-petclinic)

## Links

- [jenkins.io](https://jenkins.io)
  - [docs](https://www.jenkins.io/doc/)
- [installation](https://www.jenkins.io/doc/book/installing/)
  - [Temurin releases](https://adoptium.net/temurin/releases/)

## Jenkins CLI

```bash
# alias sweeps args under a rug:
alias jcli="java -jar $HOME/Downloads/jenkins-cli.jar -s http://jenkins:8080/ -auth @$HOME/Downloads/creds"

jcli help
jcli list-jobs
jcli install-plugin -restart pipeline-graph-view

jcli build foo -s -v
# -s = wait for job to complete, and Ctrl+C aborts job
# -v = follow (tail) console output
jenkins help build     # FYI get subcommand help
```

- docs:
  - bundled in Jenkins controller: http://jenkins:8080/manage/cli/
  - handbook: https://www.jenkins.io/doc/book/managing/cli/
