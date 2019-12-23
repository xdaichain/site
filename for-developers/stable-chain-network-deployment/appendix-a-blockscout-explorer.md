# Appendix A: BlockScout Explorer

To use `Blockscout` explorer follow this repo: [https://github.com/poanetwork/blockscout-terraform](https://github.com/poanetwork/blockscout-terraform)

On the bootnode for blockscout, add/replace the following sections in the `node.toml` file. Restart poa-parity.service

```text
    [rpc]
    apis = ["web3","eth","net", "parity", "traces"]
    processing_threads = 2
    server_threads = 2
    cors=["all"]

    [footprint]
    tracing = "on"
    pruning = "archive"
    fat_db = "on"

    [websockets]
    #max_connections = 1000
    apis = ["web3","eth","net","parity", "pubsub", "traces"]
```

Also, add the following section into the `/etc/nginx/conf.d/default.conf` file to enable websockets.

```text
    location /ws {
      proxy_set_header Host localhost:8546;
      proxy_set_header X-Real-IP $remote_addr;
      proxy_set_header Content-Type application/json;
      #add_header Access-Control-Allow-Origin "*";
      #add_header Access-Control-Allow-Headers "Origin, X-Requested-With, Content-Type, Accept";

      if ($request_method = 'OPTIONS') {
        add_header Access-Control-Allow-Headers "Origin, X-Requested-With, Content-Type, Accept";
        add_header Access-Control-Allow-Methods "GET, POST, OPTIONS";
        add_header Access-Control-Allow-Origin "*";
        add_header Access-Control-Max-Age 600;
        add_header Content-Type 'text/plain charset=UTF-8';
        add_header Content-Length 0;
        return 204;
      }
      proxy_pass http://localhost:8546;
      proxy_read_timeout 3600s;
      proxy_send_timeout 3600s;
      proxy_http_version 1.1;
      proxy_set_header Upgrade $http_upgrade;
      proxy_set_header Connection "upgrade";
    }
```

{% hint style="warning" %}
When configuring blockscout, you need to assign a public domain name to this node \(make sure 443 port is open\), e.g. `https://blockscout-node-trace-ws.nowhere` and use it for blockscout configuration, along with `wss://blockscout-node-trace-ws.nowhere/ws` for web-sockets.
{% endhint %}

