# PhpStorm Debug Setup

1. Download UniServerZ.
2. In PhpStorm go to File->Settings, in Languages & Frameworks Tab choose PHP.
3. Specify language level (7.1 as this is written)
4. For CLI Interpreter entry, click '...'
5. Specify PHP executable location. For example: C:\Users\zha202\Downloads\UniServerZ\core\php71\php.exe
6. Click 'Open in Editor' link at the end of Configuration file section. Remove properties relating to XDebug if any.
7. Specify Debugger extension in Additional Section. For example:C:\Users\zha202\Downloads\UniServerZ\core\php71\extensions\php_xdebug.dll
8. Click Ok to save settings.
9. Click 'Servers' under Settings -> Languages & Frameworks -> PHP 
10. Click '+' to add a new server.
11. Use localhost as url of the server
12. Check 'Use path mappings ...' 
13. In Absolute path, enter the server root to map to project root.
14. In UniServerZ, edit the php_production.ini to make sure the [xdebug] section is like below:
    [xdebug]
    zend_extension=${US_ROOTF}/core/php71/extensions/php_xdebug.dll
    xdebug.remote_autostart=on
    xdebug.remote_enable=on
    xdebug.remote_host=127.0.0.1
    xdebug.remote_port=9000
    xdebug.remote_handler=dbgp
    xdebug.remote_mode=req
    xdebug.idekey=default
