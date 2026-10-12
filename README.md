# create-polytoria-ts

Creates a **polytoria-ts** and **pojo** compatible project.

## Usage

```sh
mkdir my_game
cd my_game
npm init polytoria-ts
```

Make your changes (or don't), then build it:
```sh
npm install
npm run build
```
This will create an `out/` directory with the corresponding luau files.

### Game sync
[Pojo](https://www.npmjs.com/package/@polytoria-ts/pojo) is pulled by default. Pojo watches the `out/` directory for changes and updates `game/scripts` relying on `default.project.json` to map each luau file in `out/` to an instance in your game. Pojo needs an addon in your Polytoria game to work. So,

1. Open Polytoria's Creator. Navigate to your project (`my_game/game`), open `main.poly`
2. Find a `pojo` script in your explorer. That is an addon script. It is under to `World`.
3. Right click the `pojo` script, select "add as addon". Accept any permissions it may demand.
4. In the very top menu bar of Polytoria Creator, navigate to "Tools" -> "Addons" -> "Pojo"
5. Pick "Auto sync".
6. Back in your project/terminal, run `npm run dev`. This will start up a compiler in watch mode & Pojo's daemon.
7. Observe your terminal's output for what work is scheduled. See your Polytoria Creator's console for what's being done. Verify your scripts appear where they should be.
8. Edit, create, rinse and repeat.

Important: `game` is a hardcoded directory value in Pojo. Until this changes, your Polytoria project must live inside of there.

### Why does this suck?
No halbas JavaScript. Submit pull requests if you have ideas, thank you.
