Combining Union and Intersection Types in Typescript 
Introducton:
Typescript provides union( | ) and intersection ( & ) types to create flexible and reusable type definitions. A union allows a value to match one of several types, while an intersection combines the requirements of multiple types.

Explanation:
A union type means a value can be one type or another 
Example:
ts code 
type ID = string | number;
let userId: ID=101;
userId = "101";

here userID can contain either a string or a number. This is useful when an application accepts different formats for the same information. An intersection type combines multiple object types into one. The resulting value must contain all required properties.
ts code 
type User ={
name: string;
email: string;
};

type Admin = { 
role: string;
permissions: string[];
};

type AdminUser = User & Admin;

const admin: AdminUser = {
name: "sabbir",
email:"123@gamail.com",
role: "admin",
permissions: ["manage-users"]
};

We can combine both operators in practical example:
ts code
type Guest = {
name: string;
visitDate: string;
};

type Menber = {
membershipId: number;
};
type Visitor = Guest | (Guest & Member);
A Visitor must have guest informaton and may also include membership information. The union provides alternative, while the intersection combines requirements.

Conclusion:
Use | when a value can have different possible types. Use & when an object must satisfy multiple type definitons. combining them helps model application data clearly and safely.
