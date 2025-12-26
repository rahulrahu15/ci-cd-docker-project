# ------------------------
# Stage 1: Build Stage (optional, if you have build tools)
# ------------------------
# Skipped if frontend is static HTML/CSS/JS

# ------------------------
# Stage 2: Runtime Stage (Distroless Static)
# ------------------------
FROM gcr.io/distroless/static:nonroot

WORKDIR /usr/share/nginx/html

# Copy frontend static files
COPY . .

# Command to serve files (distroless static requires CMD)
CMD ["/usr/sbin/nginx","-g","daemon off;"]

