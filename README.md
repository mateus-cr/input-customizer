## InputCustomizer
TODO

## Instação
```
composer require brenofortunato/input-customizer
```
# PublicarVendor
```
php artisan vendor:publish --tag=brenofortunato\input-customizer\InputCustomizerServiceProvider  
```

1. Na view onde deseja utilizar as máscaras, por exemplo "layouts/app.blade.php", adicione ao final da tag head:
```
<head>
    ...
    @include('vendor.input-customizer.all')
    @stack('css')
</head>
```
E ao final da tag body:
```
<body>
    ...
    @stack('scripts')
</body>
```
**Certifique-se de que o jQuery esteja presente no body!**

2. Para verificar quais máscaras estão disponíveis, bem como criar novas, acesse o arquivo em:
```
/views/vendor/input-customizer/all.blade.php
```

3. Para aplicar uma máscara, basta adicioná-la como classe ao input, por exemplo:
```
<input class="form-control money-mask" name="price" type="text">
```
Ou em blade:
```
{!! Form::text('price', null, ['class' => 'form-control money-mask']) !!}
```
**O input deve ser do tipo "text" para a máscara funcionar.**