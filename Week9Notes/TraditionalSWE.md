# Traditional Software Engineering

## Table of Contents

0. [Table of Contents](#table-of-contents)
1. [Class Modeling](#class-modeling)
    1. [Terminology](#terminology)
    2. [Relationships](#relationships)
    3. [Finding Classes](#finding-classes)
2. [Textual Analysis Guidelines](#textual-analysis-guidelines)
3. [CRC Cards](#crc-cards)
    1. [Responsibilities, Collaborations](#responsibilities-collaborations)
    2. [Checking Class Definitions](#checking-class-definitions)
    3. [Example](#example)
4. [UML Class Diagrams](#uml-class-diagrams)
5. [Elements of Class Diagrams](#elements-of-class-diagrams)
    1. [Classes](#classes)
    2. [Attributes and Operations](#attributes-and-operations)
    3. [Relationships](#relationships-1)
    4. [Sample Associations](#sample-associations)
    5. [Multiplicities](#multiplicities)
    6. [Association Classes](#association-classes)
    7. [Sample Aggregations](#sample-aggregations)
    8. [Sample Compositions](#sample-compositions)
6. [Behavioral Diagrams](#behavioral-diagrams)
    1. [Sequence Diagrams](#sequence-diagrams)
        1. [Example](#example-1)
    2. [Communication Diagrams](#communication-diagrams)
        1. [Example](#example-2)
    3. [State Machine Diagrams](#state-machine-diagrams)
        1. [Example](#example-3)

## Class Modeling

### Terminology

- **Class**
    - a template for building objects
        - Concrete classes cans be used to create objects
        - Abstract classes are useful abstractions, but do not 
        directly represent real-world objects
        - *Examples: Person, Student, Instructor*
- **Attribute**
    - a piece of information related to the class (called 
    attributes, fields, or properties in various languages)
- **Operation**
    - actions that perform some sort of functionality (called 
    functions or methods in most languages)

### Relationships

- **Generalization** 
    - also known as inheritance, `is-a` oe `a-kind-of` relationships *(e.g., a Dog is an Animal, a Dog is a kind of Animal)*
- **Aggregation**
    - represents parts of wholes or assemblies, `a-part-of` or `has-parts` *(e.g., an Engine is a part of a Car)*
- **Association**
    - weaker link between two classes, not an aggregation because each part is its own thing *(e.g., a Patient is associated with an Appointment)*
- One rule of thumb: does the item make sense without the item it is associated to?

### Finding Classes

- **Textual analysis**
    - examine use-case diagrams, use-case descriptions, looking for classes, attributes, operations, and relationships
- **Brainstorming**
- **Common object lists**
    - *(lists of objects commonly found in specific domains)*
- **Patterns**

## Textual Analysis Guidelines

- A `common or improper noun` implies a class of objects 
- A `proper noun` or `direct reference` implies an instance of a class 
- A `collective noun` implies a class of objects made up of groups of instances of another class 
- An `adjective` implies an attribute of an object 
- A `doing verb` implies an operation 
- A `being verb` implies a classification relationship between an object and its class 
- A `having verb` implies an aggregation or association relationship 
- A `transitive` verb implies an operation 
- An `intransitive` verb implies an exception 
- A `predicate` or `descriptive verb phrase` implies an operation 
- An `adverb` implies an attribute of a relationship or operation 

## CRC Cards

- CRC (Class - Responsibility - Collaboration) cards document classes and their relationships 
- Also provide a good way for checking current class definitions, making sure you are not missing anything 

### Responsibilities, Collaborations

- **Knowing responsibilities**
    - what things is the class responsible for knowing?
- **Doing responsibilities**
    - what things is the class responsible for doing? 
- **Collaborations**
    - how do instances of different classes collaborate/interoperate to accomplish some task 

### Checking Class Definitions

- Get team members to pretend they are instances of each card/class, try to solve tasks 
- Ask questions of each team member 
    - *Who or what are you?*
    - *What do you know?*
    - *What can you do?*
- Role-play through each scenario, see where you get stuckL this is something that is not already modeled as part of the class that you may need 

### Example

![CRC Card Diagram](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcR15bEQelPXwmvBrDBQ7vLxwxaKvY7hsOCs8w&s)

## UML Class Diagrams

![UML Class Diagram](https://agiledata.org/wp-content/uploads/2023/04/oo1013ONF.gif)

## Elements of Class Diagrams

### Classes

- Represent the classes in the system: domain classes at this point, more detailed classes once we are in design 
- Include attributes and operations, but not those that are part of all classes 
- *Note: we can leave information out and these are still valid!* <br>

![Class Example](https://cdn-proxy.slickplan.com/wp-content/uploads/2023/10/5_uml.png)
<br>
### Attributes and Operations

- Properties (either stored or derived), or actions/functions that can be performed
- **An attribute:**
    - Represents properties that describe the state of an object 
    - Can be derived from other attributes, shown by placing a slash before the attribute's name <br>
![Attribute Example](https://cdn-images.visual-paradigm.com/guide/uml/uml-class-diagram-tutorial/04-class-attributes-with-different-visibility.png)
<br>
- **An operation:**
    - Represents the actions or functions that a class can perform
    - Can be classified as a constructor, query, or update operation 
    - Includes parentheses that may contain parameters or information needed to perform the operation <br>
![Operation Example](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSJZPU6U1htZ51YIILksRf9Zrv1vMtR_H8Xtw&s)
<br>
### Relationships

- **An association:**
    - Represents a relationship between multiple classes or a class and itself
    - Is labeled using a verb phrase or a role name, whichever better represents the relationship 
    - Can exist between one or most classes 
    - Contains multiplicity symbols, which represent the minimum and maximum times a class instance can be associated with the related class instance
- **A generalization:**
    - Represents `a-kind-of` relationship between multiple classes 
- **An aggregation:**
    - Represents a logical `a-part-of` relationship between multiple classes or a class and itself 
    - Is a special form of an association 
- **A composition:**
    - Represents a physical `a-part-of` relationship between multiple classes or a class and itself 
    - Is a special form of an association <br>
![UML Relationships Diagram](https://cdn-images.visual-paradigm.com/guide/uml/uml-class-diagram-tutorial/07-relationships-between-classes.png)
<br>
### Sample Associations

![Sample Association](https://i.sstatic.net/Idffa.png)

### Multiplicities

![Multiplicity Diagram](https://slideplayer.com/slide/13005053/79/images/33/Multiplicity+PowerPoint+Presentation+for+Dennis,+Wixom,+&+Roth+Systems+Analysis+and+Design,+3rd+Edition..jpg)

### Association Classes

- Allow information about an association to be stored 
- Very common, actually quite rare to have a true many to many relationship without such a class 
- *Example: each student, in each course, will have a grade, Grade class provides a place for this* <br>
![Association Classes Example](https://www.researchgate.net/publication/225111515/figure/fig5/AS:669054335471624@1536526392526/UML-diagram-for-association-class.png)
<br>
### Sample Aggregations

- Logical relationship 
- Classes are logically linked to one another 
- Instances of these classes make sense on their own (I can take a wheel off a car, a desk out of an office), can be linked to multiple classes <br>
![Sample Aggregation Example](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAboAAAByCAMAAAAS5eTaAAAAilBMVEX////+/v79/f0AAAD6+vrl5eX29vbr6+tCQkLOzs739/cgICBvb2/z8/PFxcV2dnZYWFjV1dUrKyuEhIRlZWU5OTlAQEBGRkbd3d3Ly8s3NzfBwcFoaGghISHh4eFtbW1cXFyysrKWlpaNjY1NTU2np6cpKSmrq6ufn5+AgICVlZUWFhYMDAwZGRmP4QqCAAAWH0lEQVR4nO1dC3uqPAxuS6HSWbkqCA5BUHGX///3vqTgbXMOz3EH/J7lOWcVKVj6NmmSpoEwpjg3GemNlKU4sRQhnDGrx3Z0JcoItTjnTVObgjYF41R/1xbXapBPNdjXNc4vtjhh+lgRxX/oIbuSbgcnnNKmbcMmy+q7BbrDKAUM7SItJj1SWqSTuacAOvIATAcd56VzaHXaNP7r4s9Odbm4SOdzEJQic/zE9596I3/z5CeJo1BEPAR0Wb5JoM290cZ/9WdJKQk1w9d8vHB6o2UYLt3nXIA8pw8BnTd9wkb3R87CyY0A5LaZRxMrNnsjJZRM80UG8pL3Pet2Im+UKyUtpZQlJf61moNDoQ6nPtVQH2tcvvhqDcEEn/gvEqFzxdWmUqjEJaiAzfTYfMl0+ZlN6HnZiY0o8aI84+RBoIunuaV61FU4qJb2s+Y6F6C71sUyk/ZL6RSCCNBrJKcckZRcEhh72N0cCRDmXFGFSFiSSobKLFdsPlfXW8Kk4soPTcoeQlwSMvcXTMn+fp/hWJ8GvAN0isyr2WrnvoAVAbAhQ3GAQwJ0gBc8BAAnJeNglAkYEsLkAicuAlAC2kkygY/XWsIfDDo7WfB+oWNdoeOkftpyq5gW7SGx0JAmEoEC3msNQ1NZFE8pE8pGnBLJxJM/J1ctbcotDR17HOhC3qfAbKGTHaAjYhkJasazgK3ybepM0qos8qp2qtCDs2q9e3ZrsOwn1dYrnRcbmKwIZ76/soD3rGrqWVdFJmXWo3FdKB8FuqxC7iSrnK2NtV1lwl/VvmHkLxUqOMU03C3DFKqVzvsmKJOCxFWYBm87Bha/XGzm3zSFPhjXeUnYq5pyG3QrBozz4nMepGInzGnK10aYEfs9Iyp4WytvqbXUwlgTs47JxHcn2TqVFCgtTfaNoikfELpvdK+fpBugo7HrSEVlMOKsLuZhXY7mxDNeYGJ7TUnsGruoejOA7cj2LSbwUFLWm1enNgET+CG48qNnkh7+kP+zwITOBRUcLai7+mZv4Tpz8Wqi/TfmZB4scvetFCQzStAz32qSLfO4mK8DAI2sn2IKOookYh5sjEBx62KTaUP7lrQa5sNwXWfjABVvbTsxzu7IpbdAx1fGCgbbLCU0cysz8G1OYvwqM2oiAgdkZepkwEZ2GGN14u0yar6Psi9G2zl09CGNgw5cx0ACUcKA6RQjd3Q23ACdBWqHMYo2DjREOZVVzzKrfDaSYu4alU28sWsXjmMSUeTGWz4BpouNWR2/AXS0E3QPpqZ0NQ6Q0Rp3E5f3dBPdYNdBK22nipYeWNwyDZS9M8mqcp0iXczClJK49t06o9yO3LwazxknKnerIF9zRi/KiQ/QPdpc53Wc6yQx03VZZFRyck+t5hY1xYKfNmPgevRzCRCWoImYaIebXqb9JrEJE5wQseBC4GIvtaQwTSjYxdF2Dt3/1jigYpcsx7kDWgC/p/PlprlOAwAwgMhGdxcqh3Ch7mrWrPRzyeCThEYy0CcpZxahCkbbxSZ/gO5/axyAPpMpMSpRp7mjinkLdO0VGqk2PgKnXeh8xdq1A8AVtA2GuDWr7xitwDqtHOznOi0w4Q9iyhr688e7hdqR1Pzkl118HGudHWHbTcpAjXPNeVmLYJsFQRqM023uTDjMPWIVhrXA/q+z9KVOQajGAa7GAYtYn+ypE7odukvET4YTBpbQfQTMDXRmHPQHHesM3byr+7mexZKRdOZNqiQOVqqKUJGLnDyJQZo6SR5VL4DdapEnbpCsCSnzVfD8bFpfqHct3Qe6BjDoYz2pUUYPkVK33OEz19H/BdcFlWlZJPPnZO2StCALh6ZTsKfiWSGIbZSK166NsS5JZfNgS0T0nPKiVIJSdeXZ7wMdSEUYV4AWkxieoGXlzdAx6xPXfZwNf5ToKV2r1X7qDF0ZoYbiGQWZL81xUMxeiDUeEamctSKFkYfRxqgVZdl0DYJVSrJONou6YA1DfEn3gg77u/2Py62C3TwhnxkHLXTnrrIfplPQukDX1Tgg5dsWdIM6skmWvySh/zwnxImIYOVY0PWsqLeFMweY4mlKGGKgbMf3R6ZmhK/pBrvuO2JC7aM+58F3ywQXiH7mun9K3Vj8DLpuKwceaJiEjDAUIZzVxVNJiMh96LBdbpH5ApQVFaSgq4pwbREc9+uYewvDRrX9ym3vNddBh4s4U83EpBbG+A8sGMkO0CFyw4SOnEPXxTiwQiMMHGMNsKym8fzVZnFtwOHWf7KJ2s08UQC/SbKdPocelDzyC1oahQLb+HuB2WmVHMxsiRoIMUFvVZqZZWPioQXAifuCggYjHFKYdi1OQW1SIDolLpl/+4D72BTkOGiO4FTtvdaM4cd/G2uEURxg9VAc+vtfRtVLKa2wQxM7u59pHCTvmxQZtAALwJ2w1ftmUxbu0/tOEV74Rh4zkhlPif+8Exjg+fSURDvvG33hBq4z67J0XrZjx4PPRTkuY5ieSFw65daCR0kLf1RO4AbwqYQWMJnutmmxWmvvMxeZZYlrY5S1GiagzRtVh5l7cUR1N3bopXsSs7TbQR515UZtbjYF0M7GAXotTFNvpoCHkMRWlAsTRKjwbIVBH5kpcFR4yhKxwhFqmkIIvUzUYa7rAp2dGG5uTN23gMmyGgdhIBhV4+nY2aRgiNeh4QYFB8VpFW6MgHOzNIxkGUQ7DDurF05dOtsrt2+MgwVGtDT7LOhR0iut/nzfS/cjpkMX0R3EyVFq6QFlte3qqmFqdLnUiz4SRiUBsYQjXHs1JA5n1jxyEz6nweOSsu/sqxug42VliyTwwpB5wNhqVRUgAXz4VLogD5X5GkiUpNCc2sjhxsIxHE+ULjSufnID18AFoi+p1TAz3rZZnYRjCnKzmfiXBFo6CkrGLHUy/SGITMoDdJ1jU2jjvWSSgzIuEUjaPifM6qBI6pHJYObRG4gwzM6yNJpXm9hdTSmqjLyv2C5ihbGpqncjMElpTMPqGaZUwMcY40CF4UImRo7TIAY6kDSJCYkck29n9bUH3RsHuKqVoSRR/FAdjB6S/VOByXREqUJL+XS10YrN/S6qzsaB5h/QBogFMwGwGtV8hV0N6CBqVFIMrFPoHdajQkcVaFg7qCmdoEtDQd4KGszYxK+L9aRMCXlJ6m1dLASOD2MJclOPm7kR4gXzN+BLAWoUmSWe2n0TXU20wFTAbuUsAhlMD7M0OmpU8PJ9L92PkDWcKAFTGTq6xYeCOKnySaP2sVvCikAFU3q+prjQgsHHesqEMcBxKuX6STlMbyhIpYRRL6XWiu4014F6JIhRk5eNnFSAGnMCRdYVKC18ClyniFGyzNTKs2e4FkjOl9eCU/QikJFRb6cvl5ftWqJg1wk/j3HRfSfKJddhnY2xAcPPTiL97P/Mt0J4Xa/zjFiUa7mFLRGBsZnsj7pC16oyIAH1bgqLZXqdBZfvtNajhI4P13faq+6cNYrtnbhOLDdp/eZ4y1cbUNzaRZ6C4b8LC3vrajH3NKudLehlYu4Yb+O5mCRG7pnjt7HIZv6iSuYnthM6C8+bBa1H6DLJ7LeUxUnMBMwHUi89gLlaTscYXs3+0aQHRhBR3qKag5bR6CUYnC+C52naPkTvgesN53ey6+Lds7PYjOtwVhBRLKpgjsEycT0Oy1jbQduRC2hylS6S6Wiz8l5m0dJej97D2Ks2S9ffTST52uxtoAtNSb23CbGnc7ilpaU/DEO1dlbLbotH9yGwJEFp93a+x1GEa23X4tKr12L/DH0HrrfQdeE6ac4zcyJEPAczm5lzAaoRPJDyPAFDElfqsgyNdaLiOM48wTNcPFexZ7I4XM09b+vEV6BjLdcxEhspsd24WYKQKLpIHL1VGyc1/1nEKuVUhDVjfo1rkzBZgc6CDG9JcoSu38D1G7juhCzcgw7aP7esZkbSclsv+JwvU9BGgtvaL2bne2FzSYRT1npTiEzGdRAqagcZcJ6qS5wB7OA5VXAd+zedhSv9T2M+iebE3GUMtJZip/fW4Hg6QNdr4PoNXAd9qlAXarZnadco1wsTHODSQ5NbUtJmFUEbZcAvykITRsUsS7eLyG6g07P0x5u30KGuWixnVU1kCiqQ5GK3QAsnnSW1x09ciD9LoJbzlzyMtkSkborc/xLt4xNa6PoOXL+B6/Bp4B/FvZZaJeJN/gf0azKt5CKC0moUp3b5p7E5YaIM3GWwps1jA8QXsNN2HWiYoEabdoxhmSao5RhNhpytYiU4Y/SukTlfk0IvhzIFsBsztd9DxGihMXQJn0DXY+D6AToaV7m2u1p5RulH5yfThqLVntSLNAz3XzUVGw80/OW0Wb/TeyIxWBvJIkKwwzIYPdiadH+x5lpiTqENVrNKZaHHWrDGqGp4jd6+9v43hI1UzS5e/bOStWZBM13b01DnLGhXK0/6jZ49WHNwjxr0YwFt2MFQzsIq9ZBsoKbwviS7rekdKx6usj9+96HwTu97PGV7E68YhWD0qCNHSn7VtPk5Ol8Buqhc2ZGbTm569PvWmEBHrv3SAgmxMJIoGiHNRm3RHEf7YrSn2aHGWRG1V311Co5mmk5udahRRZto9gYaJvqK9t2D0fpE9QDeJeg+NMObvVfJKDp7vkuP/n3ndO6+01OjJEqqCDM4cIBuVEUNTNEeLQ1TdFrs73xW8Vgcof7qVNTeFxpyVmMWJXn1ikutJylvtFutj6QAHaCz/Vf39CGuPPo9anw6NatmbmWUOvmG64lYWlaT9kEXV6ipYZ1VPyu+OmWd3uPklAA1JK12gp2kvJG4ENhLSG0XrpvmpsjU7T1w7Ic/6L5jISxTpAlCl1WhaqOU99pE2+pj8bH5e13jrCCfi9Ma7QRL6adTlMyjHd2H32rSDto+FPAO0M39haS8Pd8U5HNxW+fccjHVGqajNNeZOq2GjnxsCv2XN5+bQltyGPTT1KCkrXd61aFgxxr7G7ZRju2tTmswiSkiAm1z76ET6bwnT1MX6GZLZanz5zsrrncO/dQ533ffWYGh0/OkyVYE0PWZSwI0S3MaoBUPjZNgqMg09KcBRgg3NbSqfNd9Tn9F8+mSW70m35Cn3pReFPGW9KLPTmr9Es2pItzk5eJ5tFKExToMoBG0PTbxjEBg9pw3pXPKm58mDV2gl6XBmovHbxGuSMwX/mYtNGSSM0tdjSr9p9S3+/lecZh3oBY6aQF2We37ABx6S2UxNvJUaJ+odpn22MQz+oXuQI3ARIjitbvBHUwAIrovRZE/LVMLo1csxnv1Gp5S58D1H6KhQRdgjGf4lBcC1yl0tAaAl62mfuChJKWXN8j2QX2vHAwPOs8x3gulnfQgMJVOKEx4XD77W5OwASUX9pL8UVLe/DDhhiTxGq7e/UI3zKJUSK1QMirBfPICI7SVMJUQAlOfNoU4FOYXxZUa4m9qZMXM4f9oCeoi3XGnz18S6iDiyTdw1wEuczC9/q5dAO3QLqqn9+R5g4mi39+fnpuiOXo+++6seL5S4+mGGh9P+b6xkH3uex8O16FNqZ6rfFZ6tN0dy5st6zqCkYh5OK3cvMrdYVBevY15n/lyBwQdkHraZaWfrDI84KQxz3WAC/N2z9U6jmM7HghlRbK8bzaNG2lA0Gmu2xFrHr67tXmSARo4zyujWSkkbflxEORNQ8WupVj4YRoQdBhOANDBh0n1vCjY4X0pygQ7D+Ot8ZsBeVMwwOEXOt0U1kIHEBXR6y7jOoUHM73oPZ9grmLaRqwc6dIiyrkj9kqNv7oYk2+0sSk90YCg25vkmsQqeVrFMKjFxDHcAqeUwUjKlvoOXB8qdFR5QTLaxvHuvVpnenPw4KB7nIzrP01n0AHh3oXKjQLMCa7TsvTWssv0634+0Cl0jDKBm0TyvOBEWDooYjD6SUt9B64PlOtOXqdF+UDfZvfrfj7QKXQ6zlnvjAKZhDuK6PBer9V34PpwoMO95MJ3ZBu+s9/TqTfV6f3yA5zrehWYdDDQtUkVs4dJZdq3cfBn++t+pB2Pliy/a8b1n6Mb9tf9KJ3lw3wE6ts4GA7XneXDfATqOzZlOFy3T6r4MFzXt3EwHK5rUt48FtcNY1cry9y81+hnfFuT+ZS3WWgPDdEbHL7O+3CXX/5+G+Ql8mYLq+9h5s3G+LKJ3MWYVXxNgXVSSGnpVxdIS38n5Yca/FhDfqpx+WJ58fZKSB5Px/sstE3T2nwPg4RuPs0xsLdj53yuIf+u+6SQpkpHpUWomRtRlUS4CXI6i/DvdNQUzXfTw6kRHFyvMetUoz01ak8l0yo0FqcCc4/ZMKGzkzd3lpw92MXn+7vu+/r2M0BrhrtaLRG+RVG7SfOrTZfH4uxgdmkL5pUaF+/rzmaRa+zTdmvkeJsuYJjQedN3N4o6P98tNTp132FXqxLLqLi01/9DcaXG310cz20v9ZdHrsOXJfABQ2dX7sT2uj7f3bvPm3vzeLup9SvlK69PDRM3Ewg/PxoHKOuHDJ0XhaLPiDAke4O7WjM3FJhfuc1ce1KgE5i16WuaDTenp+jpqYs12HmNL27PBUCXnBgHTFqyTSU8SOjmft6EFX316KxL59CPnXO9+05O4fvg7WZXa98+THn61shL+snZEb1EV27/ZxrPtavQrvvXeY1PaTiLPufu50eAbjqIwPUBeFPOX/j5GND1uoQ4HK47f+HnsKHTH73pcgjQDYHr2MNwnU4+MhSBOQCu27ufH4Dr9tCF1m/0syb6KFynM0dSvV2k37wpQ4Fubxx8vejzPXRndJKNkX68xx/heLybZjZ7OiYDiH4eAnTfBjjcCF2b3Ey/S4B+uMc9oPOmY/oLHdK5cXCxxo3Q6WpMuyDYh3vcB7ol+w2hRTo3Di7W+APodIZwdgygvid0s+XvngNNlN6Z67BW48Lmx3fQ3RG6eNZvMN9w7Lpz4+AS/Ql0+mViXB7y+d0XOvkbuI70fTDf7dChqGze+MevXHV7W3UT49FyCPvrBgDdJffz8ezJ2k/X/j5U1UtK32P2/anzLxG6X5Nct4R/XvQ5nv1z6PQb/H4Kuj4Tqw4HuksrBydnyZ9DR9o0vr/Q/RBdWjk4OUv+AjpCf6H7Ubrgwzw5Sf4GusPrr36h+xmSR6771FefoPseuzPoLtLF+pfODRm6g113+Rn/BaEPU9xnz8Gljr4/eWCS43vGe+uwD1zXW0MoBmv/QncDDYjr5N02aTU3vAc81yiOBgHdALgOfR532qTV3PAe8FwjhM76hY5q6NjDcZ0lf6GjONmxR+M6qYYCXc+vEGDEeiTosqjv5BswfLSaEi9GL15s2/YcqCnsL4q/qvHVqUmaTlaVo23LvjeLdqJ5VRVZZvdGnjexV9MS+M3LDePV6I/e3t79V8MVdKApwT6RXRlP7z12GNDTqzHGNzlvx+NF6Iz7osVy7DjOWtHhpAi+TmK1cMaL3voLf9oZLwtOOFHt6xd6IlPgj+s3nT+EvNSvLe+TmhdnwGSr59t+XiR9JNpkwe5zAbMzgR5EidXH25uPxPTuB/1KeCX1siTn+7/Xim9qXL/4Qg0qObW0P1f2rLd1JYrZcXsjimNccfYf4ckzfhrraHAAAAAASUVORK5CYII=)
<br>
### Sample Compositions

- Physical relationship 
- Classes are physically part of one another 
- Instances do not make sense on their own, or cannot be easily be removed from a single related instance 
- "Ownership" <br>
![Sample Composition Example](https://www.loekvandenouweland.com/assets/2021/uml/employee.jpg)
<br>
## Behavioral Diagrams

### Sequence Diagrams

#### Example

### Communication Diagrams

#### Example

### State Machine Diagrams

#### Example
