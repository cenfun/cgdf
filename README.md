# CGDF- Common Grid Data Format
> Definition of common grid data format.


## Basic Data Structure
```js
{
    options: Object, //define grid level options
    columns: Array, //define column list and header
    rows: Array //define row list
}
```

## Simple Data (String/Array - Cell value located by index)
```js
{
    options: {},
    columns: ["Column 1", "Column 2", "Column 3"], 
    rows: [
        ["Cell 11", "Cell 12", "Cell 13"],
        ["Cell 21", "Cell 22", "Cell 23"],
        ["Cell 31", "Cell 32", "Cell 33"]
    ] 
}
```
### Simple Data with Extensible Column
```js
{
    columns: ["Column 1", {
        name: "Column 2",
        align: "center"
    }, {
        name: "Column 3",
        align: "right"
    }], 
    rows: [
        ["Cell 11", "Cell 12", "Cell 13"],
        ["Cell 21", "Cell 22", "Cell 23"],
        ["Cell 31", "Cell 32", "Cell 33"]
    ] 
}
```

## Extensible Data (Object/Array - Cell value located by id)
```js
{
    options: {},
    columns: [{
        id: "c1",
        name: "Column 1",
        otherKey: "Some Value"
    }, {
        id: "c2",
        name: "Column 2"
    }, {
        id: "c3",
        name: "Column 3"
    }], 
    rows: [
        {
            c1: "Cell 11",
            c2: "Cell 12",
            c3: "Cell 13",
            otherKey: "Some Value"
        },
        {
            c1: "Cell 21",
            c2: "Cell 22",
            c3: "Cell 23"
        },
        {
            c1: "Cell 31",
            c2: "Cell 32",
            c3: "Cell 33"
        }
    ] 
}
```

## Extensible Data with Tree Structure (subs)
```js
{
    columns: [{
        id: "c1",
        name: "Column 1"
    }, {
        id: "g1",
        name: "Group 1",
        subs: [{
            id: "c2",
            name: "Column 2",
        }, {
            id: "c3",
            name: "Column 3"
        }]
    }], 
    rows: [
        {
            c1: "Cell 11",
            c2: "Cell 12",
            c3: "Cell 13",
            subs: [{
                c1: "Sub 11-1",
                c2: "Sub 11-2",
                c3: "Sub 11-3"
            }]
        },
        {
            c1: "Cell 21",
            c2: "Cell 22",
            c3: "Cell 23"
        },
        {
            c1: "Cell 31",
            c2: "Cell 32",
            c3: "Cell 33"
        }
    ] 
}
```

## CGDF Implementations

- [markdown-grid](https://github.com/cenfun/markdown-grid) 
- [console-grid](https://github.com/cenfun/console-grid)