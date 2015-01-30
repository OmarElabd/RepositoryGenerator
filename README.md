# Repository Generator

Repository Generator will generate an entire repository structure for you. All you need to supply a namespace which contains all your Entity Framework models and the RepositoryGenerator.tt will generate repositories for all your models, it will generate a generic repository providing you with basic functionality out of the box. A Unit of Work class will also be generated.

#Usage

Modify the RepositoryGenerator.tt file, replace the line:

```csharp
string targetNamespace = "(ENTER THE FULL NAMESPACE TO YOUR MODELS)";
```

with your the fully qualified namespace to your entity framework models. If your DbContext class
is not in this namespace please also modify this line:

```csharp
string efContext = "DefaultModel";
```

replace DefaultModel with the name of the class that implements the DbContext class.

#Extending the Repository

All your repositories will inherit from Repository<T> which contains generic methods, feel free
to override any methods. To add new repository methods, please add them to the I(ClassName)Repository
interface and implement them in the (ClassName)Repository.
