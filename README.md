JSON Validator Specification
===============================

The **JSON Validator** is field validator.
It's able to use backend and frontend on the same project, you only need write once spec.


The validation spec can write this when you need update a user.
```js
{
  definitions:{
    User:{
      properties:{
        id:{
          types:["string"],
          required:true
        },
        name:{
          types:["string"],
          required:true
        },
        sex:{
          types:["string"],
          enum:["man","woman","other"]
        }
      }
    }
  }
}
```

## Validatior scheme

|name             |type             |description                                                                              |
|-----------------|-----------------|-----------------------------------------------------------------------------------------|
|definitions      |object           |This attribute is to define models,it's able to set validation rules.                    |

## Model scheme

|name             |type             |description                                                                              |
|-----------------|-----------------|-----------------------------------------------------------------------------------------|
|properties       |object           |This is field scheme, it's able to help to define field requirements.                    |

## Property scheme

|name                  |type             |default  |description                                                                                                                                          |
|----------------------|-----------------|---------|-----------------------------------------------------------------------------------------------------------------------------------------------------|
|types                 |array[string]    |         |Be able to use field type. The value must be one of `"string"`, `"number"`, `"integer"`, `"boolean"`, `"object"`, or `"array"`.                      |
|required              |boolean          |false    |The field is required if value is true.                                                                                                              |
|enum                  |array            |         |Be able to use values.                                                                                                                               |
|properties            |object           |         |Add subset properties, the `types` field is only support `object` and `array`.                                                                       |

