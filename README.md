Node.js Simplex
===============

![CI](https://github.com/renoki-games/node-simplex/workflows/CI/badge.svg?branch=master)
[![codecov](https://codecov.io/gh/renoki-games/node-simplex/branch/master/graph/badge.svg)](https://codecov.io/gh/renoki-games/node-simplex/branch/master)
[![StyleCI](https://github.styleci.io/repos/330025905/shield?branch=master)](https://github.styleci.io/repos/330025905)
[![Latest Stable Version](https://img.shields.io/github/package-json/v/renoki-games/node-simplex)](https://www.npmjs.com/package/@renoki-games/node-simplex)
[![Total Downloads](https://img.shields.io/npm/dt/@renoki-games/node-simplex)](https://www.npmjs.com/package/@renoki-games/node-simplex)
[![License](https://img.shields.io/npm/l/@renoki-games/node-simplex)](https://www.npmjs.com/package/@renoki-games/node-simplex)

Maintained fork of fast-simplex-noise that works in TS environments.

Originally forked from unmaintained [joshforisha/fast-simplex-noise-js](https://github.com/joshforisha/fast-simplex-noise-js).

## 🤝 Supporting

Renoki Co. & Renoki Games on GitHub aims on bringing a lot of open source projects and helpful projects to the world. Developing and maintaining projects everyday is a harsh work and tho, we love it.

If you are using your application in your day-to-day job, on presentation demos, hobby projects or even school projects, spread some kind words about our work or sponsor our work. Kind words will touch our chakras and vibe, while the sponsorships will keep the open source projects alive.

[![ko-fi](https://www.ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/R6R42U8CL)

## 🚀 Installation

You can install the package via npm:

```bash
npm install @renoki-games/node-simplex
```

## 🙌 Usage

```js
import { Simplex } from '@renoki-games/node-simplex';

const noiser = new Simplex({
    frequency: 0.01,
    max: 255,
    min: 0,
    octaves: 8,
});

let grid = [];

for (let x = 0; x < 1024; x++) {
    for (let y = 0; y < 768; y++) {
        grid.push({
            x,
            y,
            noise: noiser.scaled([x, y]),
        });
    }
}
```

## API

### Constructor

#### FastSimplexNoise(options?: Options = {})

Options contains:

- `amplitude: number` – The base amplitude (default: `1.0`)
- `frequency: number` – The base frequency (default: `1.0`)
- `max: number` – The maximum scaled value to return (effective default: `1.0`)
- `min: number` – The minimum scaled value to return (effective default: `-1.0`)
- `octaves: number` – Integer; the number of octaves to sum for noise generation (default: `1`)
- `persistence: number` – The persistence of amplitude per octave (default: `0.5`)
- `random: () => number` – A function that generates random values between 0 and 1 (default: `Math.random`)

### Instance Methods

#### `cylindrical(circumference: number, coords: number[]): number`

Get a scaled noise value (using **options**) for a 2D or 3D point at `coords` on the surface of a cylinder with `circumference`.

#### `cylindrical2D(circumference: number, x: number, y: number): number`

Specific `cylindrical()` call for a 2D point at (`x`, `y`).

#### `cylindrical3D(circumference: number, x: number, y: number, z: number): number`

Specific `cylindrical()` call for a 3D point at (`x`, `y`, `z`).

#### `raw(coords: number[]): number`

Get a noise value [-1, 1] at a 2D, 3D, or 4D point at `coords`.

#### `raw2D(x: number, y: number): number`

Specific `raw()` call for a 2D point at (`x`, `y`).

#### `raw3D(x: number, y: number, z: number): number`

Specific `raw()` call for a 3D point at (`x`, `y`, `z`).

#### `raw4D(x: number, y: number, z: number, w: number): number`

Specific `raw()` call for a 4D point at (`x`, `y`, `z`, `w`).

#### `scaled(coords: number[]): number`

Get a scaled noise value (using **options**) at a 2D, 3D, or 4D point at `coords`.

#### `scaled2D(x: number, y: number): number`

Specific `scaled()` call for a 2D point at (`x`, `y`).

#### `scaled3D(x: number, y: number, z: number): number`

Specific `scaled()` call for a 3D point at (`x`, `y`, `z`).

#### `scaled4D(x: number, y: number, z: number, w: number): number`

Specific `scaled()` call for a 4D point at (`x`, `y`, `z`, `w`).

#### `spherical(circumference: number, point: number[]): number`

Get a scaled noise value (using **options**) at a 2D or 3D point at `coords` on the surface of a sphere with `circumference`.

#### `spherical2D(circumference: number, x: number, y: number): number`

Specific `spherical()` call for a 2D point at (`x`, `y`).

#### `spherical3D(circumference: number, x: number, y: number, z: number): number`

Specific `spherical()` call for a 3D point at (`x`, `y`, `z`).

## 🐛 Testing

``` bash
npm run test
```

## 🤝 Contributing

Please see [CONTRIBUTING](CONTRIBUTING.md) for details.

## 🔒  Security

If you discover any security related issues, please email alex@renoki.org instead of using the issue tracker.

## 🎉 Credits

- [Alex Renoki](https://github.com/rennokki)
- [All Contributors](../../contributors)
