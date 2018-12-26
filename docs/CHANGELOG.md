# Changelog

## 0.4.0


### Protocol
- Refatcored HTTP1, using MOSN's IO goroutine, 30% performance improvement
- Refatcored HTTP2, using MOSN's IO goroutine, 100% performance improvement
- Support GRPC in HTTP2, support pesudo header query
- Refatcored protocol framework
- Support HTTP1/HTTP2 protocol automatic identification
- Support tracing in SofaRPC

### Traffic Management
- Support retry policy
- Support direct response policy
- Support HTTP header rewrite, rewrite the Host and URI
- Support HTTP custom headers add/delete
- Optimize tcp proxy
- Support rate limit and qps limit
- Support fault inject

### Telemetry
- Support mixer report request/response info

### Extension
- Support more extensions
  - Support a scalable chain routing
  - SofaRPC Protocol support extension

### Others
- Add admin APIs, support update default logger level and get mosn's config
- Use RCU lock to update cluster

### Bug Fix
- Fix some memory leak bugs
- Fix some smooth upgrade bugs
- Fix some HTTP1/HTTP2 bugs
- Fix some tiny bugs


## 0.3.0
- Support router mode 
- Optimize statistic, support smooth upgrade statistic data 
- Support smooth upgrade on TLS
- Optimize cpu usage and memory footprint in SofaRPC
- Fix some bugs

## 0.2.1
- Add TLS disable flag in cluster's host, allows request upstream host in non-TLS mode
- Support dubbo in Xprotocol mode
- Fix some bugs

## 0.2.0
- Support wrr loadbalancer
- Support weighted subset router
- Support listener update/delete, integrated with ISTIO pilot by XDS api
- Support cluster update/delete, integrated with ISTIO pilot by XDS api
- Support network filter extensions, allows config multiple filters
- Support TLS extension, allows customized certificate acquisition
- Support io callback mechanism based on raw epoll/kqueue, optimize support for a large number of connections through io worker pool
- Enhance customized codec extension mechanism in protocol layer
- Add first version of x-protocol extension mechanism
- Add memory reuse framework, use it in io/protocol/stream/protocol layers
- Fix data race cases
- Fix some bugs

## 0.1.0
- Provide usable network programing models & extensible network filter extension framework
- Support protocol framework & sofa rpc implementation (tr/boltv1/boltv2)
- Support stream framework & http2 / sofa rpc stream & client & pool implementation
- Support stream filter extension framework & some filter implementation
- Support proxying http2 / sofa rpc request in a mesh way
- Support cluster management & lb strategies
- Integration with confreg in service discovery model
- Support basic route support
- Support start from a json-format config file
- Support HUP smooth reload
- Support process smooth upgrade
- Process guard by supervisord & log managed by logrotate
