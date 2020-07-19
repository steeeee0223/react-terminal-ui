![CI](https://github.com/jonmbake/react-terminal-ui/workflows/CI/badge.svg) [![Jest Code Coverage Report](jest-code-coverage-report.svg)](https://jonmbake.github.io/react-terminal-ui/coverage/) ![Types TypeScript](types-type-script.svg)

# React Terminal UI

A react terminal componement with support for light/dark modes. Styling cortesy of [termynal.js](https://github.com/ines/termynal).

Check out the **[Demo](https://jonmbake.github.io/react-terminal-ui/demo/)** :heart_eyes:

![React Terminal UI Demo Dark](https://github.com/jonmbake/screenshots/raw/master/react-terminal-ui/react-terminal-ui-demo-dark.png)

![React Terminal UI Demo Light](https://github.com/jonmbake/screenshots/raw/master/react-terminal-ui/react-terminal-ui-demo-light.png)

## Installation

```
npm install --save react-terminal-ui
```

## Usage

The _React Terminal UI_ componement is a "dumb component"-- whatever props you pass in, it will render. You usually want to have
a smart, controller component that controls terminal state. For example:

```
import React from 'react';
import Terminal, { ColorMode, LineType } from 'react-terminal-ui';

const TerminalController = (props = {}) => {
  // Should be state on this component
  const terminalLineData = [{type: LineType.Output, value: 'Welcome to the React Terminal UI Demo!'}];
  // Terminal has 100% width by default so it should usually be wrapped in a container div
  return (
    <div className="container">
      <Terminal name='React Terminal Usage Example' colorMode={ ColorMode.Light }  lineData={ terminalLineData } onInput={ terminalInput => console.log(`Terminal input received: '${ terminalInput }'`) }/>
    </div>
  )
});
```

## Component Props

| Name          | Description |
| ------------- | ------------- |
| name          | Name of the terminal. Displays at the top of the rendered component. In the demo, the name is set to _React Terminal UI_ |
| colorMode     | Terminal color mode-- either Light or Dark.  |
| lineData      | Terminal line data to render. Line data with `LineType.Input` will display with a prompt before the line. |
| onInput       | A callback function that is invoked when a user presses enter on the prompt. The function is passed the current prompt input. |
| prompt        | The prompt character. Default to '$' |

## License

[MIT](https://opensource.org/licenses/MIT)

Terminal.js is also licensed under MIT, Copyright (C) 2017 Ines Montani.
