Create new challenge
====================

#. Download the template challenge repo

#. Open it with `VS Code <https://code.visualstudio.com/>`_

#. Setup the platformio.ini file

    #. You can share your own board (:doc:`Link <share_device>`)
    #. Use a board from the community (:doc:`Link <../learn/community_device>`)

#. The lib/challenge/src/challenge.cpp file contains the challenge description, and a function, that the student should fill with the solution. (There can be more functions, and more challenge files btw, but the rest of the code should be adapted).
    
    #. Explain the challenge in comments
    #. Write the function signature and body, with a dummy return, so you can build and test your code.

#. The testing/inc/testing.hpp and testing/src/testing.cpp are containing the testing functions that test the students' solution. If you have your own implementation of the challenge (a solution for the challenge), so you can easily test the students code, you should put it in the testing.cpp, because it will be archived, and the student won’t be able to read it easily.
    
    #. Write the test in the testing.hpp and testing.cpp
    #. You can use the challenge.hpp in the testing.hpp file (else it will fail)

#. The sample_tests/sample_tests.cpp contains the calling of the tests you wrote in testing.hpp and testing.cpp. This file will be called, when the student runs the unit tests.
    
    #. Call your test functions with RUN_TEST() between UNITY_BEGIN(); and UNITY_END();
    #. All the tests that are called in the sample_test.cpp, will be run in the same run of the microcontroller
    #. If you need to do tests after fresh flashing, you can create a new folder under test/ like sample_test2, and copy the content of the sample_tests.cpp to sample_tests2.cpp file, but change the RUN_TEST() calls. Each subfolder under test, will have a fresh reflashing of the microcontroller. Each folder will be executed independently, after reflashing.

#. If you are ready with all the files, test it if it runs on the microcontroller, you want to use. If it does not work, debug it.

    #. All tests will fail, because you did not solve the challenge
    #. If you want to make sure the tests are good, add your solution into the challenge file, and test it, if all the tests are passing.

#. If it works, you should change the content of the lib/testing folder, like the following:

    #. Go to .pio/build/<env_name>, and look for the libtesting.a, and copy it to the lib/testing folder.
    #. Uncomment (remove semicolon) in the platformio.ini file from the following line:
    
    .. code-block:: text
    
        ;build_flags = -Ilib/testing/inc -Llib/testing -llibtesting

#. You are done! Zip this folder, or push it to git, and you can send it around.

#. If you want to submit to the community, then please send us the link for the git repo, or just the source, and we will create the git repo, then share it with the community. Thanks for sharing :)
