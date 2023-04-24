# Solution to Module 24 Exercise: GraphQL Data Exercise

## To launch the GraphQL testing environment:
- clone this repository
- call `npm install` to install all dependencies
- call `node index.js` 
- visit `http://localhost:5500/graphql` in your browser

## For the easiness of testing, all test query calls are in the test_queries file. But also here below...

```
query getRestaurant($iid: Int=1) {
  restaurant(id: $iid) {
    id
    name
    description
    dishes {
      name
      price
    }
  }
}

query getRestaurants {
  restaurants {
    id
    name
    description
  }
}

mutation setRestaurants($name: String="Example Name", $description: String="Descr" ) {
	setrestaurant(input: {
      name: $name,
      description: $description
  }) 
  {
    name
    description
  }
}


mutation editRestaurants($iid: Int=1, $name: String = "NewName") {
    editrestaurant(id: $iid, name: $name) {
      id
      name
      description
    }
  }


mutation deleteRestaurants($iid: Int=1) {
  deleterestaurant(id: $iid) {
    ok
  }
}
```