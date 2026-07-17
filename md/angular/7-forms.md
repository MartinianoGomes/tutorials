# Forms

O Angular oferece duas abordagens para trabalhar com formulários: [`Template-Driven Forms`](#template-driven-forms) (formulários orientados por template) e [`Reactive Forms`](#reactive-forms) (formulários reativos).

## Template-Driven Forms

- Abordagem mais simples.
- A lógica fica principalmente no HTML.
- Recomendado para formulários simples.

**Setup**: importe o `FormsModule` no seu módulo (ou no `imports` do componente standalone).

Exemplo:

```
import { FormsModule } from '@angular/forms';

@Component({
    standalone: true,
    imports: [FormsModule],
    // ...
})
export class MeuFormularioComponent {
    usuario = {
        nome: '',
        email: ''
    };

    onSubmit() {
        console.log(this.usuario);
    }
}
```
`meu-formulario.ts`

```
<form #meuForm="ngForm" (ngSubmit)="onSubmit()">
    <input
        name="nome"
        [(ngModel)]="usuario.nome"
        required
        minlength="3"
        #nome="ngModel"
    />

    @if (nome.invalid && nome.touched) {
        <div>
        Nome é obrigatório (mín. 3 caracteres)</div>
    }

    <inpurt
        name="email"
        [(ngModel)]="usuario.email"
        required
        email
    />

    <button [disabled]="meuForm.invalid">Enviar</button>
</form>
```
`meu-formulario.html`