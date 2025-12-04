# DevPulse

Real-time code performance profiler with flame graph visualization.

## Overview

DevPulse is a browser-based profiler that instruments JavaScript and TypeScript code in real-time. It provides interactive flame graphs, memory leak detection, and performance regression alerts.

## Features

- **Live Profiling**: Real-time function execution tracking
- **Flame Graphs**: Interactive visualization of call stacks
- **Memory Analysis**: Leak detection and heap snapshots
- **Regression Alerts**: Automatic performance degradation warnings
- **Source Mapping**: Connect profiles to original source code
- **Export/Import**: Share and compare profile data

## Technical Stack

- **TypeScript** - Type-safe instrumentation
- **Chrome DevTools Protocol** - Low-level browser profiling
- **D3.js** - Flame graph visualization
- **React** - Dashboard UI
- **Node.js** - Backend analysis service

## Profiler Metrics

- Function execution time
- Call frequency
- Memory allocation
- GC pressure
- Event loop lag
- Network timing

## Flame Graph Reading

\`\`\`
┌────────────────────────────────────────────┐
│                  main()                     │ <- Entry point
├──────────────────┬─────────────────────────┤
│    fetchData()   │     processData()       │ <- Called by main
├────────┬─────────┼──────────┬──────────────┤
│ parse  │ decode  │ transform│   render     │ <- Sub-calls
└────────┴─────────┴──────────┴──────────────┘

Width = Time spent in function + children
Color = Category (network/compute/render)
\`\`\`

## Usage

\`\`\`javascript
import { DevPulse } from 'devpulse';

const profiler = new DevPulse();
profiler.start();

// Your code here

const report = profiler.stop();
profiler.visualize(report);
\`\`\`

## Demo

View the live demo at: https://danielminton.github.io/DevPulse/

## Author

Daniel Minton