---
ms.openlocfilehash: d1ddba72ce25c5e01025d916d52f785b5a1a9e71
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901661"
---
### <a name="hosting-generic-host-restricts-startup-constructor-injection"></a>호스팅: 제네릭 호스트는 시작 생성자 주입을 제한합니다.

제네릭 호스트가 `Startup` 클래스 생성자 주입을 지원하는 형식은 `IHostEnvironment`, `IWebHostEnvironment` 및 `IConfiguration`뿐입니다. `WebHost`를 사용하는 앱은 영향을 받지 않습니다.

#### <a name="change-description"></a>변경 내용 설명

ASP.NET Core 3.0 이전에는 `Startup` 클래스의 생성자에 있는 임의 형식에 생성자 주입을 사용할 수 있습니다. ASP.NET Core 3.0에서는 웹 스택이 제네릭 호스트 라이브러리로 다시 플랫폼화되었습니다. 템플릿의 *Program.cs* 파일에서 변경 내용을 확인할 수 있습니다.

**ASP.NET Core 2.x:**

<https://github.com/dotnet/aspnetcore/blob/5cb615fcbe8559e49042e93394008077e30454c0/src/Templating/src/Microsoft.DotNet.Web.ProjectTemplates/content/EmptyWeb-CSharp/Program.cs#L20-L22>

**ASP.NET Core 3.0:**

<https://github.com/dotnet/aspnetcore/blob/b1ca2c1155da3920f0df5108b9fedbe82efaa11c/src/ProjectTemplates/Web.ProjectTemplates/content/EmptyWeb-CSharp/Program.cs#L19-L24>

`Host`는 하나의 DI(종속성 주입) 컨테이너를 사용하여 앱을 빌드합니다. `WebHost`는 두 개의 컨테이너(호스트용과 앱용)를 사용합니다. 따라서 `Startup` 생성자는 더 이상 사용자 지정 서비스 주입을 지원하지 않습니다. `IHostEnvironment`, `IWebHostEnvironment` 및 `IConfiguration`만 주입할 수 있습니다. 이 변경으로 인해 싱글톤 서비스의 중복 만들기와 같은 DI 문제가 방지됩니다.

#### <a name="version-introduced"></a>도입된 버전

3.0

#### <a name="reason-for-change"></a>변경 이유

이 변경 내용은 웹 스택을 제네릭 호스트 라이브러리로 다시 플랫폼화한 결과입니다.

#### <a name="recommended-action"></a>권장 조치

`Startup.Configure` 메서드 서명에 서비스를 주입합니다. 예:

```csharp
public void Configure(IApplicationBuilder app, IOptions<MyOptions> options)
```

#### <a name="category"></a>범주

ASP.NET Core

#### <a name="affected-apis"></a>영향을 받는 API

없음

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
