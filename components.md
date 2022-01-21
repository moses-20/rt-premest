1. class component

``` js
import React from 'react';

class MyApp extends React.Component {
    render(){
        return (
            <div>
                <h1> Hello React! </h1>
            </div>
        );
    }
}

export default MyApp;
```

2. function component

``` js
import React from 'react';

function MyApp(){
    return (
        <div>
            <h1> Hello React Component! </h1>
        </div>
    );
}

export default MyApp;
```

3. nesting components

``` js
import React from 'react';
function MyComp(){
    return <h1> Moses Gameli </h1>;
}

function MyApp(){
    return (
        <div>
            <MyComp />
        </div>
    )
}
```



4. higher order components

``` js
import React from 'react';

function withName(Comp){
    function AddName(){
        const name = 'Moses Gameli';

        return (
            <div>
                {name}
                <Comp />
            </div>
        );
    }

    return AddName;
}

export default AddName;
```

5. rules of components
   - [ ] return only one element
   - [ ] render js variables in braces
   - [ ] access children from props


6. styling components

``` js
// inline styling
function MyApp(){
    return (
        <div style={{
            textAlign='center'
        }}>
            <h1> Moses Gameli </h1>
        </div>
    )
}
```

``` css
/* class names */
.container {
    text-align: 'center';
}
```
``` js
import './style.css';

function MyApp(){
    return (
        <div className="container">
            <h1> Gbemu Terra </h1>
        </div>
    )
}
```