# Electron History State Bug

When you add state to `window.history`, e.g. `window.history.replaceState({x:1}, undefined, window.location.href)`, then you should expect to see that state after you refresh `console.log(window.history.state)`.

If you open `index.html` inside chrome and press the next button a few times, you'll see the history state logged to the console. When you refresh, you should see the state continue counting where it left off. However if you use this file in the electron app using `npm start`, you'll notice that refreshing the page clears the history state.