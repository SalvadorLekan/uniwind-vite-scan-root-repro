# Uniwind on Vite: classes are detected outside the `cssEntryFile` directory

Based on [`apps/vite-example`](https://github.com/uni-stack/uniwind/tree/main/apps/vite-example). The only addition is `docs/notes.md`, which is outside `src/` (the directory of `cssEntryFile: './src/App.css'`) and is not imported anywhere:

```md
Example usage: `<View className="bg-red-500 animate-spin" />`
```

## Steps

```sh
bun install
bun run build
grep -oE '\.(bg-red-500|animate-spin)' dist/assets/*.css
```

## Result

```
.animate-spin
.bg-red-500
```

Neither class is used in `src/`.
