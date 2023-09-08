# CutterAIReverse
Supplement Reverse Engineering attempts with Cutter.re using AI!

## What Does This Tool Do?
Cutter.re is a modern and advanced Software Reverse Engineering tool which has established itself as an Open Source competitor to tools like NSA Ghidra or other proprietary competitors on the market. This *intended goal* of this project is to develop a plugin for Cutter that integrates modern AI functionality into the software, allowing Reverse Engineers to receive suggestions and "hints" from the AI on places to look within a disassembled or decompiled binary program for important elements, such as:
- Identifying standard library functions belonging to specific operating systems and suggesting function and variable names in lieu of this discovery.
- Identifying the entry and main function to a program and labelling it as such.
- Identifying other functions in the disassembled code, and using the already decompiled code for reference to suggest what each function's role is
- Providing an AI chat interface for further in-depth technical questions.

**NOTE: THIS IS A WORK IN PROGRESS, AND THE DEVELOPERS ARE NOT RESPONSIBLE FOR USERS DAMAGING THEIR SYSTEM WHILE USING ALPHA/BETA SOFTWARE!**

## How Does This Plugin Work?
This plugin is just a simple C++ plugin for the Cutter.RE API which simply allows us to provide the necessary data from Cutter to the AI Software, and the response gets fed back to the plugin. The plugin then instructs Cutter to display the outputted results via the UI (which incidentally is how we gather user input).

```
┌───────────────────┐         ┌──────────────────┐          ┌──────────────────┐
│                   │         │                  │          │                  │
│                   │         │                  │          │                  │
│                   │         │                  │          │                  │
│                   ├────────►│                  ├─────────►│                  │
│     CUTTER API    │         │    CUTTER AI     │          │    AI SOFTWARE   │
│                   │         │                  │          │                  │
│                   │◄────────┤                  │◄─────────┤                  │
│                   │         │                  │          │                  │
│                   │         │                  │          │                  │
│                   │         │                  │          │                  │
└───────────────────┘         └──────────────────┘          └──────────────────┘
```

