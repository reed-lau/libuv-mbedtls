## Transport Layer Security

### TLS Record Protocol
```c
typedef uint8_t RecordType;
/* supported record types:
 *
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
  
} HandShake;
```
