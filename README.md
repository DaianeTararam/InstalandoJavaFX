## 🎯 Passo a Passo

### 1. Baixar o JavaFX
- Site: https://gluonhq.com/products/javafx/
- Baixe o SDK (Windows x64)
- Extraia para dentro da pasta `lib/` do seu projeto (exemplo: `JavaFX-Projeto/lib`)

### 2. Criar o Arquivo Java
Dentro da pasta `src`, crie um arquivo chamado `Teste.java` com este código:

```java
import javafx.application.Application;
import javafx.scene.Scene;
import javafx.scene.control.Label;
import javafx.scene.layout.StackPane;
import javafx.stage.Stage;

public class Teste extends Application {
    @Override
    public void start(Stage primaryStage) {
        Label label = new Label("Hello, JavaFX!");
        StackPane root = new StackPane(label);
        Scene scene = new Scene(root, 300, 200);
        primaryStage.setScene(scene);
        primaryStage.setTitle("JavaFX App");
        primaryStage.show();
    }

    public static void main(String[] args) {
        launch(args);
    }
}
```

### 3. Configurar o launch.json
Dentro da pasta `.vscode`, crie o arquivo `launch.json` com esse conteúdo:

```json
{
  "version": "0.2.0",
  "configurations": [
    {
      "type": "java",
      "name": "Launch JavaFX",
      "request": "launch",
      "mainClass": "Teste",
      "vmArgs": "--module-path lib --add-modules javafx.controls,javafx.fxml"
    }
  ]
}
```

> ⚠️ Atenção: Verifique se o nome da sua classe principal está certo ("Teste"). Não precisa ser exclusivamente esse nome.

### 4. Compilar e Executar
- Abra o VS Code na pasta do projeto
- Clique em "Run and Debug" (Ctrl + Shift + D)
- Escolha a opção "Launch JavaFX"

Ou use o terminal:
```bash
javac --module-path lib --add-modules javafx.controls,javafx.fxml src/Teste.java
java --module-path lib --add-modules javafx.controls,javafx.fxml -cp src Teste
```

---

Feito com carinho por **Daiane Tararam** ✨🚀
