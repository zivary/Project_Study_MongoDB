<img scr="https://upload.wikimedia.org/wikipedia/commons/thumb/9/93/MongoDB_Logo.svg/220px-MongoDB_Logo.svg.png">
# Project Study MongoDB 

2022년 2주차 Study

#. mongodb 에서 data 처리 기본 명령어

 RDBMS	 	| mongodb

 insert		| db.user.insert( { : ,  : ~~~ } );

 update		| db.user.update( { : ,  $set ~ : ~~~ } );

 delete		| db.user.remove( { username : ,} );

 select		| db.user.find( { : ,  : ~~~ } );

---
DB 검색
  > show dbs

test db 선택(변경, 생성)
  > use testDB
  
사용중인 DB 삭제
  > db.dropdatabase()

사용중이 DB 확인
  > db

Collection 검색
  > show collections

Collection 생성
  > db.creatCollection("Collection 이름")
  > db.collection.insert({"Key": "Value"})
  > db.creatCollection("Collection 이름",{option})
    option
      capped: true,   // true 이며 반드시 size를 설정해야 한다.
      size: 6142800,  // 해당 Collection의 최대 크기
      max: 10000      // 해당 Collection에 포함될 수 있는 최대 갯수
Collection 삭제
  > db.collection.drop()
  
---

db.user.insertMany( [
     { username: "Tom", password: 1111 },
     { username: "Jane", password: 2222 },
     { username: "Alice", password: 3333 } ] );

db.user.insert( [
     { username: "Han", password: 4444 }] );

db.user.find({});

db.user.find({ username : "Jane" });

db.user.update({ username : "Jane"}, { $set: {password: 5555 } } );

db.user.remove( {username:"Jane"} );

db.user.find({});

---

db.dept.insertMany( [
    { deptno: 10, dname: "ACCOUNTING", loc: "NEWYORK"}, 
    { deptno: 20, dname: "RESEARCH", loc: "DALLAS"}, 
    { deptno: 30, dname: "SALES", loc: "CHICAGO"}, 
    { deptno: 40, dname: "OPERATIONS", loc: "BOSTON"} ] );

db.dept.find({});
