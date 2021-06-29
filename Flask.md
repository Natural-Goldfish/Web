# Application Object

- ## app.config
  _Flask.Config class_ 와 같은 _configuration dictionary_ 입니다. Regular dictionary와 동일하게 동작하지만, configuration을 file에서 load하기 위한 추가 methods를 지원합니다. Default configuration parameters는 아래와 같습니다. :
  
  ```python
  default_config = {
      'APPLICATION_ROOT': '/',
      'DEBUG': None, 
      'ENV': None, 
      'EXPLAIN_TEMPLATE_LOADING': False, 
      'JSONIFY_MIMETYPE': 'application/json', 
      'JSONIFY_PRETTYPRINT_REGULAR': False, 
      'JSON_AS_ASCII': True, 
      'JSON_SORT_KEYS': True, 
      'MAX_CONTENT_LENGTH': None, 
      'MAX_COOKIE_SIZE': 4093,
      'PERMANENT_SESSION_LIFETIME': datetime.timedelta(days=31),
      'PREFERRED_URL_SCHEME': 'http',
      'PRESERVE_CONTEXT_ON_EXCEPTION': None,
      'PROPAGATE_EXCEPTIONS': None, 
      'SECRET_KEY': None,
      'SEND_FILE_MAX_AGE_DEFAULT': None,
      'SERVER_NAME': None, 
      'SESSION_COOKIE_DOMAIN': None,
      'SESSION_COOKIE_HTTPONLY': True,
      'SESSION_COOKIE_NAME': 'session',
      'SESSION_COOKIE_PATH': None,
      'SESSION_COOKIE_SAMESITE': None,
      'SESSION_COOKIE_SECURE': False,
      'SESSION_REFRESH_EACH_REQUEST': True,
      'TEMPLATES_AUTO_RELOAD': None,
      'TESTING': False,
      'TRAP_BAD_REQUEST_ERRORS': None,
      'TRAP_HTTP_EXCEPTIONS': False,
      'USE_X_SENDFILE': False
  }
  ```
  
- ## property debug : bool
  Application object의 property인 이 값은 _DEBUG config key와 mapping됩니다._ 
  Debug mode를 사용하게 되면, _flask run_ 을 사용하여 development server를 실행했을 때, interactive debugger가 unhandled exceptions를 표시합니다. 
  또한, code에 변화가 생길 때마다 server가 자동으로 reload되어, 서버를 재실행 해야하는 불편함이 없습니다. 
  이 값은 application object의 _env_ 값이 _'development'_ 인 경우나 _FLASK_DEBUG_ envrionment variable에 의해 overridden 되었을 때 활성화 됩니다. 
  따라서, code내에서 값을 설정한 경우에는 예상했던대로 동작하지 않을 수 있습니다.  

  _Default : True if env is 'development', or False otherwise._

- ## env
  Application이 실행되는 환경을 의미합니다. Flask와 extensions는 실행되는 환경에 따라, 가능한 행동이 있습니다. 예를 들어, debug mode를 실행하는 것이 있습니다. 이 값은 _ENV config key와 mapping 됩니다._ 또한, _FLASK_ENV_ envrionment variable에 의해 설정 될 수 있으며, code내에서 값을 설정한 경우에는 예상했던대로 동작하지 않을 수 있습니다.  
  
  _Default : 'production'_
  
