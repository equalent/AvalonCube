# AvalonCube

This is a proof of concept for 2 ideas. Together, they can form a foundation of a game engine world editor where the engine runtime is native but the editor is implemented in C#.

## RPC

Using CppAst.NET, a C# tool parses C++ header file and extracts interface definition. Then it generates:
- C++ metadata and serialisation code
- C# binding

A custom RPC protocol is then used to communicate calls and results from C# client to C++ server.

## Texture sharing

The native runtime uses D3D12 to render a cube to an offscreen texture. A cross-process handle to this texture is communicated over RPC. Now the .NET app must render the texture inside an Avalonia control.
