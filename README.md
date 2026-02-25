# Keycloak QQ Identity Provider

QQ OAuth2 Identity Provider for Keycloak 26.x.

This project provides a custom Identity Provider (IdP) implementation that enables QQ login support for Keycloak using OAuth2.

> Built as a Keycloak SPI extension — no modification to Keycloak source code required.

## ✨ Features

- ✅ QQ OAuth2 login support
- ✅ Works with Keycloak 26.x
- ✅ SPI-based extension
- ✅ Production-ready Maven build
- ✅ Apache License 2.0

## 📦 Compatibility

| Component | Version |
|------------|----------|
| Keycloak | 26.x |
| Java | 17 |
| Maven | 3.8+ |

## 🏗 Project Structure

This project implements a custom Identity Provider using the Keycloak SPI:

- `QQIdentityProvider`
- `QQIdentityProviderFactory`
- `QQIdentityProviderConfig`

It extends:

```

org.keycloak.broker.oidc.AbstractOAuth2IdentityProvider

```

## 🚀 Installation

### 1️⃣ Download Release

Download the latest `.jar` file from GitHub Releases.

### 2️⃣ Copy to Keycloak

Place the jar file into:

```

/opt/keycloak/providers/

````

(Or your custom Keycloak installation providers directory)

### 3️⃣ Build Keycloak

Run:

```bash
bin/kc.sh build
````

### 4️⃣ Restart Keycloak

```bash
bin/kc.sh start
```

## ⚙ Configuration

After restarting Keycloak:

1. Open **Admin Console**
2. Go to **Identity Providers**
3. Click **Add provider**
4. Select **QQ**
5. Configure:

| Field             | Value                                                                              |
| ----------------- | ---------------------------------------------------------------------------------- |
| Client ID         | QQ App ID                                                                          |
| Client Secret     | QQ App Secret                                                                      |

Save configuration.

## 🔐 QQ Developer Setup

1. Register application at QQ Open Platform
2. Obtain:

   * App ID
   * App Key
3. Configure callback URL:

```
https://your-domain/realms/{realm}/broker/qq/endpoint
```

## 🛠 Build From Source

Clone repository:

```bash
git clone https://github.com/Trashblazer/keycloak-identity-provider.git
cd keycloak-identity-provider
```

Build:

```bash
mvn clean verify
```

Package:

```bash
mvn clean package
```

The jar file will be located in:

```
target/
```

## 📄 License

Licensed under the Apache License, Version 2.0.

See the [LICENSE](LICENSE) file for details.

## 🤝 Contributing

Contributions are welcome.

Before submitting a PR:

* Ensure Java 17 compatibility
* Ensure `mvn verify` passes
* Ensure license headers are present
* Follow standard Keycloak SPI patterns

## ⚠ Disclaimer

This project is not affiliated with or endorsed by Keycloak.

Keycloak is a registered trademark of Red Hat.
