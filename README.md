# to-do
Angular NestJs TypeORM
# Tutorial
https://www.youtube.com/watch?v=j38ufd8Q86w
# Application creation steps
1)  ````
         npx create-nx-workspace --preset=angular --style=scss
         npm start -- should throw an error of message null http://localhost:4200
         npm install concurrently
2)  add these commands inside package.json
    ```` 
         "serve:api": "nx run api:serve",
         "serve:web": "ng serve",
         "serve:all": "concurrently \"npm run serve:api \" \" npm run serve:web \""
3) ````
         npm run serve:all -- should resolve earlier error by connecting frontend to backend
5) add angular material theme to project 
    ```` 
         npx nx add @angular/material
5) add NgRx store to project
    ```` 
         npx nx add @ngrx/store
6) add Library to project
    ```` 
         npx nx g lib material
         npx nx g lib core-state --routing=true
         npx nx g lib core-data --routing=true

# Building blocks

1) **api-interface** project is used to communicate to server
   let's create data-model to api-interface project's api-interface.ts
   ```` 
       export interface BaseEntity {
         id : string | null;
       }
       export interface Todo extends BaseEntity {
         Title : string;
         Description : string;
         Date : Date;
         IsComplete : boolean;
       }
2) Add services
 ```
       npx nx g s services/todos/todo --project=core-data
