# React-Dropzone---for-FILE-UPLOADS
This is a reference doc regarding how to use  -> Dropzone to upload files    


Dropzone is a React component that allows users to upload files by dragging and dropping them onto a designated area.


Here is an example on how to use dropzone in react to upload files -

import React, { Component } from 'react';
import Dropzone from 'react-dropzone';

class App extends Component {
  state = {
    uploadedFiles: []
  };

  handleDrop = (files) => {
    this.setState({
      uploadedFiles: files
    });
  };

  render() {
    return (
      <div>
        <Dropzone onDrop={this.handleDrop}>
          <h3>Drop files here</h3>
        </Dropzone>
        <ul>
          {this.state.uploadedFiles.map((file, index) => (
            <li key={index}>{file.name}</li>
          ))}
        </ul>
      </div>
    );
  }
}

export default App;



Explanation :- 

After importing dropzone 

The App class extends the Component class from React. The state variable uploadedFiles is defined to store the uploaded files.

The handleDrop function is called when the user drops a file onto the Dropzone component. The files argument to the handleDrop function is an array of the files that were dropped. The handleDrop function updates the uploadedFiles state variable with the files array.

The render method renders the Dropzone component and a list of the uploaded files. The Dropzone component is rendered with the onDrop prop set to the handleDrop function. The list of the uploaded files is rendered using the map method to iterate over the uploadedFiles state variable and render a li element for each file. The key prop is set to the index of the file in the uploadedFiles state variable to ensure that the list of files is rendered in the correct order.

At last we export or App
