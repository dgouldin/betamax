History
=======

0.3.0 - 2014-xx-xx
------------------

- Add ``digest-auth`` matcher to help users match the right request when using 
  requests' ``HTTPDigestAuth``.

- Reorganize and refactor the cassettes, matchers, and serializers modules.

0.2.0 - 2014-04-12
------------------

- Fix bug where new interactions recorded under ``new_episodes`` or ``all``
  were not actually saved to disk.

- Match URIs in a far more intelligent way.

- Use the Session's original adapters when making new requests

  In the event the Session has a custom adapter mounted, e.g., the SSLAdapter 
  in requests-toolbelt, then we should probably use that.

- Add ``on_init`` hook to ``BaseMatcher`` so matcher authors can customize 
  initialization

- Add support for custom Serialization formats. See the docs for more info.

- Add support for preserving exact body bytes.

- Deprecate ``serialize`` keyword to ``Betamax#use_cassette`` in preference 
  for ``serialize_with`` (to be more similar to VCR).

0.1.6 - 2013-12-07
------------------

- Fix how global settings and per-invocation options are persisted and 
  honored. (#10)

- Support ``match_requests_on`` as a parameter sent to
  ``Betamax#use_cassette``. (No issue)

0.1.5 - 2013-09-27
------------------

- Make sure what we pass to ``base64.b64decode`` is a bytes object

0.1.4 - 2013-09-27
------------------

- Do not try to sanitize something that may not exist.
 
0.1.3 - 2013-09-27
------------------

- Fix issue when response has a Content-Encoding of gzip and we need to 
  preserve the original bytes of the message.

0.1.2 - 2013-09-21
------------------

- Fix issues with how requests parses cookies out of responses

- Fix unicode issues with ``Response#text`` (trying to use ``Response#json``
  raises exception because it cannot use string decoding on a unicode string)

0.1.1 - 2013-09-19
------------------

- Fix issue where there is a unicode character not in ``range(128)``

0.1.0 - 2013-09-17
------------------

- Initial Release

- Support for VCR generated cassettes (JSON only)

- Support for ``re_record_interval``

- Support for the ``once``, ``all``, ``new_episodes``, ``all`` cassette modes

- Support for filtering sensitive data

- Support for the following methods of request matching:

  - Method

  - URI

  - Host

  - Path

  - Query String

  - Body

  - Headers
