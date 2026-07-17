# Forms

O Angular oferece duas abordagens para trabalhar com formulários: `Template-Driven Forms` (formulários orientados por template) e `Reactive Forms`.

## Índice

- [Template-Driven Forms](#template-driven-forms)
- [Reactive Forms](#reactive-forms)
- [FormBuilder](#usando-formbuilder-mais-limpo)
- [FormArray](#formarray-listas-dinâmicas)

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

## Reactive Forms

- Abordagem mais robusta e escaável.
- Lógica fica no TypeScript.
- HTML mais limpo.
- Recomendada para formulários complexos, testes e formulários dinâmicos.

**Setup**: importe `ReactiveFormsModule`.

```
import { ReactiveFormsModule } from '@angular/forms';
import { FormGroup, FormControl, Validators } from '@angular/forms';

@Component({
    standalone:true,
    imports: [ReactiveFormsModule],
    // ...
})
export class MeuFormularioComponent {
    meuForm = new FormGroup({
        nome: new FormControl('', [Validators.required, Validators.minLenght(3)]),
        email: new FormControl('', [Validators.required, Validators.email]),
    });

    onSubmit() {
        console.log(this.meuForm.value);
    }
}
```
`meu-formulario.ts`

```
<form [formGroup]="meuForm" (ngSubmit)="onSubmit()">
    <input formControlName="nome" />

    @if (meuForm.get('nome')?.invalid && meuForm.get('nome')?.touched) {
        <div>
            Nome é obrigatório (mín. 3 caracteres)
        </div>
    }

    <input formControlName="email" />

    <button [disabled]="meuForm.invalid">Enviar</button>
</form>
```
`meu-formulario.html`

## Usando FormBuilder (mais limpo)

```
import { FormBuilder, Validators } from '@angular/forms';

export class MeuFormularioComponent {
    private formBuilder = inject(FormBuilder);

    meuForm = this.formBuilder.group({
        nome: ['', [validators.required, Validators.minLenght(3)]],
        email: ['', [Validators.required, Validators.email]],
    })
}
```
`meu-formulario.ts`