FROM jenkins/jenkins:2.176.2

ENV JAVA_OPTS -Djenkins.install.runSetupWizard=false \
              -Djava.awt.headless=true \
              -Dhudson.model.ParametersAction.keepUndefinedParameters=true

# Install plugins
COPY plugins/plugins.txt /usr/share/jenkins/ref/plugins.txt
RUN /usr/local/bin/install-plugins.sh < /usr/share/jenkins/ref/plugins.txt


