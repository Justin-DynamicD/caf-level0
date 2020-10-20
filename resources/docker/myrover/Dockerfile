###########################################################
# base MSRover to modify
###########################################################

ARG versionRover

FROM ${versionRover} as base

# all the versions we need to lock
# note these MUST be unique from existing ENV in base
# or they will be ignored
ARG versionPacker

###
# Install Packer
###
RUN echo "Installing packer ${versionPacker}..." && \
    sudo curl -sSL -o ./packer.zip https://releases.hashicorp.com/packer/${versionPacker}/packer_${versionPacker}_linux_amd64.zip && \
    sudo unzip -d /usr/bin ./packer.zip && \
    sudo chmod +x /usr/bin/packer && \
    sudo rm ./packer.zip

###
# Add aliases for packer
###
RUN echo "alias packer=/usr/bin/packer" >> /home/${USERNAME}/.bashrc