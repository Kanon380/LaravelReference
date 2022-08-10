# Form

### Send
```jsx
import { Inertia } from '@inertiajs/inertia'

const onSubmit = () => {
  Inertia.get('/url', data)
}
```

```jsx
import { Head, Link } from '@inertiajs/inertia-react';

export default function Example () {
  return(
    <Link href={ route('example.index') } method='post' as="button" data={{ uuid: props.res.uuid }}>
      { props.res.name }
    </Link>
  )
}

```

### Validate for react-hook-form
```jsx
import { useForm } from "react-hook-form"

export default function Example () {

  const { register, formState: { errors }, handleSubmit } = useForm({
    defaultValues: {
      name: '',
    }
  })
  const onSubmit = (data) => {
    Inertia.get('/url', data)
  }
  
  return(
    <form onSubmit={ handleSubmit(onSubmit) }>
      <input {...register("name", { required: true })} type="text" />
      { errors.name?.type === 'required' && <p>Name is required.</p> }
      <input {...register("number", { required: true, min: 1, max: 10 })} type="number" />
      { errors.number?.type === 'required' && <p>Name is required.</p> }
      <button type='submit'>Submit</button>
    </form>
  )
}

```
