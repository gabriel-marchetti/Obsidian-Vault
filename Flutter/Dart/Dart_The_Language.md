Dart is a type safe language. It uses type checking to consistently create code.

It has a "sound null safety" which will allow null types only if you explicitly say it. 

```dart
void main(){
	print('Hello, World!');
}
```

Para rodar um código .dart primeiro precisamos criar o ambiente que executaremos o nosso código. Desse modo temos que rodar:

```powershell
dart create -t console cli
```

This will create a structure that consists of a lib and a bin folder that contain a file cli.dart. But will vary based on the name of the application.

To run the code we just need to cd into the directory and run the command.

```
dart run
```

To generate an .exe we can run the

```
dart compile exe bin/cli.dart
```

