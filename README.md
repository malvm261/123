# ==========================================
# === АНОНИМИЗАЦИЯ ЗАГОЛОВКОВ ==============
# ==========================================

via off
forwarded_for delete

request_header_access Via deny all
request_header_access X-Forwarded-For deny all
request_header_access Pragma deny all
request_header_access Cache-Control deny all
