- 👋 Hi, I’m @GaboSHT
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
GaboSHT/GaboSHT is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
# https://emscripten.org/docs/compiling/WebAssembly.html#web-server-setup
Options +MultiViews
RemoveType .gz
AddEncoding x-gzip .gz
AddType application/octet-stream .data
AddType application/wasm .wasm

# CPU-intensive, better pre-gzip
#AddOutputFilterByType DEFLATE application/wasm


# Force browser to check if cache needs to be refreshed or not (304) for XHR
# (preserve browser cache, but revalidate)
<IfModule mod_headers.c>
  Header set Cache-Control "max-age=0"
</IfModule>

# Disable ETags which don't play nice with mod_gzip and HTTP/1.1
# (ETags come in handy if you need to rollback to an older version though)
#<IfModule mod_headers.c>
#  # Generated ETags
#  Header unset ETag
#</IfModule>
## Static ETags
#FileETag None
