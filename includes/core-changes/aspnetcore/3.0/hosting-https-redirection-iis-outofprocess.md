---
ms.openlocfilehash: eb3fa768a491f6c0ff4b15479beabd71b0670338
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937288"
---
### <a name="hosting-https-redirection-enabled-for-iis-out-of-process-apps"></a>호스팅: IIS Out of Process 앱에 대해 HTTPS 리디렉션 사용

IIS Out of Process를 통해 호스팅하기 위한 [ASP.NET Core 모듈(ANCM)](/aspnet/core/host-and-deploy/aspnet-core-module)의 버전 13.0.19218.0은 ASP.NET Core 3.0 및 2.2 앱에 대한 기존 HTTPS 리디렉션 기능을 사용하도록 설정합니다.

토론은 [dotnet/AspNetCore#15243](https://github.com/dotnet/AspNetCore/issues/15243)을 참조하세요.

#### <a name="version-introduced"></a>도입된 버전

3.0

#### <a name="old-behavior"></a>이전 동작

ASP.NET Core 2.1 프로젝트 템플릿은 먼저 <xref:Microsoft.AspNetCore.Builder.HttpsPolicyBuilderExtensions.UseHttpsRedirection%2A> 및 <xref:Microsoft.AspNetCore.Builder.HstsBuilderExtensions.UseHsts%2A>와 같은 HTTPS 미들웨어 메서드에 대한 지원을 도입했습니다. 개발 중인 앱은 기본 포트 443을 사용하지 않으므로 HTTPS 리디렉션을 사용하도록 설정하려면 구성을 추가해야 합니다. [HSTS(HTTP Strict Transport Security)](https://cheatsheetseries.owasp.org/cheatsheets/HTTP_Strict_Transport_Security_Cheat_Sheet.html)는 요청이 HTTPS를 이미 사용하고 있을 경우에만 활성화됩니다. localhost는 기본적으로 생략됩니다.

#### <a name="new-behavior"></a>새 동작

ASP.NET Core 3.0에서 IIS HTTPS 시나리오는 [향상](https://github.com/dotnet/AspNetCore/pull/4685)되었습니다. 향상된 기능을 사용하면 앱이 서버의 HTTPS 포트를 검색하고 기본적으로 `UseHttpsRedirection` 작업을 수행할 수 있습니다. In Process 구성 요소는 `IServerAddresses` 기능을 사용하여 포트 검색을 완료했습니다. In Process 라이브러리가 프레임워크를 통해 버전이 지정되었기 때문에 이 기능은 ASP.NET Core 3.0 앱에만 영향을 줍니다. `ASPNETCORE_HTTPS_PORT` 환경 변수를 자동으로 추가하도록 Out of Process 구성 요소가 변경되었습니다. Out of Process 구성 요소가 전역적으로 공유되기 때문에 이 변경은 ASP.NET Core 2.2 및 3.0 앱 모두에 영향을 미쳤습니다. ASP.NET Core 2.1 앱은 기본적으로 이전 버전의 버전을 ANCM을 사용하므로 영향을 받지 않습니다.

ASP.NET Core 3.0.1과 3.1.0 Preview 3에서 이전 동작을 수정하여 ASP.NET Core 2.x의 동작 변경을 되돌립니다. 해당 변경 내용은 IIS Out of Process 앱에만 영향을 줍니다.

위에서 설명한 대로 ASP.NET Core 3.0.0을 설치하면 ASP.NET Core 2.x 앱에서 `UseHttpsRedirection` 미들웨어도 활성화되는 부작용이 있었습니다. ASP.NET Core 3.0.1 및 3.1.0 Preview 3을 설치해도 ASP.NET Core 2.x 앱에 더 이상 영향을 주지 않도록 변경되었습니다. ASP.NET Corea 3.0.0에서 ANCM이 채운 `ASPNETCORE_HTTPS_PORT` 환경 변수가 ASP.NET Core 3.0.1 및 3.1.0 Preview 3의 `ASPNETCORE_ANCM_HTTPS_PORT`로 변경되었습니다. `UseHttpsRedirection`는 새로운 변수와 이전 변수를 모두 이해하기 위해 이 릴리스에서도 업데이트되었습니다. ASP.NET Core 2.x는 업데이트되지 않습니다. 그 결과, 기본적으로 사용하지 않도록 설정된 이전 동작으로 돌아갑니다.

#### <a name="reason-for-change"></a>변경 이유

ASP.NET Core 3.0 기능이 향상되었습니다.

#### <a name="recommended-action"></a>권장 조치

모든 클라이언트가 HTTPS를 사용하도록 하려면 작업이 필요 없습니다. 일부 클라이언트가 HTTPS를 사용하도록 허용하려면 다음 단계 중 하나를 수행합니다.

* 프로젝트의 `Startup.Configure` 메서드에서 `UseHttpsRedirection` 및 `UseHsts`에 대한 호출을 제거하고 앱을 다시 배포하세요.
* *web.config* 파일에서 `ASPNETCORE_HTTPS_PORT` 환경 변수를 빈 문자열로 설정하세요. 변경은 앱을 다시 배포하지 않고 서버에서 직접 발생할 수 있습니다. 예:

    ```xml
    <aspNetCore processPath="dotnet" arguments=".\WebApplication3.dll" stdoutLogEnabled="false" stdoutLogFile="\\?\%home%\LogFiles\stdout" >
        <environmentVariables>
        <environmentVariable name="ASPNETCORE_HTTPS_PORT" value="" />
        </environmentVariables>
    </aspNetCore>
    ```

`UseHttpsRedirection`은 여전히 다음이 될 수 있습니다.

* `ASPNETCORE_HTTPS_PORT` 환경 변수를 적절한 포트 번호(대부분의 프로덕션 시나리오에서 443)로 설정하여 ASP.NET Core 2.x에서 수동으로 활성화했습니다.
* 빈 문자열 값으로 `ASPNETCORE_ANCM_HTTPS_PORT`를 정의하여 ASP.NET Core 3.x에서 비활성화했습니다. 이 값은 앞의 `ASPNETCORE_HTTPS_PORT` 예제와 동일한 방식으로 설정됩니다.

ASP.NET Core 3.0.0 앱을 실행하는 컴퓨터는 ASP.NET Core 3.1.0 Preview 3 ANCM을 설치하기 전에 ASP.NET Core 3.0.1 런타임을 설치해야 합니다. 이렇게 하면 `UseHttpsRedirection`이 ASP.NET Core 3.0 앱에 대해 예상대로 작동합니다.

Azure App Service에서는 ANCM이 전역 특성 때문에 런타임과 별도의 일정으로 배포됩니다. ANCM은 ASP.NET Core 3.0.1 및 3.1.0가 배포된 후 해당 변경과 함께 Azure에 배포되었습니다.

#### <a name="category"></a>범주

ASP.NET Core

#### <a name="affected-apis"></a>영향을 받는 API

<xref:Microsoft.AspNetCore.Builder.HttpsPolicyBuilderExtensions.UseHttpsRedirection(Microsoft.AspNetCore.Builder.IApplicationBuilder)?displayProperty=nameWithType>

<!-- 

#### Affected APIs

`M:Microsoft.AspNetCore.Builder.HttpsPolicyBuilderExtensions.UseHttpsRedirection(Microsoft.AspNetCore.Builder.IApplicationBuilder)`

-->
