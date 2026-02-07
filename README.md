# Todo App

A modern, minimal todo application built with **Vue 3**, **TypeScript**, and the **Composition API**. Perfect for learning and practicing modern Vue.js development patterns.

## ✨ Features

- ✅ **Add, edit, and delete tasks** - Full task management capabilities
- 🎯 **Filter tasks** - View all tasks, only completed, or only pending tasks
- 📊 **Progress tracking** - See how many tasks you've completed
- 🎨 **Clean UI** - Built with Pico CSS for a minimalist, elegant design
- ⚡ **Fast development** - Powered by Vite for instant hot module reloading
- 📘 **TypeScript** - Full type safety and excellent IDE support
- 🧩 **Composition API** - Modern Vue 3 patterns with `<script setup>`

## 🛠️ Tech Stack

- **Framework:** Vue 3
- **Language:** TypeScript
- **Build Tool:** Vite
- **Package Manager:** Bun
- **CSS Framework:** Pico CSS
- **State Management:** Composition API with `ref` and `computed`

## 📋 Project Structure

```
src/
├── components/
│   ├── FilterButton.vue    # Filter toggle buttons (all/todo/done)
│   ├── TaskForm.vue        # Form to add new tasks
│   └── TaskList.vue        # Task list display component
├── App.vue                 # Main application component
├── main.ts                 # Application entry point
├── style.css               # Global styles
└── types.ts                # TypeScript type definitions
```

## 🚀 Getting Started

### Prerequisites

- [Bun](https://bun.sh/) installed on your system
- Node.js 18+ (Bun includes this)

### Installation

1. Clone the repository:
```bash
git clone <your-repo-url>
cd todo-app
```

2. Install dependencies with Bun:
```bash
bun install
```

### Development

Start the development server with hot module reloading:

```bash
bun run dev
```

The app will be available at `http://localhost:5173`

### Building for Production

Build the app for production:

```bash
bun run build
```

This runs TypeScript compilation checks and creates an optimized build in the `dist/` directory.

### Preview Production Build

Preview your production build locally:

```bash
bun run preview
```

## 📚 Learning Resources

This project is great for learning:

- **Vue 3 Composition API** - See how to manage component state with `ref` and `computed`
- **TypeScript with Vue** - Full type safety in your components
- **Single File Components** - Modern `<script setup>` syntax
- **Vite & Bun** - Experience modern JavaScript tooling

Useful references:
- [Vue 3 Documentation](https://vuejs.org/)
- [Vue 3 TypeScript Guide](https://vuejs.org/guide/typescript/overview.html)
- [Composition API](https://vuejs.org/guide/extras/composition-api-faq.html)
- [Pico CSS](https://picocss.com/)
- [Vite Documentation](https://vitejs.dev/)

## 🎯 Usage

1. **Add a Task:** Type in the input field and click "Add Task"
2. **Mark Complete:** Click the checkbox next to a task to mark it done/undone
3. **Delete Task:** Click the delete button to remove a task
4. **Filter Tasks:** Use the filter buttons to view all, pending, or completed tasks

## 🔧 Available Scripts

| Script | Description |
|--------|-------------|
| `bun run dev` | Start development server with HMR |
| `bun run build` | Build for production with type checking |
| `bun run preview` | Preview the production build |

## 🤝 Contributing

Contributions are welcome! Feel free to:
- Report bugs
- Suggest features
- Submit pull requests

## 📄 License

This project is open source and available under the MIT License.

## 🎓 Notes

This project demonstrates best practices for:
- Vue 3 Composition API usage
- TypeScript integration with Vue
- Component composition and reusability
- Modern build tooling with Vite
- Minimal, semantic HTML with Pico CSS
