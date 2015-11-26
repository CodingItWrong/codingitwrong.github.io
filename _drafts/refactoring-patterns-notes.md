More from Help Me talk.

- Query Objects
- Value Objects: no one talks about this much, probably because ActiveRecord makes it hard.
- Policy Objects: for reads, especially permissions checks
- Draper-style Decorator: additional display logic related to a model, instead of in helpers
- View Objects: Multiple models out. Many in the Rails community call this a Presenter. Multiple models. View display logic not directly related to one model.


- Form Objects: Multiple models in. Laravel calls these FormRequests. Jay Fields calls this a Presenter. Can also use for form-specific conditional validation; model validation is just the core. Example is password/conf. Good alternative to accepts-nested-attributes.
- General Decorator: wrap a model with secondary effects, instead of callbacks.
- Service Objects: BNR says use for more complex effects instead of callbacks. Especially if coordinating external services like payment. Laravel calls these jobs. Also called command handlers.
- Events: a more indirect way to call secondary effects.

BUILT-IN
- Validators: if you're really submitting just one thing, but you need to check something complex, you can write really complex ones
- Concerns: things that actually belong in the model, but are grouped together for readability.
- Callbacks: BNR says use for data integrity only, not secondary effects.

DISPLAY LOGIC
- View: just markup output. For real.
- View model: model-agnostic display logic
- Draper decorator: model-specific display logic
- Value objects: field-specific display logic
- Model

SECONDARY EFFECTS
- Form object: if have secondary effects, probably better to call it a service object.
- General decorator: secondary effects wrapped around model. Knowledge of effects in caller, not always fired.
- Service object: secondary effects in independent class; an active job is a category of this. Knowledge of effects in independent class, but caller needs to know about it in the abstract, so not always fired. Could coordinate general decorators.
- Events: secondary effects originating from model, bound outside of model. Always fired, but knowledge of effects not coupled to model OR caller.
- Callbacks: secondary effects IN model. BNR says just for internal stuff, like data consistency. Always fired, knowledge of effects in model.

- Concerns: separate module, included in same model; for related domains; could include callbacks, events, validators, value objects. Just a way for organizing built-in or external patterns within model itself.
- Validators
- Model