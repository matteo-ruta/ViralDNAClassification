## Contenuto della repository
- **Dataset**: i dati
- **Models**: modelli fatti e finiti. Se testate qualcosa potete fare in modo che i modelli vengano salvati qui? Almeno non lasciamo file a caso in giro. I path sono già specificati automaticamente nei notebook che ho caricato comunque, basta che copiate quelli
- **Notebooks**: codice sotto forma di notebooks, dovrebbe andare sia su Jupyter che su Colab senza bisogno di specificare path differenti (se runnate in locale in cartelle diverse dalla repo, allora sì). Il notebook con il modello è EnhancedVirusModel.ipynb

## IMPORTANTE
Non so quanto vi convenga fare dei branch se c'avete voglia di fare dei test. L'unica cosa che vi chiedo è di non modificare EnhancedVirusModel.ipynb, ma di copiarlo, modificarlo per i cavoli vostri e poi rinominarlo se lo intendete pushare. Occhio che là ci sta la roba definitiva, non vorrei che ce la perdiamo (in teoria GitHub lo dovrebbe prevenire penso, ma la verità è che non so usarlo così bene, per cui meglio evitare)

## Note sul modello "EVM2_cyclicRate_1conv_Xavier.pth"
- scheduler:
  ```scheduler = torch.optim.lr_scheduler.CyclicLR(optimizer, base_lr=learning_rate, max_lr=learning_rate*100, mode='triangular2')```
- optimizer:
  ```optimizer = torch.optim.Adam(model.parameters(), lr=learning_rate)```
- learning rate: 0.001
- bacth_size = 256
- Xavier initialization for the final linear layer
- one convolutional layer
- Attention block: original
- model declaration:
  ```model = EnhancedVirusModel2(maps=128, hidden=64).to(device)``` 