# Cofoundry.Plugins.Mail.MailKit

[![Build status](https://ci.appveyor.com/api/projects/status/neoc6yy7ed64td14?svg=true)](https://ci.appveyor.com/project/Cofoundry/Cofoundry.Plugins.Mail.MailKit)
[![NuGet](https://img.shields.io/nuget/v/Cofoundry.Plugins.Mail.MailKit.svg)](https://www.nuget.org/packages/Cofoundry.Plugins.Mail.MailKit/)
[![Gitter](https://img.shields.io/gitter/room/cofoundry-cms/cofoundry.svg)](https://gitter.im/cofoundry-cms/cofoundry)


This library is a plugin for [Cofoundry](https://www.cofoundry.org). For more information on getting started with Cofoundry check out the [Cofoundry repository](https://github.com/cofoundry-cms/cofoundry).

## Overview

This library allows you to send mail using the cross platform [MailKit](https://github.com/jstedfast/MailKit) library. By referencing this package your Cofoundry project will automatically replace the default `IMailDispatchService` implementation with one that uses MailKit. Use the following settings to configure the service:

- *Cofoundry:Plugins:MailKit:Host* Host address of the smtp server to connect with. Defaults to localhost.
- *Cofoundry:Plugins:MailKit:Port* The port to connect to the smtp server on. Defaults to 25.
- *Cofoundry:Plugins:MailKit:EnableSsl* Indicates whether ssl should be used to connect to the host.
- *Cofoundry:Plugins:MailKit:UserName* The user name to authenticate with the smtp server. If left empty then no auth will be used.
- *Cofoundry:Plugins:MailKit:Password* The password use when authenticating with the smtp server.
- *Cofoundry:Plugins:MailKit:CertificateValidationMode* Used to configure how the ssl certificate is validated. `Default` uses the default MailKit validator, which allows valid certificates and self-signed certificates with an untrusted root. `All` ignores all certificate errors. `ValidOnly` allows only valid certificates without errors.
- *Cofoundry:Plugins:MailKit:Disabled* Indicates whether the plugin should be disabled, which means services will not be bootstrapped. Defaults to false.


## Custom Connection Configuration

For more control over how MailKit initializes and connects to the smtp host you can override the default `ISmtpClientConnectionConfiguration` implementation using the [Cofoundry DI system](https://github.com/cofoundry-cms/cofoundry/wiki/Dependency-Injection#overriding-registrations).