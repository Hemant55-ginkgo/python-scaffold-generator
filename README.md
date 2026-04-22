# 🐍 Python Scaffold Generator

An **offline, LLM-free** Python code skeleton builder. Open `python_scaffold_generator.html` in any browser — no server, no internet, no dependencies.

## What it does

Type a class/app name, pick a category and template, and get a ready-to-edit Python skeleton in seconds. Every template has `# TODO` markers showing exactly where to add your logic.

## Categories & Templates

### 🟢 Backend
| Template | Deps |
|---|---|
| Flask REST API | `flask` |
| FastAPI App | `fastapi uvicorn pydantic` |
| Service Class | stdlib |
| CLI Tool | stdlib |

### 🔵 Frontend / UI
| Template | Deps |
|---|---|
| Tkinter Desktop App | stdlib |
| Streamlit Dashboard | `streamlit pandas` |
| Gradio Interface | `gradio` |
| Pygame Window | `pygame` |

### 🟠 Database
| Template | Deps |
|---|---|
| SQLAlchemy ORM | `sqlalchemy` |
| Alembic Migration | `alembic sqlalchemy` |
| Pydantic Schema | `pydantic` |
| Redis Cache Layer | `redis` |

### 🩷 JSON & Schema
| Template | Deps |
|---|---|
| JSON Validator | `jsonschema` |
| JSON Transformer | stdlib |
| JSON File Store | stdlib |

### 🟣 API Modelling
| Template | Deps |
|---|---|
| OpenAPI Spec Builder | `pyyaml` |
| API Client | `requests` |
| Mock API Server | `flask` |
| Webhook Handler | `flask` |

### 🌿 AI Tools *(LLM as replaceable brain)*
| Template | Deps |
|---|---|
| LLM Router | `requests` |
| Prompt Builder | stdlib |
| Agent Loop | `requests` |
| Vector Store | `numpy` |
| RAG Pipeline | `requests numpy` |

### ⚙️ Utilities
| Template | Deps |
|---|---|
| File Processor | stdlib |
| Task Scheduler | stdlib |
| Config Loader | stdlib |

## Usage

1. Open `python_scaffold_generator.html` in your browser
2. Click a category in the left sidebar
3. Type your class/app name in the top-right input
4. Click a template card
5. Hit **Copy** and paste into your editor

## Philosophy: AI as a replaceable brain

The AI Tools category is designed around the principle that your application logic should be **LLM-agnostic**. The `LLM Router` template shows this clearly — one `chat()` function, controlled by a single env variable:

```bash
LLM_PROVIDER=anthropic  # use Claude
LLM_PROVIDER=openai     # use GPT
LLM_PROVIDER=ollama     # use local Llama (free, offline)
```

Your RAG pipeline, agent loop, and prompt builder don't change at all — only the brain swaps.

## No install required

The HTML file is fully self-contained. Just open it.

```bash
open python_scaffold_generator.html        # macOS
xdg-open python_scaffold_generator.html   # Linux
start python_scaffold_generator.html       # Windows
```

## Contributing

To add a new template, add an entry to the `TEMPLATES` object in the `<script>` section of the HTML file:

```javascript
{
  id: 'my_template',
  icon: '🔧',
  name: 'My Template',
  deps: 'some-lib',   // or 'stdlib'
  code: (n) => `# your Python code here with ${n} as the class name`
}
```

## License

MIT
