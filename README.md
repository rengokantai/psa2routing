# psa2routing
## 3. Routing Basics
### 4 Importing the Angular Router


  
---|---  
RouterModule.forRoot|RouterModule.forChild 


## 4. Routing to Features
### 4 Activating a Route with Code
```
this.router.navigate(['/welcome']);
```
or shortcut
```
this.router.navigate('/welcome');
```

byurl
```
this.router.navigateByUrl('/welcome');
```


## 8. Grouping and Component-less Routes
### 2 Grouping Routes
```
RouterMoudule.forChild([
{
  path:'products',
  component:ProductListComponent,
  children:[
    {
      path:':id',
      component:ProductDetailComponent,
      resolve:{product:ProductResolver}
    },
    {
      path:':id/edit',
      component:ProductEditComponent,
      resolve:{product:ProductResolver},
      children:[]
    }
  ] 
}
])
```
## 9. Styling, Animating, and Watching Routes
### 2 Styling the Selected Route
```
<div class="wizard">
<a [routerLink]="['info']" routerLinkActive="active">
 basic
</a>
<a [routerLink]="['tags']">
 search
</a>
```

#### 02:42
```
isValid(path: string):boolean{
 this.validate();
 if(path){
  return this.dataIsValid[path];
 }
 return (this.dataIsValid && Object.keys(this.dataIsValid).every(d=>this.dataIsValid[d]===true));
}
```


### 4 Watching Routing Events
```
imports:[
RouterModule.forRoot([
],{enableTracing:true})
],
```

### 5 Reacting to Routing Events


## 11. Route Guards
### 1 Introduction
```
canActivate - guard navigation to a route
canActiveChild - guard navigation to a child route
canDeactive - guard navigation away from a route
canLoad - prevent async routing
resolve - prefetch data
```


### 3 
