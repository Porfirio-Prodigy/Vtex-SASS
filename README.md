# How To Setup Sass In Vtex
Author: Porfirio



### 1 - Enter the **store-theme** folder and run the following commands
</br>


NPM:

To run commands in parallel in package.json

~~~
npm install concurrently --save
~~~

to install sass
~~~
npm install -g sass
~~~

</br>

### 2 - In the **package.json** file of the **store-theme** folder add the following script:
</br>
This command is used to create an npm script that runs 2 commands at the same time, it starts sass in parallel with vtex link.

~~~
"dev": "concurrently \"sass --watch --no-source-map react/styles/scss:react/styles/css --style compressed\" \"vtex link\""
~~~

### 3 - In the react folder create a folder called styles, and inside the **styles** folder create two other folders named **scss** and **css**

</br>

### 4 - In the react folder, enter the **global.css** file and add the following lines of code:

</br>

CSS:
~~~
@import 'styles/css/filename.css'
~~~
> you use this instruction for all css files you want to import, for all created scss files a file with the same name with the extension .css will be created in the css folder
</br>

</br>

## Recommendations
- Create a colors.scss file to add all project colors to sass variables, whenever you need to use some color, import the colors.scss file with @import and add the name of the variable that contains the color you want.

</br>

- Sass uses two types of basic syntax:

Sass
~~~
$font-stack: Helvetica, sans-serif
$primary-color: #333

body
  font: 100% $font-stack
  color: $primary-color
~~~

scss
~~~
$font-stack: Helvetica, sans-serif;
$primary-color: #333;

body {
  font: 100% $font-stack;
  color: $primary-color;
}
~~~

> Always change the file extension in the styles/scss folder to the syntax you want to use
>> although sass has two different syntax it will always generate the same css


## How To Run

Enter the **store-theme** folder and run the following command:

NPM:
~~~
npm run dev
~~~
