## Workflow in rails with migrations

* Crear una migración 

```sh
rails g migration CreateProducts name:string part_number:string
```

* Agregar columnas a un modelo 

```sh
rails g migration AddPartNumberToProducts part_number:string:index
```

* Remover Columnas 

```sh
rails g migration RemovePartNumberFromProducts part_number:string

```

* Agregar relaciones

```sh
rails g migration AddUserRefToProducts user:references
```

* Crear un modelo con migraciones

```sh
rails generate model Product name:string description:text
```

Note: Documentación http://guides.rubyonrails.org/active_record_migrations.html
