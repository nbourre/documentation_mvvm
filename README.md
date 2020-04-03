# Workflow – MVVM

Ici, je présente mon « flux de production » que j&#39;utilise lorsque je veux faire des applications simples en utilisant le MVVM.

# Code – App

Modifier App.xaml.cs

- Ajouter un constructeur App().
- Ajouter un membre pour la fenêtre principale
- Instancier dans le constructeur la fenêtre principale et montrer celle-ci.

```csharp
public partial class App : Application
{
    MainWindow _wnd;

    public App()
    {
        _wnd = new MainWindow();
        _wnd.Show();
    }
}
```

Modifier App.xaml en supprimant StartupURI

# Code – ViewModel

- Création d'un dossier « ViewModels » dans la structure du projet
  - On ajoute tous les ViewModels ici.
- Créer une classe BaseViewModel qui implémente INotifyPropertyChanged
  - Tous les ViewModels devront hériter de cette classe.
- Créer le ViewModel désiré
  - Faire hériter celui-ci de BaseViewModel
- Ajouter les propriétés que l&#39;on désire afficher dans l&#39;interface
  - Lorsque nécessaire, ne pas oublier de notifier la modification de propriété.
  - Exemple : Nom, Prénom et ObservableCollection

# Code – MainWindow

## Interface

- Déterminer ce que je veux présenter à l&#39;utilisateur.
- Faire une maquette approximative de l&#39;application.

## Code-behind

- Dans le constructeur, indiquer au DataContext le ViewModel que l&#39;on veut associer.
- Réaliser les bindings nécessaire dans le XAML.

## Commands
- Récupérer la classe DelegateCommand
- Déterminer les commandes nécessaires pour l'interface
