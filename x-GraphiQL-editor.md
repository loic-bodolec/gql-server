### Queries and mutations :

```javascript
query getSingleCourse($courseID: Int!) {
  course(id: $courseID) {
    title
    author
    description
    topic
    url
  }
}

query getCoursesByTitle($title: String!) {
  coursesByTitle(title: $title) {
    title
    author
    description
    topic
    url
  }
}

query getCourseWithFragments($courseID1: Int!, $courseID2: Int!) {
  course1: course(id: $courseID1) {
    ...courseFields
  }
  course2: course(id: $courseID2) {
    ...courseFields
  }
}

mutation addCourse($id: Int!, $title: String!, $author: String!, $description: String!, $topic: String!, $url: String!) {
  addCourse(id: $id, title: $title, author: $author, description: $description, topic: $topic, url: $url) {
    ...courseFields
  }
}

mutation updateCourseTopic($id: Int!, $topic: String!) {
  updateCourseTopic(id: $id, topic: $topic) {
    ...courseFields
  }
}

fragment courseFields on Course {
  title
  author
  description
  topic
  url
}
```
