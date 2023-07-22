# Getting Started with Jenkins (3rd Edition)

## Sample Repo

- `spring-petclinic` fork [g0t4/course3-jenkins-gs-spring-petclinic](//github.com/g0t4/course3-jenkins-gs-spring-petclinic)

## Demos

- Use [install](./install/compose.yaml) to run only Jenkins in a container.
- Use [emails](./emails/compose.yaml) to run only MailHog in a container.
  - This allows Jenkins on your host (ie via `jenkins.war`) to use a container based mailhog instance.
- Use [both](./both/compose.yaml) to run both Jenkins and MailHog in containers.
  - FYI, when configuring `SMTP` in Jenkins, use:
    - hostname `email` (compose file service name for mailhog)
    - port `1025`

## Links

- [jenkins.io](https://jenkins.io)
  - [docs](https://www.jenkins.io/doc/)
- [installation](https://www.jenkins.io/doc/book/installing/)
  - [Temurin releases](https://adoptium.net/temurin/releases/)
