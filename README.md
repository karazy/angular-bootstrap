# Bootstrap APP

## Create the App
 ng new PROJECT_NAME --style=scss 
 cd PROJECT_NAME

## Install required libs etc.
### https://material.angular.io/
```
npm install --save @angular/material @angular/cdk
```

### bootstrap css
```
npm install --save bootstrap
```

### Add Angular Animations for material:

https://material.angular.io/guide/getting-started#step-2-animations
```
npm install --save @angular/animations
```

## Modify project files
### styles

Edit styles.css

If project was not created with sass at first: `ng set defaults.styleExt scss --global`

```
@import "~bootstrap/dist/css/bootstrap.min.css";
@import '~@angular/material/prebuilt-themes/deeppurple-amber.css';
```

Edit indexl.html and add Material Icons
```
<link href="https://fonts.googleapis.com/icon?family=Material+Icons"
  rel="stylesheet">
  ```

### Add imports etc in app.module.ts

Imports
```
import { FormsModule } from '@angular/forms';
import { HttpClientModule } from "@angular/common/http";
import { MatListModule } from '@angular/material/list';
import { MatCardModule } from '@angular/material/card';
import { MatButtonModule } from '@angular/material/button';
import { MatIconModule } from '@angular/material/icon';
import { MatToolbarModule } from '@angular/material/toolbar';
import {MatDialogModule} from '@angular/material/dialog';
import {MatInputModule} from '@angular/material/input';
import {BrowserAnimationsModule} from '@angular/platform-browser/animations';
```

NgModule settings
```
@NgModule({
  declarations: [
    AppComponent,
    CUSTOM_CLASSES
  ],
  imports: [
    BrowserModule,
    BrowserAnimationsModule,
    HttpClientModule,
    MatListModule,
    MatCardModule,
    MatButtonModule,
    MatIconModule,
    MatToolbarModule,
    MatDialogModule,
    MatInputModule,
    FormsModule
  ],
  providers: [ProjectService],
  bootstrap: [AppComponent],
  entryComponents: [ADD_DIALOG_CLASSES HERE]
})
```

Dialog creation
In declarations dialog und component importieren
entryComponents: [CreateProjectDialogComponent]


## Start development

```ng serve```


#Adding assets
#https://stackoverflow.com/questions/44042223/load-json-from-local-file-with-http-get-in-angular-2

Put YOUR_DATA.json under assets/. Then add it in angular-cli.json.
Then it can be retrieved via http.get.
```
 { "glob": "YOUR_DATA.json", "input": "./", "output": "./assets/" }
 ```


## Docs for lookup --> devdocs.io
* https://angular.io
* https://material.angular.io/components
* https://getbootstrap.com/docs/4.0/getting-started/introduction/