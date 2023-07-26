# Specs

## Auth

### Register

HTTP Method: POST<br>
Body:<br>
```json
{
  "email": "email@email.email",
  "password": "password"
}
```

### Login

HTTP Method: POST<br>
Body:<br>
```json
{
  "email": "email@email.email",
  "password": "password"
}
```

## Management

### Restaurant

#### Create Restaurant
HTTP Method: POST<br>
Body:<br>
```json
{
  "name": "restaurant_name",
  "owner_id": 1
}
```
Comment:<br>
owner_id is uuid

#### Delete Restaurant
HTTP Method: DELETE<br>
Body:<br>
```json
{
  "restaurant_id": 1
}
```
Comment:<br>
restaurant_id is uuid 

### Employees

#### Add Employee
HTTP Method: PUT<br>
Body:<br>
```json
{
  "restaurant_id": 1,
  "employee_id": 1,
  "role": "cashier or manager"
}
```
Comment:<br>
restaurant_id and employee_id are uuid

#### Update Employee
HTTP Method: PATCH<br>
Body:<br>
```json
{
  "restaurant_id": 1,
  "employee_id": 1,
  "role": "cashier or manager"
}
```
Comment:<br>
restaurant_id and employee_id are uuid

#### Delete Employee
HTTP Method: DELETE<br>
Body:<br>
```json
{
  "restaurant_id": 1,
  "employee_id": 1
}
```
Comment:<br>
restaurant_id and employee_id are uuid

### Menu

#### Create Menu
HTTP Method: POST<br>
Body:<br>
```json
{
  "name": "menu_name",
  "type": "menu_type",
  "restaurant_id": 1
}
```
Comment:<br>
restaurant_id is uuid

#### Add Menu Item
HTTP Method: PUT<br>
Body:<br>
```json
{
  "menu_id": 1,
  "name": "menu_item_name",
  "price": 1.00,
  "options": [
    "option_x"
  ]
}
```
Comment:<br>
menu_id is uuid

#### Edit Menu Item Options
HTTP Method: PATCH<br>
Body:<br>
```json
{
  "menu_id": 1,
  "item_id": 1,
  "to_remove": [
    "option_x"
  ],
  "to_add": [
    "option_y"
  ]
}
```
Comment:<br>
menu_id and item_id are uuid
to_remove or to_add can be empty

#### Remove Menu Item
HTTP Method: DELETE<br>
Body:<br>
```json
{
  "menu_id": 1,
  "item_id": 1
}
```
Comment:<br>
menu_id and item_id are uuid

### Finance

## Regular

### Order
#### Order

HTTP Method: POST<br>
Body:<br>
```json
{
  "menu_id": 1,
  "menu_item_id": 1,
  "options": {
    "option_x": false 
  },
  "register_id": 1,
  "worker_id": 1
}
```
Comment:<br>
all ids are uuid
options false for not having something true for extra