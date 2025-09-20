# Flutter Deploy Demo

Um projeto Flutter que demonstra como utilizar **GitHub Actions** para automatizar o processo de build e geração de arquivos necessários para publicação nas lojas de aplicativos móveis.

## 🎯 Objetivo do Projeto

Este projeto tem como finalidade exemplificar na prática como o **GitHub Actions** pode ser configurado e utilizado para:

- **Automatizar builds**: Compilação automática de aplicativos Flutter para Android e iOS
- **Gerar APK e AAB**: Criação dos arquivos necessários para publicação na **Google Play Store**
- **Gerar IPA**: Criação dos arquivos necessários para publicação na **Apple App Store**
- **Deploy automatizado**: Envio dos arquivos compilados via FTP para distribuição

## 🚀 Como Funciona o GitHub Actions

O projeto utiliza workflows automatizados que são executados através do GitHub Actions. O workflow principal (`release.yml`) pode ser disparado manualmente e executa as seguintes etapas:

### Para Android:
1. **Setup do ambiente**: Configura JDK 17 e Flutter 3.35.4
2. **Instalação de dependências**: Executa `flutter pub get`
3. **Build APK**: Gera o arquivo `.apk` para distribuição direta
4. **Build AAB**: Gera o arquivo `.aab` otimizado para Google Play Store
5. **Deploy FTP**: Envia os arquivos para servidor via FTP

### Para iOS:
1. **Setup do ambiente**: Configura Flutter em macOS
2. **Configuração de certificados**: Instala certificados de assinatura de código
3. **Instalação de dependências**: Executa `flutter pub get`
4. **Build IPA**: Gera o arquivo `.ipa` para Apple App Store
5. **Deploy FTP**: Envia o arquivo para servidor via FTP

## 📁 Arquivos Gerados

O workflow gera os seguintes arquivos prontos para publicação:

- **`app-release.apk`**: Arquivo para instalação direta no Android
- **`app-release.aab`**: Arquivo otimizado para Google Play Store
- **`*.ipa`**: Arquivo para publicação na Apple App Store

## ⚙️ Configuração Necessária

Para utilizar este projeto como base, você precisará configurar os seguintes **GitHub Secrets**:

### Para FTP Deploy:
- `FTP_SERVER`: Endereço do servidor FTP
- `FTP_USERNAME`: Usuário do FTP  
- `FTP_PASSWORD`: Senha do FTP

### Para iOS (apenas se for fazer build para iOS):
- `P12_BASE64`: Certificado .p12 codificado em base64
- `P12_PASSWORD`: Senha do certificado P12
- `PROVISIONING_PROFILE_BASE64`: Perfil de provisionamento codificado em base64

## 🛠️ Como Usar

1. **Fork este repositório** para sua conta GitHub ou copie o código do workflow (`release.yml`) para o seu projeto Flutter
2. **Configure os Secrets** necessários nas configurações do repositório
3. **Acesse a aba Actions** do seu repositório
4. **Execute manualmente** o workflow "📱 Compilar e Distribuir Aplicativo"
5. **Aguarde a conclusão** e verifique os arquivos gerados

## 📚 Recursos Adicionais

- [Documentação GitHub Actions](https://docs.github.com/en/actions)
- [Flutter Deployment Guide](https://docs.flutter.dev/deployment)
- [Google Play Console](https://play.google.com/console)
- [Apple App Store Connect](https://appstoreconnect.apple.com)

## 🎓 Aprendizados

- Este projeto demonstra como o GitHub Actions pode simplificar significativamente o processo de deploy de aplicativos Flutter, eliminando a necessidade de builds manuais e automatizando todo o pipeline de distribuição.
- Você pode complementar o workflow com etapas adicionais, como testes automatizados, análise de código, notificações, atualizações de versão, execução automatica ao push ou novas tags, entre outros.