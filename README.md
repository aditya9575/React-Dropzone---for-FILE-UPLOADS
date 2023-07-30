# React-Dropzone---for-FILE-UPLOADS
This is a reference doc regarding how to use  -> Dropzone to upload files    


Dropzone is a React component that allows users to upload files by dragging and dropping them onto a designated area.


Here is an example on how to use dropzone in react to upload files -

import './App.css';
import Dropzone from 'react-dropzone'


function App() {
  return (
    <div className="app">
      
      <h1>HELLO CODERS</h1>

      <Dropzone onDrop={acceptedFiles => console.log(acceptedFiles)}>
  {({getRootProps, getInputProps}) => (
    <section>
      <div {...getRootProps()}>
        <input {...getInputProps()} />
        <button>Drag 'n' drop some files here, or click to select files</button>
      </div>
    </section>
  )}
</Dropzone>

    </div>
  );
}

export default App;























//---------------------------------------------------------------------------------------------------------------------------------\\
//In Case of adding a check on file type we want to be upload we use this piece of code 

// import React, { useState } from 'react';
// import './App.css';
// import Dropzone from 'react-dropzone';

// function App() {
//   const [errorMessage, setErrorMessage] = useState('');

//   const handleDrop = (acceptedFiles) => {
//     // Filter the acceptedFiles array to only keep image file types
//     const allowedImageTypes = ['image/jpeg', 'image/png', 'image/gif'];
//     const filteredImages = acceptedFiles.filter(file =>
//       allowedImageTypes.includes(file.type)
//     );

//     // Check if any non-image files were found
//     if (filteredImages.length !== acceptedFiles.length) {
//       setErrorMessage('Only image files (JPEG, PNG, GIF) are allowed.');
//     } else {
//       // Process the filteredImages further (e.g., display them, upload them, etc.)
//       console.log(filteredImages);
//       setErrorMessage('');
//     }
//   };

//   return (
//     <div className="app">
//       <h1>HELLO CODERS</h1>

//       <Dropzone onDrop={handleDrop}>
//         {({ getRootProps, getInputProps }) => (
//           <section>
//             <div {...getRootProps()}>
//               <input {...getInputProps()} />
//               <button>Drag 'n' drop some images here, or click to select images</button>
//             </div>
//           </section>
//         )}
//       </Dropzone>
      
//       {errorMessage && <p className="error">{errorMessage}</p>}
//     </div>
//   );
// }

// export default App;


//---------------------------------------------------------------------------------------------------------------------------------\\


**********************************************************************************************************************************************
                                                             FULL EXPLANATION
1) Set up the react app and delete the unwanted folders/files 
2) run the command npm install react-dropzone
3) Now inside our app.js import dropzone -> import Dropzone from 'react-dropzone'
4) Now inside the return statement of the App function we use dropzone -> 

i.e ---> <Dropzone onDrop={acceptedFiles => console.log(acceptedFiles)}>
  {({getRootProps, getInputProps}) => (
    <section>
      <div {...getRootProps()}>
        <input {...getInputProps()} />
        <button>Drag 'n' drop some files here, or click to select files</button>
      </div>
    </section>
  )}
</Dropzone>

5) This is how we use dropzone to upload files we can find this dropzone usage documentation on -> https://react-dropzone.js.org/

                                              =============**************==============
6) Now in case we want to add a check on what type of file should be uploaded according to us 
-> 
import React, { useState } from 'react';
import './App.css';
import Dropzone from 'react-dropzone';

function App() {
  const [errorMessage, setErrorMessage] = useState('');

  const handleDrop = (acceptedFiles) => {
    // Filter the acceptedFiles array to only keep image file types
    const allowedImageTypes = ['image/jpeg', 'image/png', 'image/gif'];
    const filteredImages = acceptedFiles.filter(file =>
      allowedImageTypes.includes(file.type)
    );

    // Check if any non-image files were found
    if (filteredImages.length !== acceptedFiles.length) {
      setErrorMessage('Only image files (JPEG, PNG, GIF) are allowed.');
    } else {
      // Process the filteredImages further (e.g., display them, upload them, etc.)
      console.log(filteredImages);
      setErrorMessage('');
    }
  };

  return (
    <div className="app">
      <h1>HELLO CODERS</h1>

      <Dropzone onDrop={handleDrop}>
        {({ getRootProps, getInputProps }) => (
          <section>
            <div {...getRootProps()}>
              <input {...getInputProps()} />
              <button>Drag 'n' drop some images here, or click to select images</button>
            </div>
          </section>
        )}
      </Dropzone>
      
      {errorMessage && <p className="error">{errorMessage}</p>}
    </div>
  );
}

export default App;

=================================================================================================
                                                EXPLANATION

The <section> element is like a container that holds everything related to the drop zone area.

The <div> element is where users can drop files or click to select them. It's the actual area where the magic happens.

...getRootProps() is like a special set of instructions that help the <div> element handle the drag and drop behavior.
 It's like giving the <div> a superpower to handle files.

The <input> element is hidden and acts like a secret button. When it's clicked, 
it opens the file selection window on the user's device.

...getInputProps() is like a secret set of instructions for the <input> element. It helps the hidden input do its job properly.

The <button> element is a message for users, telling them to drag files or click the secret button to select files.

Overall, this code creates a special area in your app where users can drop or select files. When they do that, it logs some
information about the files to the console. It's like a cool feature that lets users interact with files in a fun way!                                                
