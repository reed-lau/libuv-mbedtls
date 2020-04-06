## Transport Layer Security

### TLS Record Protocol
```c
typedef uint8_t RecordType;
/*
 * change_cipher_spec = 20;
 * alert              = 21;
 * handshake          = 22;
 * application_data.  = 23;
 */

typedef struct {
  uint8_t major;
  uint8_t minior;
} ProtocolVersion;
/*
 * TLS1.0 : major = 3, minior = 1;
 * TLS1.1 : major = 3, minior = 2;
 * TLS1.2 : major = 3, minior = 3;
 */

typedef uint8_t HandShakeType;
/*
 * hello_request.      = 0;
 * client_hello        = 1;
 * server_hello.       = 2;
 * certificate         = 11;
 * server_key_exchange = 12;
 * certificate_request = 13;
 * server_hello_done   = 14;
 * certificate_verify  = 15;
 * client_key_exchange = 16;
 * finished            = 20;
 */

typedef struct {
  uint8_t unix_time[4];
  uint8_t random[28];
} Random;

typedef struct {
  uint8_t length;
  uint8_t data[0];
} SessionId;

typedef struct {
  uint16_t length;
  uint16_t ciphers[1];
} CipherSuiteList;

typedef struct {
  uint8_t length;
  uint8_t compress_method[0];
} CompressionMethod;

typedef struct {
  uint16_t type;
  uint16_t length;
  uint8_t  data[1];
} Extension;
/* type:
 * server_name = 0;
 * max_fragment_length = 1;
 * client_certificate_url = 2;
 * trusted_ca_keys = 3;
 * truncated_hmac = 4;
 * status_request = 5;
 */

typedef struct {
  uint16_t length;
  Extension *Extension;
} Extensions;

typedef struct {
  PrococolVersion version;
  Random  random;
  SessionId session_id;
  CipherSuiteList cipher_suite;
  CompressionMethod compression_method;
  Extensions extensions;
} ClientHello;

typedef struct {
  
} HandShake;

```
