# Readmes
location ^~ /frontend-product-admin/ {
    index  index.html index.htm;
    try_files $uri @fallback;
    allow all;
}

location @fallback {
    rewrite .* /frontend-product-admin/index.html break;
}
