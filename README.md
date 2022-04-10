# to-do
Angular NestJs TypeORM
# Tutorial
https://www.youtube.com/watch?v=j38ufd8Q86w
# Application creation steps
1)  npx create-nx-workspace --preset=angular --style=scss
2)  npm start -- should throw an error of message null http://localhost:4200
3)  npm install concurrently
4)  add these commands inside package.json
    ```` "serve:api": "nx run api:serve",
         "serve:web": "ng serve",
         "serve:all": "concurrently \"npm run serve:api \" \" npm run serve:web \""
5) npm run serve:all -- should resolve earlier error by connecting frontend to backend
6) add angular material theme to project 
    ```` npx nx add @angular/material
7) add NgRx store to project
    ```` npx nx add @ngrx/store
8) add Library to project
    ```` npx nx g lib material
         npx nx g lib core-state --routing=true
         npx nx g lib core-data --routing=true

# Building blocks

1) **api-interface** project is used to communicate to server
   ```` let's create data-model to api-interface project's api-interface.ts
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
 
