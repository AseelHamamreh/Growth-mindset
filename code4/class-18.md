# Read: 18 - Web App Security

## Many to Many relationships

A relationship is a connection between two types of entities. In the case of a many-to-many relationship, both sides can relate to multiple instances of the other side.
in Many to Many relationships, we need to create a separate table to hold the foreign keys.
Such a table is called a join table. In a join table, the combination of the foreign keys will be its composite primary key.

Modeling a many-to-many relationship with POJOs is easy. We should include a Collection in both classes, which contains the elements of the others.

After that, we need to mark the class with ```@Entity``` and the primary key with ```@Id``` to make them proper JPA entities.

Also, we should configure the relationship type. So, we mark the collections with ```@ManyToMany``` annotations.

we need to make association between the two classes and make it bidirectional.

## Security: a humorous overview

* five-way secret sharing has been illegal since the Protestant Reformation [Luther1517]. 
* ecurity researchers have a problem with public relations. (from the writer thought)
* large swaths of the security community are fixated on avant garde horrors such as the fact that, during solar eclipses, pacemakers can be remotely controlled with a garage door opener and a Pringles can. It’s definitely unfortunate that
Pringles cans are the gateway to an obscure set of Sith-like powers that can be used against the 0.002% of the population that has both a pacemaker and bitter enemies in the electronics hobbyist community of a Pilgrim who magically has access to 3-choose-2 {Rivest, Shamir, Adleman} (haha)

##### I don't think there is something really needs to be coverd in this reading.