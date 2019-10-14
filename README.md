# psa2routing
## 3. Routing Basics


### 3 Defining the Base Path
```
ng build --base-href /addpath/
```
### 4 Importing the Angular Router


|RouterModule.forRoot|RouterModule.forChild|  
|---|---|  
|||

### 8 Using HTML 5 or Hash-based Url

|HTML 5 Style|Hash-based|  
|---|---|  
|Leverages HTML5 history pushstate| Leverage Url fragments|
|Default|Must be set with {useHashL true|
|More natural||
|Requires Url rewriting|Server ignores everything after hash|


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

## 5. Route Parameters
### 2 Configuring a Parameterized Route
```
@NgModule({
 imports:[
   SharedModule,
   RouterModule.forChild([
    {path:'',component:},
    {}
   ])
 ]
})
```
### 5 Reading Route Parameters: Snapshot
```
this.route.snapshot.paramMap.get('id')
```
or use observable:
```
this.route.paramMap.subscribe(
```

### 8 Defining Optional Route Parameters
```
[routerLink]="['/products',{newkey:oldkey,newkey2:oldkey2}]"
```
get:
```
this.route.snapshot.paramMap.get('newkey')
```
### 9 Defining Query Parameters
```
[routerLink]=   [queryParams]=
```


retaining parameters
```
{queryParamsHandling:'peserve'}
```

### 10 Reading Query Parameters
```
this.route.snapshot.queryParamMap.get('date')
```

## 6. Prefetching Data Using Route Resolvers 
### 2 Providing Data with a Route
```
this.route.snapshot.data['date']
```


## 7. Child Routes
### 5 Activating Child Routes
```
//Absolute path
this.router.navigate(['/products', this.product.id, 'edit', 'info']);

//Relative path
this.router.navigate(['info'],{relativeTo: this.route})
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
