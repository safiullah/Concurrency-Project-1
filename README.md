# Concurrency Project 1
 
- Task L1.1 : In the base class `TrafficObject`, set up a thread barrier in its destructor that ensures
that all the thread objects in the member vector` _threads` are joined.

- Task L1.2 : In the `Vehicle` class, start a thread with the member function `drive` and the
object `this` as the launch parameters. Also, add the created thread into the `_thread` vector of
the parent class.

- Task L1.3 : Vary the number of simulated vehicles in `main` and use the top function on the terminal
or the task manager of your system to observe the number of threads used by the simulation.

# launch.json

{
    // Use IntelliSense to learn about possible attributes.
    // Hover to view descriptions of existing attributes.
    // For more information, visit: https://go.microsoft.com/fwlink/?linkid=830387
    "version": "0.2.0",
    "configurations": [
        {
            "name": "(gdb) Launch",
            "type": "cppdbg",
            "request": "launch",
            "program": "${workspaceFolder}/build/traffic_simulation",
            "args": [],
            "stopAtEntry": true,
            "cwd": "${workspaceFolder}/build",
            "environment": [],
            "externalConsole": false,
            "MIMode": "gdb",
            "setupCommands": [
                {
                    "description": "Enable pretty-printing for gdb",
                    "text": "-enable-pretty-printing",
                    "ignoreFailures": true
                }
            ],
            "preLaunchTask": "g++ build active file"
            ,"miDebuggerPath": "/usr/bin/gdb"
        }
    ]
}

# tasks.json

{
    "version": "2.0.0",
    "tasks": [
        {
            "label": "g++ build active file",
            "type": "shell",
            "command": "cd build && cmake -DCMAKE_BUILD_TYPE=Debug .. && make",
            "problemMatcher": [],
            "group": {
                "kind": "build",
                "isDefault": true
            }
        }
    ]
}
