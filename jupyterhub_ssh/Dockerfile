# FROM jupyterhub/jupyterhub:$JUPYTERHUB_VERSION AS base

# # Install dockerspawner,
# # hadolint ignore=DL3013
# RUN python3 -m pip install --no-cache-dir \
#     dockerspawner

# # Install self build ldapauthenticator
# ARG AUTHENTICATOR_PATH

# RUN echo "Using Auth: $AUTHENTICATOR_PATH "
# COPY $AUTHENTICATOR_PATH $AUTHENTICATOR_PATH
# RUN python3 -m pip install --no-cache-dir $AUTHENTICATOR_PATH
# RUN rm $AUTHENTICATOR_PATH

# # Add static route for static content
# RUN mkdir -p /srv/jupyterhub/assets/static
# # Symlink it into custom
# RUN ln -sf /srv/jupyterhub/assets/static /usr/local/share/jupyterhub/static/custom

# # DEBUGGER IMAGE

# FROM base as debugger

# RUN python3 -m pip install --no-cache-dir \
#     debugpy

# ENTRYPOINT ["python3", "-m", "debugpy", "--listen", "0.0.0.0:5678", "--wait-for-client", "-m"]


# # PRIMARY IMAGE

# FROM base as primary

# ENTRYPOINT ["jupyterhub", "-f", "/srv/jupyterhub/jupyterhub_config.py"]