# MemoChat
[中文版本](README.md)

MemoChat is an intelligent workstation integrating document and chat functions. It allows users to freely adjust and set roles in conversations, supports multi-window and real-time synchronization, and can directly interact with local files.

## Features

- **Free Context Management**: Experience unrestricted conversation management. MemoChat allows you to freely adjust and set roles in conversations, breaking the traditional turn-based interaction mode.
- **Multi-window and Real-time Sync**: Handle different tasks in multiple windows simultaneously. MemoChat ensures real-time synchronization of all window contents, avoiding information inconsistency.
- **Local File Interaction Support**: Interact with local files directly in MemoChat without switching applications.
- **Markdown Preview Support**: In MemoChat, you can directly preview Markdown documents, including complex mermaid and UML diagrams.

## Getting Started with MemoChat

### Multi-window
- **Description**: MemoChat supports opening multiple windows simultaneously. Use `Cmd + N` to open a new window. All opened windows are floating on top and may block other applications. Use `option` `z` to toggle pin/unpin all windows.

### Triggering the Large Model
- **Shortcut**: `Cmd` `=`
- **Description**: After entering content in the editor, press `Cmd` `=` to trigger the large model for content generation.

### Interrupting the Large Model
- **Description**: During the generation process of the large model, press any key to interrupt the generation, or click anywhere in the edit box with the mouse to interrupt the large model.

### Mention Quick Operations
- **Description**: Use `@` at the beginning of a line to invoke intent selection;
- **system, user, assistant**: Used to mark conversation roles.
- **file**: Used to insert file content. After entering `file `, you can select a local file.
- **recent**: After entering `recent `, you can quickly access recently used files.
- **tabs**: After entering `tabs `, you can access currently open tabs.
- **clipboard**: After entering `clipboard `, you can access clipboard history.
- **temp**: User's temporary independent conversation, not using the context in the edit box;
- **blockmatcher**: Used to control the code block matching of the large model.
- **vscode**: After entering `vscode `, you can access recently opened files in VSCode.
- **diffchecker**: Used to check code/text differences.
- **terminal**: After entering `terminal `, you can get the current working directory (pwd) information of the terminal;
- **workingDir**: After entering `workingDir `, you can select files in the current working directory (pwd) to insert into the conversation.

### Local File Interaction
- **Drag into VSCode Tab File**: Supports dragging files into the editor to insert them into the conversation.
- **SEARCH/REPLACE block**: The large model edits the specified file, matches according to the SEARCH block, and replaces using the REPLACE block.

<img src="images/Local_File_Interaction.png" alt="Local File Interaction" width="600"/>

### Local Command Line Tool Interaction
- **Terminal**: Execute command line operations through the built-in terminal. Use `Cmd + J` to toggle show/hide terminal.

### Markdown Preview
- **Shortcut**: `Cmd + P`
- **Description**: Supports real-time preview of Markdown content, including Latex mathematical formulas, Mermaid flowcharts, and PlantUML diagrams.

### Ghost Text
- **Description**: After entering content in the editor, the system automatically generates suggested text, press `Tab` to accept the suggestion. Ghost text will start requesting after staying at the cursor position for 0.5 seconds.

### Custom Model
- **Description**: Supports any interface that conforms to the OpenAI request format.
- **Configuration Method**: Click the configuration button on the bottom status bar to open the `models-config.json` file for self-configuration.
- Temporarily built-in deepseek model, this key is currently mine, and I will charge 10 RMB (5 million tokens) per month, use it until it runs out. If there are no other options, it is recommended to use this model.

### Custom Agent
- **Description**: Use `@` in a non-line-start position to invoke a custom Agent. The content of the selected agent will be passed to the model as a system prompt.
- By setting the file name of the conversation file to `agent_{agentname}.md`, you can add an agent and use it with @agentname.
- For example, the coder agent below is actually built-in with a conversation file named "agent_coder.md", which can be viewed by triggering the conversation history box search with `Cmd` `k`.
- **@coder**: Code generation assistant.
- **@jarvis**: Intelligent assistant.
- **@html**: HTML generation assistant.
- **@commander**: Command execution assistant.
- **@docer**: Document generation assistant.
- **@thinking_process**: Thinking process analysis assistant.

### Toolbar Popup for Selected Content
- **comment**: Use the selected content and the above text as context for conversation.
- **chat**: Use only the selected content as context for conversation.
- **load_file**: The selected content is a local file address, load the file into the conversation.
- **load_url**: The selected content is a URL, load the webpage content into the conversation.
- **exec**: The selected content is a terminal command, open the terminal to execute the command.
	- If you want the result of the execution to be automatically copied to the clipboard, you can add `| pbcopy` to the end of the command, such as `cat hello.txt | pbcopy`, for easy pasting into the conversation later.

### Shortcut Summary
- **option + z**: Toggle pin/unpin all windows.
- **Cmd + =**: Trigger the large model.
- **Cmd + Shift + =**: Retrieve related documents and then trigger the large model.
- **Cmd + J**: Toggle terminal.
- **Cmd + T**: Open a new tab.
- **Cmd + W**: Close the current tab.
- **Cmd + P**: Toggle Markdown preview.
- **Cmd + L**: Adjust window size, small, medium, large.
- **Cmd + N**: Open a new window.
- **Cmd + H**: Show history conversation records.
- **Cmd + S**: Save the content of the current tab.