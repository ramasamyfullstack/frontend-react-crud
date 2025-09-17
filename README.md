### 1. create github repository and setting -> pages -> root to main and make url
### 2. add the url in package.json in "homepage" like below

### 3. npm install gh-pages --save-dev

## 4. package.json  and check

    "predeploy": "npm run build",
    "deploy": "gh-pages -d build"

```json
{
  "name": "frontend",
  "version": "0.1.0",
  "private": true,
  "homepage": "https://ramasamyfullstack.github.io/frontend-react-crud",
  "dependencies": {
    "@testing-library/dom": "^10.4.1",
    "@testing-library/jest-dom": "^6.8.0",
    "@testing-library/react": "^16.3.0",
    "@testing-library/user-event": "^13.5.0",
    "axios": "^1.11.0",
    "bootstrap": "^5.3.7",
    "react": "^19.1.1",
    "react-dom": "^19.1.1",
    "react-router-dom": "^7.8.1",
    "react-scripts": "5.0.1",
    "web-vitals": "^2.1.4"
  },
  "scripts": {
    "start": "react-scripts start",
    "build": "react-scripts build",
    "test": "react-scripts test",
    "eject": "react-scripts eject",
    "predeploy": "npm run build",
    "deploy": "gh-pages -d build"
  },
  "eslintConfig": {
    "extends": [
      "react-app",
      "react-app/jest"
    ]
  },
  "browserslist": {
    "production": [
      ">0.2%",
      "not dead",
      "not op_mini all"
    ],
    "development": [
      "last 1 chrome version",
      "last 1 firefox version",
      "last 1 safari version"
    ]
  },
  "devDependencies": {
    "gh-pages": "^6.3.0"
  }
}
```

### in App.js gibe basename="/repository-name" in BrouserRouter like below

```
import './App.css';
import Layout from './Layout';
import { BrowserRouter, Routes, Route } from 'react-router-dom';
import TraineeList from './Components/TraineeList';
import TraineeAdd from './Components/TraineeAdd';
import TraineeUpdate from './Components/TraineeUpdate';


function App() {
  return (
    <div className="App">

      <BrowserRouter basename="/frontend-react-crud">
        <Layout />
        <Routes>
          <Route exact path='/' element={<TraineeList />}></Route>
          <Route path='/add' element={<TraineeAdd />}></Route>         
          <Route path='/update' element={<TraineeUpdate />}></Route>
        </Routes>

      </BrowserRouter>

    </div>
  );
}

export default App;
```

### 5. npm run build

### 6. upload all the file from build folder into the github



