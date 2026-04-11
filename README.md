# http-server-cpp

HTTP server written in C++23 for Windows, built around a service registry that wires up communication, logging, and configuration services under a single TCP server loop.

## Platform

- Windows (links against `ws2_32`)
- g++ with `-std=c++23`

## Layout

```
Source/
  Main.cpp
  Core/
    Server/              main server class
    SignalHandler/       graceful shutdown
    Services/            BaseService, CommunicationService, LogService,
                         ServiceConfig, ServiceRegistry
    Types/               TcpClient, LogEntry
    Utilities/           SocketUtility, LogFileUtility, LogConsoleUtility
    Helpers/             DateTimeHelper, FileHelper
.vscode/                 tasks.json contains the full build command
```

## Build

The build is driven by VS Code tasks in `.vscode/tasks.json`. Open the folder in VS Code and run the `Build C++ (Debug)` or `Build C++ (Release)` task, which invokes g++ directly and writes the executable to `Build/Debug/` or `Build/Release/`.
