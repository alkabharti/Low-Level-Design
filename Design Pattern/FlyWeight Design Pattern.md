## FlyWeight Design Pattern :

#### Properties :

- Structural Design Pattern
- Used when we need to create many Object of a Class. We use it to reduce creation of Object. 
- Intrinsic Properties : which are same for a Object
- Extrinsic Properties : which are different for a Object


#### Implementation :

- Interface : which contain method - Employee
- Object : Individual Class - Developer, Tester
- Intrinsic Property (Developer : Fix the issue, Tester : Test the issue)
- Extrinsic Property : Skills
- We use Factory to use return Object : EmployeeFactory
- Client : Client Class
- We will assign issues as per skills
