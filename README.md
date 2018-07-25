# demo-express-graphql

1. Install modules

```
    npm install
```

2. start server

```
    node server2.js
```

3. run graphql-ui

go to [localhost:4000/graphql](localhost:4000/graphql)

4. test query

* get all courses

```
    query {
        allCourses {
            id, 
            title, 
            author, 
            description
        }
    }
```

* get all course with specify topic

```
    query getSingleCourse($courseTopic: String!) {
        courses(topic: $courseTopic) {
            title
            author
            description
            topic
            url
        }
    }
```

query variable

```
    { 
        "courseTopic": "Node.js"
    }
```

* get single course with id

```
    query getSingleCourse($courseID: Int!) {
        course(id: $courseID) {
            title
            author
            description
            topic
            url
        }
    }
```

query variable

```
    { 
        "courseID": 2
    }
```

* update course title

```
    mutation updateCourseTitle($id: Int!, $title: String) {
        updateCourse(id: $id, title: $title) {
            id, title, author, description
        }
    }
```

query variable

```
    {
        "id": 2,
        "title": "Express & MongoDB"
    }
```