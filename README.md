# teedm : Tee Data Modeling Language Idea

## Directives List

model User {
  id: ID @directives # [name]: [type] use ! for required , use @directives for validation
  name: String(255) # use [type]([options]) not have ? is required field
  balance: Float(10,2) # use [type]([options])
  active: Boolean @default(true) # use [type]([options]), @default: directives default
  username: String! # unique field
  gender: String? # optional field
  roles: Role[] # required relation 1-N
  posts: Post[]? # optional relation 1-N
  role: Role # required relation 1-1
  tags: Tag[] @pivot(type="user") # required relation polymorph
  
}
