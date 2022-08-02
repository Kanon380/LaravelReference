# Form

### Send
```jsx
import { Inertia } from '@inertiajs/inertia'

const onSubmit = () => {
  Inertia.get('/url', data)
}
```

### validate
```jsx
import { useForm } from "react-hook-form"

export default function Example () {

  const { register, formState: { errors }, handleSubmit } = useForm({
    defaultValues: {
      name: '',
    }
  })
  
  return(
    <form onSubmit={ handleSubmit(onSubmit) }>
      <input {...register("name", { required: true })} type="text" />
      <button type='submit'>Submit</button>
      {
        errors.product?.type === 'required' &&
        <p>
          Name is required.
        </p>
      }
    </form>
  )
}

```
