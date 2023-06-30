FROM jenkins/jenkins

# jenkins user has trouble accessing bind mounted docker.sock (DooD scenario) so use root to run jenkins
USER root

RUN curl -fsSL https://download.docker.com/linux/debian/gpg | gpg --dearmor -o /etc/apt/keyrings/docker.gpg \
  && chmod a+r /etc/apt/keyrings/docker.gpg \
  && echo \
    "deb [arch="$(dpkg --print-architecture)" signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/debian \
    "$(. /etc/os-release && echo "$VERSION_CODENAME")" stable" | \
    tee /etc/apt/sources.list.d/docker.list > /dev/null \
  && apt-get update \
  && apt-get install -y docker-ce-cli file

# reclaim ownership for root - FYI if you start as one user and switch then change ownership to new user for all of JENKINS_HOME else you can run into issues (ie lingering workspace owned by old user, git will refuse to checkout a new repo b/c git config safe.directory)
# RUN chown root:root /var/jenkins_home
# untested => todo test this... existing volumes should need to be modified manually if switch users with already created say named volume for /var/jenkins_home
