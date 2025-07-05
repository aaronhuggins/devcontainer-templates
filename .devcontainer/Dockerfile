FROM denoland/deno:bin AS deno
FROM fedora:latest
ARG remoteUser
COPY --from=deno /deno /usr/local/bin/deno
RUN dnf install -y --refresh bash openssh git which vim-enhanced curl file
RUN curl -sS https://starship.rs/install.sh | sh -s -- -y
RUN useradd -ms /bin/bash ${remoteUser}
USER ${remoteUser}
RUN echo 'eval $(starship init bash)' >> ~/.bashrc
