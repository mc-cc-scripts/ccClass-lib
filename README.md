# ccClass-lib

## Simulates Class Instances for Lua

> Returns only the class, not in instance of it!
>
> Init by _classname_(), which returns an Instance of the class!

# Exampe

```lua
require 'class'

-- definition of classes
Animal = class(function(a,name)
   a.name = name
end)

function Animal:__tostring()
  return self.name..': '..self:speak()
end

Cat = class(Animal, function(c,name,breed)
         Animal.init(c,name)  -- must init base!
         c.breed = breed
      end)

function Cat:speak()
  return 'meow'
end

Lion = class(Cat)

function Lion:speak()
  return 'roar'
end
```

```lua
-- init of class

local BigCat = Lion('Leo', 'African')
print(Leo)
--- "Leo: roar"

print(BigCat:is_a(Cat))
--- "true"
```

Source: http://lua-users.org/wiki/SimpleLuaClasses
