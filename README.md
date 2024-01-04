# Manipulando Fluxo no Angular

## Pipes

> Funções simples para usar em template expressions para aceitar um valor de entrada e retornar esse valor transformado.

O Angular já possui _[pipes](https://angular.io/api/common#pipes)_ incorporados:

- `DatePipe`
- `UpperCasePipe`
- `LowerCasePipe`
- `CurrencyPipe`
- `DecimalPipe`
- `PercentPipe`
- `AsyncPipe`
- `JsonPipe`

```html
{{ data | date:'hh:mm:ss' }}
```

```html
{{ texto | uppercase }}
```

```html
{{ valor | currency:'USD' }}
```

```html
<div>{{ valor | async | uppercase }}</div>
```

### Pipes Customizados

`ng g p pipes/exemplo`

```typescript
import { Pipe, PipeTransform } from '@angular/core';

@Pipe({
  name: 'hash',
})
export class HashPipe implements PipeTransform {

  transform(value: string, options?: any): string {
    return CryptoJS.MD5(value).toString();
  }

}
```

Utilização:

```html
<div>{{ texto | hash }}</div>
```

## Guards

> Classes especiais para controlar o fluxo de navegação de umma aplicação.

`ng g g guards/auth`

## Projetos

- [Criando um Clone do BuzzFeed com Angular](https://github.com/Err0rGCeni/DIOProject_BuzzQuizzNG)
