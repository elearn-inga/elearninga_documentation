Local device
============

How to use your own board for testing?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

    #. Look up your board, platform, framework info here: https://platformio.org/boards
    #. Check on which port it connects to your PC (COM*, or provided here: https://docs.platformio.org/en/latest/projectconf/section_env_upload.html)
    #. Set the env, platform, board and framework of your device in your platformio.ini

        .. code-block:: text
        
            [env:megaatmega2560]
            platform = atmelavr
            board = megaatmega2560
            framework = arduino
            build_flags = -Ilib/testing/inc -Llib/testing -llibtesting
    
    #. Then you can to use the `PlatformIO: Test` feature to test locally

        .. figure:: ../_static/img/local_test.png
            :alt: local testing
