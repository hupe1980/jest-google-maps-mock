# jest-google-maps-mock

> Jest mock for google maps

## Installation

```sh
// with npm
npm install -D jest-google-maps-mock

// with yarn
yarn add -D jest-google-maps-mock
```

## How to use

```js
import createGoogleMapsMock from 'jest-google-maps-mock';

describe('createGoogleMapsMock', () => {
  let googleMaps;

  beforeEach(() => {
    googleMaps = createGoogleMapsMock();
  });

  it('should create a map mock', () => {
    const mapDiv = document.createElement('div');
    new googleMaps.Map(mapDiv);

    expect(googleMaps.Map).toHaveBeenCalledTimes(1);
    expect(googleMaps.Map.mock.instances.length).toBe(1);
    expect(googleMaps.Map).toHaveBeenLastCalledWith(mapDiv);
  });
});
```

## License

[MIT](LICENSE)
