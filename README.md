To build a file-based key-value data store that supports the basic CRD (create, read, and delete) operations.

The data store will support the following  requirements:

1. A new key-value pair can be added to the data store using the Create operation. The key
   is always a string - capped at 32chars. The value is always a JSON object - capped at
   16KB.
2. If Create is invoked for an existing key, an appropriate error must be returned.
3. A Read operation on a key can be performed by providing the key, and receiving the
   value in response, as a JSON object.
4. A Delete operation can be performed by providing the key.
5. Every key supports setting a Time-To-Live property when it is created. This property is
   optional. If provided, it will be evaluated as an integer defining the number of seconds
   the key must be retained in the data store. Once the Time-To-Live for a key has expired,
   the key will no longer be available for Read or Delete operations.
6. The size of the file storing data must never exceed 1GB.   

