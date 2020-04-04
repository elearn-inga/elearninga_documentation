Solve challenges
================


#. Download the git repo for the challenge
#. Open the repo in VSCode

    a. File / Open folder
    b. Look for the root folder of the repo
    c. Ok

#. Open platformio.ini
#. Select a device to do the challenge on
#. Change the following values to match the device parameters

    .. code-block:: text

        [env:<Environment>]
        platform = <Platform>
        board = <Board>
        framework = <Framework>
        upload_port = <Upload_port>
        build_flags = <Link_tester_library>

    Example:

    .. code-block:: text

        [env:megaatmega2560]
        platform = atmelavr
        board = megaatmega2560
        framework = arduino
        upload_port = COM9
        build_flags = -Ilib/testing/inc -Llib/testing -llibtesting

#. Run the sample tests:
    
    a. Remote upload
    b. Remote Test

#. Solve the challenge

    a. Open lib/challenge/challenge.h
    b. Write the desired function
    c. Run remote test
