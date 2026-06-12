Table Users {
  id uuid [pk]
  login varchar(100) [unique, not null]
  email varchar(255) [unique, not null]
  passwordHash varchar(255) [not null]
  avatarUrl varchar(255)
  currentRole UserRole [default: 'Client']
  rating decimal(3,2) [default: 0.00]
  createdAt timestamp [default: `now()`]
}

Enum UserRole {
  Client
  Worker
  Both
  Admin
}

Table UserDocuments {
  id uuid [pk]
  userId uuid [ref: > Users.id, not null]
  documentType varchar(100) [not null]
  s3Url varchar(255) [not null]
  createdAt timestamp [default: `now()`]
}

Table Sessions {
  sessionString varchar(255) [pk]
  userId uuid [ref: > Users.id, not null]
  userAgent varchar(255)
  ipAddress varchar(45)
  createdAt timestamp [default: `now()`]
  expires timestamp [not null]
  replacedBy varchar(255)
}


Table Orders {
  id uuid [pk]
  ownerId uuid [ref: > Users.id, not null]
  workerId uuid [ref: > Users.id]
  title varchar(200) [not null]
  description text
  cost decimal(10,2) [not null]
  
  latitude decimal(9,6) 
  longitude decimal(9,6)
  address varchar(255) 
  
  s3Url varchar(255) 
  createdAt timestamp 
  expiresAt timestamp 
  state OrderState
}

Enum OrderState {
  Open
  InProgress
  Completed
  Cancelled
}

Table Tags {
  id int [pk, increment]
  name varchar(50) [unique, not null]
  color varchar(7)
}

Table OrderTags {
  orderId uuid [ref: > Orders.id]
  tagId int [ref: > Tags.id]

  indexes {
    (orderId, tagId) [pk]
  }
}


Table Transactions {
  id uuid [pk]
  orderId uuid [ref: > Orders.id, not null]
  senderId uuid [ref: > Users.id, not null]
  recipientId uuid [ref: > Users.id, not null]
  amount decimal(10,2) [not null]
  status TransactionStatus [default: 'Pending']
  createdAt timestamp [default: `now()`]
}

Enum TransactionStatus {
  Pending
  Held 
  Released 
  Refunded
  Failed
}
