# Read: 33 - GraphQL @connection

## GraphQL @connection 

### Add relationships between types

* The @connection directive enables you to specify relationships between @model types. Currently, this supports one-to-one, one-to-many, and many-to-one relationships. You may implement many-to-many relationships using two one-to-many connections and a joining @model type. See the usage section for details.

#### Definition

```directive @connection(keyName: String, fields: [String!]) on FIELD_DEFINITION```

#### Usage

Relationships between types are specified by annotating fields on an @model object type with the @connection directive.

The fields argument can be provided and indicates which fields can be queried by to get connected objects. The keyName argument can optionally be used to specify the name of secondary index (an index that was set up using @key) that should be queried from the other type in the relationship.

When specifying a keyName, the fields argument should be provided to indicate which field(s) will be used to get connected objects. If keyName is not provided, then @connection queries the target table’s primary index.

#### Has one
* A Has One @connection can only reference the primary index of a model (ie. it cannot specify a “keyName” as described below in the Has Many section).

#### Has many
* one-to-many connection needs an @key that allows comments to be queried by the postID and the connection uses this key to get all comments whose postID is the id of the post was called on.
* example: a post has many comments.

#### Belongs to
* You can make a connection bi-directional by adding a many-to-one connection to types that already have a one-to-many connection.

#### Many-to-many connections
* You can implement many to many using two 1-M @connections, an @key, and a joining @model.



