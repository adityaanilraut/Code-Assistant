# Code Assistant

A comprehensive AI coding assistant with rich terminal interface, advanced tool system, conversation management

## ✨ Features

🤖 **Enhanced AI Integration**: OpenAI GPT-4 with streaming, token tracking, and model switching  
🎨 **Rich Terminal Interface**: Syntax highlighting, status line, progress bars, and beautiful output  
🛠️ **Comprehensive Tools**: Python execution, file operations, shell commands, web fetching, git integration  
💬 **Conversation Management**: Session persistence, history, export to multiple formats  
⚙️ **Extensible Hooks**: Pre/post execution hooks, webhooks, custom Python scripts  
📊 **Performance Monitoring**: Real-time status, token usage tracking, execution timing  
🎯 **Slash Commands**: Rich command system for configuration, session management, and control  
⌨️ **Keyboard Shortcuts**: Ctrl+C/Ctrl+D handling, enhanced prompts, multi-line support  

## 🚀 Quick Start

### Installation
```bash
# Clone and install dependencies
git clone <repository-url>
cd devtool
pip install -r requirements.txt

# Set up environment
cp .env.example .env
# Edit .env and add your OpenAI API key
```

### Basic Usage
```bash
# Interactive mode with rich interface
python main.py

# Single command mode
python main.py --command "Create a Python function to calculate fibonacci numbers"

# Debug mode with detailed errors
python main.py --debug

# Override configuration
python main.py --model gpt-3.5-turbo --no-status
```

## 🎯 Core Tools

### Development Tools
- **🐍 Python Execution**: Run code with syntax highlighting and timing
- **📁 File Operations**: Read, write, edit files with backup support
- **🔍 Code Search**: Advanced grep functionality across projects
- **📝 Smart Editing**: Text replacement with context validation
- **📊 Directory Listing**: Enhanced file browser with metadata

### System Integration
- **🔧 Shell Commands**: Execute system commands with rich output
- **📦 Git Integration**: Status checking, branch information
- **🌐 Web Fetching**: Download and extract web content
- **📋 Todo Management**: Track tasks with status indicators

## 💬 Conversation Features

### Session Management
- **Auto-Save**: Conversations automatically saved with metadata
- **History**: Browse and replay previous conversations  
- **Export**: Multiple formats (Markdown, HTML, Text, JSON)
- **Search**: Find conversations by content or metadata

### Slash Commands
```bash
/help                    # Show comprehensive help
/model gpt-4            # Switch AI models use gpt-5-nano
/save my_session        # Save current conversation
/load my_session.json   # Load previous conversation
/export markdown        # Export as markdown
/status                 # Show system status
/history 10             # Show recent messages
/sessions               # List all saved sessions
/config                 # Show configuration
/stats                  # Usage statistics
/clear                  # Clear conversation
```

## ⚙️ Configuration

### YAML Configuration (`config.yaml`)
```yaml
# LLM Settings
llm:
  default_model: gpt-4
  temperature: 0.7
  max_tokens: 4000
  stream: true

# Interface Settings  
interface:
  theme: monokai
  show_status_line: true
  vim_mode: false
  auto_save_conversations: true

# Tool Settings
tools:
  python_executable: python3
  max_execution_time: 30
  syntax_highlighting: true
  show_tool_output: true

# File Operations
files:
  create_backups: true
  max_file_size: 10MB
  allowed_extensions: [.py, .js, .ts, .md, .txt, .json, ...]
```

### Environment Variables
```bash
export OPENAI_API_KEY="your_openai_key_here"
export DEFAULT_MODEL="gpt-4"
export MAX_EXECUTION_TIME="60"
export PYTHON_EXECUTABLE="python3"
```

## 🔌 Hooks System

### Extensibility
Create custom hooks for various events:

```yaml
hooks:
  pre_tool_execution:
    - ./hooks/validate_commands.py      # Python script
    - "echo 'Executing {tool_name}'"    # Shell command
  post_tool_execution:
    - ./hooks/log_usage.py              # Python script
    - "https://api.example.com/webhook" # HTTP webhook
```

### Hook Types
- **Python Files**: Custom modules with `execute_hook(context)` function
- **Shell Commands**: Scripts with context variable substitution  
- **Webhooks**: HTTP POST endpoints for external integrations

## 📊 Rich Interface

### Status Line
Real-time display showing:
- 🤖 Current model and connection status
- 🎯 Token usage and execution count
- ⏱️ Session duration and timing
- ❌ Error indicators and health status

### Enhanced Output
- **Syntax Highlighting**: Code displayed with proper language highlighting
- **Progress Indicators**: Spinners and progress bars for long operations
- **Rich Tables**: Formatted output for lists and data
- **Panels**: Bordered content areas for better organization
- **Color Themes**: Customizable color schemes

## 📁 File Structure

```
├── main.py                 # Rich CLI interface
├── config.yaml             # Main configuration
├── requirements.txt        # Dependencies
├── system-prompt.txt       # AI behavior prompt
├── .env                    # Environment variables
├── src/
│   ├── assistant.py        # Enhanced assistant core
│   ├── llm_providers.py    # OpenAI integration
│   ├── tools.py            # Comprehensive tool system
│   ├── conversation.py     # Session management
│   ├── hooks.py            # Extensibility system
│   └── config.py           # Configuration management
├── conversations/          # Saved sessions (auto-created)
└── hooks/                  # Custom hook files (optional)
```

## 🎬 Usage Examples

### Interactive Coding Session
```bash
$ python main.py
🤖 Code Assistant
Enhanced AI assistant with comprehensive tool support

You: Create a Python function to calculate fibonacci numbers
