# Use the latest Grafana image
FROM grafana/grafana:latest

# Ensure we are using root to make permissions-related changes
USER root

# Add custom CSS
COPY styles.css /usr/share/grafana/public/css/

# Add a custom footer HTML
COPY custom_footer.html /usr/share/grafana/public/views/

# Replace the default Grafana logo with a custom one
COPY danieli.svg /usr/share/grafana/public/img/grafana_icon.svg

# Modify JavaScript files to change the welcome message to 'Welcome to JSW'
RUN sed -i 's/Welcome to Grafana/Welcome to JSW/g' /usr/share/grafana/public/build/*.js

# Switch back to the grafana user for security reasons
USER grafana
