Comandos executados:

Iniciando o projeto:

`composer create-project --prefer-dist laravel/laravel projeto_exemplo`

---
`php artisan make:model Aluno --migration`
```
app\Aluno.php
database\migrations\2019_11_21_222412_create_alunos_table.php
```

`php artisan make:model Instituicao --migration`
```
app\Instituicao.php
database\migrations\2019_11_21_222418_create_instituicaos_table.php
```

`php artisan make:model Curso --migration`
```
app\Curso.php
database\migrations\2019_11_21_222425_create_cursos_table.php
```
---
`php artisan make:controller AlunoController --resource`
```
app\Http\Controllers\AlunoController.php
```

`php artisan make:controller InstituicaoController --resource`
```
app\Http\Controllers\InstituicaoController.php
```

`php artisan make:controller CursoController --resource`
```
app\Http\Controllers\CursoController.php
```
---
No `routes\web.php`:

```
Route::resources([
    'alunos' => 'AlunoController',
    'instituicoes' => 'InstituicaoController',
    'cursos' => 'CursoController',
]);
```

`php artisan route:list`

```
+--------+-----------+--------------------------------+----------------------+----------------------------------------------------+--------------+
| Domain | Method    | URI                            | Name                 | Action                                             | Middleware   |
+--------+-----------+--------------------------------+----------------------+----------------------------------------------------+--------------+
|        | GET|HEAD  | /                              |                      | Closure                                            | web          |
|        | GET|HEAD  | alunos                         | alunos.index         | App\Http\Controllers\AlunoController@index         | web          |
|        | POST      | alunos                         | alunos.store         | App\Http\Controllers\AlunoController@store         | web          |
|        | GET|HEAD  | alunos/create                  | alunos.create        | App\Http\Controllers\AlunoController@create        | web          |
|        | GET|HEAD  | alunos/{aluno}                 | alunos.show          | App\Http\Controllers\AlunoController@show          | web          |
|        | PUT|PATCH | alunos/{aluno}                 | alunos.update        | App\Http\Controllers\AlunoController@update        | web          |
|        | DELETE    | alunos/{aluno}                 | alunos.destroy       | App\Http\Controllers\AlunoController@destroy       | web          |
|        | GET|HEAD  | alunos/{aluno}/edit            | alunos.edit          | App\Http\Controllers\AlunoController@edit          | web          |
|        | GET|HEAD  | api/user                       |                      | Closure                                            | api,auth:api |
|        | GET|HEAD  | cursos                         | cursos.index         | App\Http\Controllers\CursoController@index         | web          |
|        | POST      | cursos                         | cursos.store         | App\Http\Controllers\CursoController@store         | web          |
|        | GET|HEAD  | cursos/create                  | cursos.create        | App\Http\Controllers\CursoController@create        | web          |
|        | PUT|PATCH | cursos/{curso}                 | cursos.update        | App\Http\Controllers\CursoController@update        | web          |
|        | GET|HEAD  | cursos/{curso}                 | cursos.show          | App\Http\Controllers\CursoController@show          | web          |
|        | DELETE    | cursos/{curso}                 | cursos.destroy       | App\Http\Controllers\CursoController@destroy       | web          |
|        | GET|HEAD  | cursos/{curso}/edit            | cursos.edit          | App\Http\Controllers\CursoController@edit          | web          |
|        | GET|HEAD  | instituicoes                   | instituicoes.index   | App\Http\Controllers\InstituicaoController@index   | web          |
|        | POST      | instituicoes                   | instituicoes.store   | App\Http\Controllers\InstituicaoController@store   | web          |
|        | GET|HEAD  | instituicoes/create            | instituicoes.create  | App\Http\Controllers\InstituicaoController@create  | web          |
|        | DELETE    | instituicoes/{instituico}      | instituicoes.destroy | App\Http\Controllers\InstituicaoController@destroy | web          |
|        | PUT|PATCH | instituicoes/{instituico}      | instituicoes.update  | App\Http\Controllers\InstituicaoController@update  | web          |
|        | GET|HEAD  | instituicoes/{instituico}      | instituicoes.show    | App\Http\Controllers\InstituicaoController@show    | web          |
|        | GET|HEAD  | instituicoes/{instituico}/edit | instituicoes.edit    | App\Http\Controllers\InstituicaoController@edit    | web          |
+--------+-----------+--------------------------------+----------------------+----------------------------------------------------+--------------+
```