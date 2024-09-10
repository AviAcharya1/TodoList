# SvelteKit TodoList App


A responsive and modern TodoList application built with SvelteKit, TailwindCSS, and Iconify.

## Features

- Add, toggle, and delete todos
- Responsive design for various device sizes
- Local storage persistence
- Clean and intuitive user interface
- Iconify integration for scalable icons

## Prerequisites

Before you begin, ensure you have the following installed:
- [Node.js](https://nodejs.org/) (version 14 or later recommended)
- npm (comes with Node.js)

## Installation

1. Clone the repository:
   ```
   git clone https://github.com/yourusername/sveltekit-todolist.git
   cd sveltekit-todolist
   ```

2. Install the dependencies:
   ```
   npm install
   ```

## Development

To start the development server:

```
npm run dev
```

This will start the app in development mode. Open [http://localhost:5173](http://localhost:5173) to view it in your browser.

## Building for Production

To create a production build:

```
npm run build
```

To preview the production build:

```
npm run preview
```

## Project Structure

```
todo-app/
│
├── src/
│   ├── lib/
│   │   └── components/
│   │       └── TodoItem.svelte
│   │
│   ├── routes/
│   │   ├── +layout.svelte
│   │   └── +page.svelte
│   │
│   └── app.css
│
├── static/
├── tests/
├── .gitignore
├── package.json
├── postcss.config.js
├── svelte.config.js
├── tailwind.config.js
└── vite.config.js
```

## Technologies Used

- [SvelteKit](https://kit.svelte.dev/): The fastest way to build Svelte apps
- [TailwindCSS](https://tailwindcss.com/): A utility-first CSS framework
- [Iconify](https://iconify.design/): Unified icons for popular icon sets

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the project
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License

This project is open source and available under the [MIT License](LICENSE).

Project Link: (https://todo-list-five-virid.vercel.app/)
