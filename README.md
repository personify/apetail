#@petail
easy DSLs with CoffeeScript


apetail wires up keywords prefixed with the ‘@’ to services
within your Agent or exposed by external Agents or libs:

```coffeescript

# app/config/apetail.config

in: personify.service.in
out: personify.service.out
chain: ctrl.chain
foo: @agent.domain.foo

```

```coffeescript
# agent/domain/_services/foo.coffee

@in
    fsPath: @string
@out
  foo: @chain
    1: @foo fsPath
    2: walk  
```  


BUT ‘@’ MEANS ‘this’  in CoffeeScript!
there is no “this”, fuck you