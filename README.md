# jalylah
# Create project directory
mkdir http2-lab
cd http2-lab

# Initialize npm
npm init -y

# Create directory structure
mkdir -p servers clients public public/images scripts docs results
# Generate self-signed certificate
openssl req -x509 -newkey rsa:4096 -nodes \
  -keyout localhost-key.pem \
  -out localhost.pem \
  -days 365 \
  -subj "/C=ID/ST=East Java/L=Surabaya/O=HTTP2 Lab/CN=localhost" \
  -addext "subjectAltName=DNS:localhost,DNS:*.localhost,IP:127.0.0.1"

# Verify certificate
openssl x509 -in localhost.pem -text -noout | grep -A2 "Subject:"
