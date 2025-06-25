# Flutter Extract to ARB 
[![Visual Studio Marketplace Version](https://img.shields.io/visual-studio-marketplace/v/zealousFoundry.flutter-extract-to-arb?label=Version)](https://marketplace.visualstudio.com/items?itemName=zealousFoundry.flutter-extract-to-arb)
[![Visual Studio Marketplace Downloads](https://img.shields.io/visual-studio-marketplace/d/zealousFoundry.flutter-extract-to-arb?label=VS%20Marketplace%20Downloads)](https://marketplace.visualstudio.com/items?itemName=zealousFoundry.flutter-extract-to-arb)
[![Open VSX Downloads](https://img.shields.io/open-vsx/dt/zealousfoundry/flutter-extract-to-arb?label=Open%20VSX%20Downloads)](https://open-vsx.org/extension/ZealousFoundry/flutter-extract-to-arb)

## 🔗 Links

Download the extension from the [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=zealousFoundry.flutter-extract-to-arb) or the [Open VSX Registry](https://open-vsx.org/extension/ZealousFoundry/flutter-extract-to-arb)

If you want to add a feature or file a bug, please open an issue on the [GitHub repository](https://github.com/tempo-riz/flutter-extract-to-arb-vscode)


## 💡 Code Action

- **Extract String to ARB** : Right-click a string (or quick fix it with `⌘.` / `Ctrl+.`) and select "Extract String to ARB".

<img src="https://github.com/tempo-riz/flutter-extract-to-arb-vscode/blob/049cb13ef79d7209b9ec8716cf471af803476dc2/demo/demo-action.gif?raw=true" width="1000"/>


## ⚡️ Commands (Premium Features)

🛒 *Premium only*: Requires a valid license key. [Buy one for $14.90 →](https://your-buy-link.com "Purchase a license to unlock premium features")


Access from the Command Palette (`⇧⌘P` / `Ctrl+Shift+P`):

- **Extract Texts (Current File)** : Extracts all `Text()` widget strings in the current Dart file to your ARB files.

- **Extract Texts (Project)** : Extracts all `Text()` widget strings from the `lib/` folder to your ARB files.


<img src="https://github.com/tempo-riz/flutter-extract-to-arb-vscode/blob/049cb13ef79d7209b9ec8716cf471af803476dc2/demo/demo-file.gif?raw=true" width="1000"/>

## 🚀 Getting Started (Auto Setup)

Access from the Command Palette (`⇧⌘P` / `Ctrl+Shift+P`):

**Setup Localization for Project** : 
  Sets up all necessary files for localization in your Flutter project, including `l10n.yaml`, `pubspec.yaml` and `arb` files.

<img src="https://github.com/tempo-riz/flutter-extract-to-arb-vscode/blob/ff1e41f908f57a950fe457fee54c13c732b0ca19/demo/demo-setup.gif?raw=true" width="1000"/>

## 🔧 Manual Setup (I recommend using the setup command instead)

You should already have a `l10n.yaml` file in your project. If not, create one.  
This extension uses Flutter's official options for internationalization. See [Flutter's i18n docs](https://docs.flutter.dev/ui/accessibility-and-internationalization/internationalization#configuring-the-l10n-yaml-file)

The extension also supports additional options:

### Extension-specific `l10n.yaml` options (with defaults)
```yaml
# Enable translation (via DeepL)
translate: true              

# Auto-run flutter gen-l10n after extraction              
generate: true       

# Key prefix for translations             
key-prefix: AppLocalizations.of(context)!.  

# Generate key name
# "ask" = Prompt with a suggested key name, true = infer from text, false = prompt manually  
auto-name-key: true       

# Language to use for key name generation                 
key-name-language: en       

# Import line to insert if needed                
import-line: ""                             
```


For translation to work, you need to add your Deepl API key in vscode settings.json file (`⇧⌘P` / `Ctrl+Shift+P` → `Preferences: Open User Settings (JSON)`):

`"flutter.deeplApiKey": "your-key",`   

You can get a generous free API key [here](https://www.deepl.com/en/pro#developer)

Finally, make sure `generate: true` is set in your `pubspec.yaml`:

```yaml
flutter:
  generate: true # <---
```

And that's it! You're ready to go 🚀


## 😎 Pro tips
You can define an extension getter to access your translations more concisely:
```dart
extension ContextExt on BuildContext {
  AppLocalizations get t => AppLocalizations.of(this);
}

// then instead of this
Text(AppLocalizations.of(context).yourKey)

// use it like this:
Text(context.t.yourKey)
```
Don't forget to update the `key-prefix` & `import-line` options in l10n.yaml ;)



## ☕ Support

If you'd like to support this project, consider contributing [here](https://github.com/sponsors/tempo-riz). Thank you! :)