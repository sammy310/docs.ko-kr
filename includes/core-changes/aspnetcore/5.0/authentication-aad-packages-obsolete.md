---
ms.openlocfilehash: 8bcd9987cb061233c8476b9c083a224fc0e25440
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90539508"
---
### <a name="authentication-azureadui-and-azureadb2cui-apis-and-packages-marked-obsolete"></a>인증: AzureAD.UI 및 AzureADB2C.UI API와 패키지는 사용되지 않는 것으로 표시됨

ASP.NET Core 2.1에서 Azure AD(Azure Active Directory) 및 Azure AD B2C(Azure Active Directory B2C) 인증과의 통합은 [Microsoft.AspNetCore.Authentication.AzureAD.UI](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.AzureAD.UI) 및 [Microsoft.AspNetCore.Authentication.AzureADB2C.UI](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.AzureADB2C.UI) 패키지에서 제공됩니다. 이러한 패키지에서 제공되는 기능은 Azure AD v1.0 엔드포인트를 기반으로 합니다.

ASP.NET Core 5.0 이상에서 Azure AD 및 Azure AD B2C 인증과의 통합은 [Microsoft.Identity.Web](https://www.nuget.org/packages/Microsoft.Identity.Web) 패키지에서 제공됩니다. 이 패키지는 Microsoft ID 플랫폼(이전에는 Azure AD v2.0 엔드포인트라고 함)을 기반으로 합니다. 따라서, `Microsoft.AspNetCore.Authentication.AzureAD.UI` 및 `Microsoft.AspNetCore.Authentication.AzureADB2C.UI` 패키지의 이전 API는 더 이상 사용되지 않습니다.

자세한 내용은 GitHub 이슈 [dotnet/aspnetcore#25807](https://github.com/dotnet/aspnetcore/issues/25807)을 참조하세요.

#### <a name="version-introduced"></a>도입된 버전

5.0 미리 보기 8

#### <a name="old-behavior"></a>이전 동작

해당 API는 사용되지 않는 것으로 표시되지 않았습니다.

#### <a name="new-behavior"></a>새 동작

해당 API는 사용되지 않는 것으로 표시됩니다.

#### <a name="reason-for-change"></a>변경 이유

Azure AD 및 Azure AD B2C 인증 기능은 `Microsoft.Identity.Web`에서 제공하는 Microsoft 인증 라이브러리(MSAL) API로 마이그레이션되었습니다.

#### <a name="recommended-action"></a>권장 조치

[웹앱](https://github.com/azuread/microsoft-identity-web/wiki/web-apps) 및 [웹 API](https://github.com/azuread/microsoft-identity-web/wiki/web-apis)에 대한 `Microsoft.Identity.Web` API 지침을 따르세요.

#### <a name="category"></a>범주

ASP.NET Core

#### <a name="affected-apis"></a>영향을 받는 API

* [Microsoft.AspNetCore.Authentication.AzureADAuthenticationBuilderExtensions](/dotnet/api/microsoft.aspnetcore.authentication.azureadauthenticationbuilderextensions?view=aspnetcore-3.0)
* [Microsoft.AspNetCore.Authentication.AzureAD.UI.AzureADDefaults](/dotnet/api/microsoft.aspnetcore.authentication.azuread.ui.azureaddefaults?view=aspnetcore-3.0)
* [Microsoft.AspNetCore.Authentication.AzureAD.UI.AzureADOptions](/dotnet/api/microsoft.aspnetcore.authentication.azuread.ui.azureadoptions?view=aspnetcore-3.0)
* [Microsoft.AspNetCore.Authentication.AzureADB2CAuthenticationBuilderExtensions](/dotnet/api/microsoft.aspnetcore.authentication.azureadb2cauthenticationbuilderextensions?view=aspnetcore-3.0)
* [Microsoft.AspNetCore.Authentication.AzureADB2C.UI.AzureADB2CDefaults](/dotnet/api/microsoft.aspnetcore.authentication.azureadb2c.ui.azureadb2cdefaults?view=aspnetcore-3.0)
* [Microsoft.AspNetCore.Authentication.AzureADB2C.UI.AzureADB2COptions](/dotnet/api/microsoft.aspnetcore.authentication.azureadb2c.ui.azureadb2coptions?view=aspnetcore-3.0)

<!--

#### Affected APIs

- `T:Microsoft.AspNetCore.Authentication.AzureADAuthenticationBuilderExtensions`
- `T:Microsoft.AspNetCore.Authentication.AzureAD.UI.AzureADDefaults`
- `T:Microsoft.AspNetCore.Authentication.AzureAD.UI.AzureADOptions`
- `T:Microsoft.AspNetCore.Authentication.AzureADB2CAuthenticationBuilderExtensions`
- `T:Microsoft.AspNetCore.Authentication.AzureADB2C.UI.AzureADB2CDefaults`
- `T:Microsoft.AspNetCore.Authentication.AzureADB2C.UI.AzureADB2COptions`

-->
