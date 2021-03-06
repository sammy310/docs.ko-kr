---
title: ASP.NET Core에 대 한 eShop 마이그레이션 예제
description: 샘플 온라인 스토어 앱을 참조로 사용 하 여 기존 ASP.NET MVC 앱을 ASP.NET Core로 마이그레이션하는 연습입니다.
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: 83110909632e4eb433e1fabaedf3490ce594e12e
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401777"
---
# <a name="example-migration-of-eshop-to-aspnet-core"></a>ASP.NET Core에 대 한 eShop 마이그레이션 예제

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

이 장에서는 .NET Framework 앱을 .NET Core로 마이그레이션하는 방법에 대해 알아봅니다. 이 장에서는 ASP.NET 5.0 용으로 작성 된 샘플 온라인 스토어 앱을 검사 합니다. 앱은이 책의 앞부분에서 설명한 많은 개념과 도구를 사용 합니다. [ *EShopModernizing* GitHub 리포지토리에서](https://github.com/dotnet-architecture/eShopModernizing)시작 지점 앱을 찾을 수 있습니다. 여러 가지 시작 지점 앱이 있습니다. 이 장에서는 *eShopLegacyMVCSolution* 를 집중적으로 다룹니다.

프로젝트의 초기 버전은 그림 4-1에 나와 있습니다. 매우 표준 ASP.NET MVC 5 앱입니다.

![그림 4-1](media/Figure4-1.png)

**그림 4-1.** *EShopModernizing* MVC 샘플 프로젝트 구조입니다.

이 장에서는 많은 업그레이드 단계를 직접 수행 하는 방법을 보여 줍니다. 또는 [.Net 업그레이드 도우미 도구](https://aka.ms/dotnet-upgrade-assistant) 를 사용 하 여 프로젝트 파일을 변환 하 고, 대상 프레임 워크를 변경 하 고, NuGet 패키지를 업데이트 하는 등의 다양 한 초기 단계를 수행할 수 있습니다.

## <a name="run-apiport-to-identify-problematic-apis"></a>*Apiport* 를 실행 하 여 문제가 있는 api 식별

마이그레이션을 준비 하는 첫 번째 단계는 *Apiport* 도구를 실행 하는 것입니다. 이 도구는 앱에서 호출 하는 .NET Framework Api 수와 .NET Standard 또는 .NET Core의 해당 항목 수를 식별 합니다. 주로 사용자의 앱 논리에 초점을 맞춘 후 타사 종속성이 아니라 이식 해야 하는 종속성에 주의를 기울여야 `System.Web` 합니다. ApiPort 도구는 [종속성을 이해 하 고 업데이트 하](/understand-update-dependencies.md)는 마지막 챕터에서 도입 되었습니다.

[ *Apiport* 도구를 설치 하 고 구성한](../../standard/analyzers/portability-analyzer.md)후에는 그림 4-2에 나와 있는 것 처럼 Visual Studio 내에서 분석을 실행 합니다.

![그림 4-2](media/Figure4-2.png)

**그림 4-2.** Visual Studio에서 어셈블리 이식성을 분석 합니다.

그림 4-3에 표시 된 것 처럼 프로젝트의 *bin* 폴더에서 웹 프로젝트의 어셈블리를 선택 합니다.

![그림 4-3](media/Figure4-3.png)

**그림 4-3.** 프로젝트의 웹 어셈블리를 선택 합니다.

솔루션에 여러 프로젝트가 포함 되어 있는 경우 모두 선택할 수 있습니다. *EShop* 샘플에는 단일 MVC 프로젝트만 포함 되어 있습니다.

보고서가 생성 되 면 파일을 열고 결과를 검토 합니다. 이 요약은 앱에서 호환 되는 버전을 만드는 .NET Framework 호출의 비율을 간략하게 보여 줍니다. 그림 4-4에서는 *eShop* MVC 프로젝트에 대 한 요약을 보여 줍니다.

![그림 4-4](media/Figure4-4.png)

**그림 4-4.** ApiPort 요약.

이 앱의 경우 .NET Framework 호출의 약 80%가 호환 됩니다. 호출의 20%는 이식 프로세스 중에 처리 해야 합니다. 세부 정보를 보면 호환 되지 않는 호출이 모두에 포함 된다는 것을 알 수 `System.Web` 있습니다. `System.Web`응용 프로그램의 컨트롤러 및 관련 클래스가 이후 단계에서 마이그레이션되면 호출에 대 한 종속성이 처리 됩니다. 그림 4-5에는 도구에서 찾을 수 있는 특정 형식이 나와 있습니다.

![그림 4-5](media/Figure4-5.png)

**그림 4-5.** *Apiport* 호환 되지 않는 형식 세부 정보입니다.

호환 되지 않는 대부분의 형식은 `Controller` ASP.NET Core에 해당 하는 및 관련 된 다양 한 특성을 참조 합니다.

## <a name="update-project-files-and-nuget-reference-syntax"></a>프로젝트 파일 및 NuGet 참조 구문 업데이트

다음으로 이전 *.csproj* 파일 구조에서 .net Core를 사용 하 여 더 간단 하 고 더 간단한 구조로 마이그레이션합니다. 이 작업을 수행 하는 경우  `<PackageReference>` 프로젝트 파일에서 요소를 사용 하기 위한 NuGet 참조를 위해packages.config파일을 사용 하는 것 에서도 마이그레이션됩니다.

원본 프로젝트의 *eShopLegacyMVC* 파일 길이는 418 줄입니다. 그림 4-6에는 프로젝트 파일의 샘플이 나와 있습니다. 전반적인 크기와 복잡도를 이해 하기 위해 이미지의 오른쪽에는 전체 파일의 축소 된 보기가 포함 되어 있습니다.

![그림 4-6](media/Figure4-6.png)

**그림 4-6.** *EShopLegacyMVC* 파일 구조입니다.

기존 ASP.NET 프로젝트에 대 한 새 프로젝트 파일을 만드는 일반적인 방법은 `dotnet new`   >    >  Visual Studio에서 또는 파일 새로 만들기 **프로젝트** 를 사용 하 여 새 ASP.NET Core 앱을 만드는 것입니다. 그런 다음 이전 프로젝트에서 새 프로젝트에 파일을 복사 하 여 마이그레이션을 완료할 수 있습니다.

C # 프로젝트 파일 외에도 NuGet 종속성은 그림 4-7과 같이 별도의 45 줄 *packages.config* 파일에 저장 됩니다.

![그림 4-7](media/Figure4-7.png)

**그림 4-7.** *packages.config* 파일입니다.

새 *.csproj* 파일 형식으로 업그레이드 한 후에는 Visual Studio를 사용 하 여 클래스 라이브러리 프로젝트의 *packages.config* 를 마이그레이션할 수 있습니다. 그러나이 기능은 ASP.NET 프로젝트에서 작동 하지 않습니다. [ `<PackageReference>` Visual Studio에서 *packages.config* 로 마이그레이션에 대해 자세히 알아보세요](/nuget/consume-packages/migrate-packages-config-to-package-reference). 마이그레이션할 프로젝트 수가 많은 경우 [이 커뮤니티 도구가 도움이 될 수 있습니다](https://github.com/MarkKharitonov/NuGetPCToPRMigrator).

## <a name="create-new-aspnet-core-project"></a>새 ASP.NET Core 프로젝트 만들기

Visual Studio의 **솔루션 탐색기** 내에서 대부분의 작업을 수행할 수 있기 때문에 기존 앱의 솔루션에 새 ASP.NET Core 프로젝트를 추가 하 여 파일을 더 쉽게 이동할 수 있습니다. Visual Studio에서 앱 솔루션을 마우스 오른쪽 단추로 클릭 하 고 **추가 새 프로젝트** 를 선택 합니다. **ASP.NET Core 웹 응용 프로그램** 을 선택 하 고 그림 4-8에 표시 된 것 처럼 새 프로젝트에 이름을 지정 합니다.

![그림 4-8](media/Figure4-8.png)

**그림 4-8.** 새 ASP.NET Core 웹 응용 프로그램을 추가 합니다.

다음 대화 상자에서 사용할 템플릿을 선택 하 라는 메시지를 표시 합니다. **비어 있는** 템플릿을 선택합니다. 또한 드롭다운을 **.Net Core** 에서 **.NET Framework** 로 변경 해야 합니다. 그림 4-9와 같이 **ASP.NET Core 2.2** 를 선택 합니다.

![그림 4-9](media/Figure4-9.png)

**그림 4-9.** ASP.NET Core 2.2를 사용 하 여 .NET Framework를 대상으로 하는 빈 프로젝트 템플릿을 선택 합니다.

### <a name="migrating-nuget-packages"></a>NuGet 패키지 마이그레이션

*packages.config* 로 마이그레이션하기 위한 기본 제공 마이그레이션 도구는 `<PackageReference>` ASP.NET 프로젝트에서 작동 하지 않기 때문에 대신 커뮤니티 도구를 사용 하거나 직접 마이그레이션할 수 있습니다. [사용한 커뮤니티 도구](https://gist.github.com/tomkuijsten/2d75074d9a3c19c04ee8ea19a6289ddf) 는 XSL 파일을 사용 하 여 한 형식에서 다른 형식으로 변환 합니다. 이를 사용 하려면 먼저 *packages.config* 파일을 새로 만든 ASP.NET Core 프로젝트 폴더에 복사 합니다. 이 스크립트는 스크립트를 실행 하는 모든 폴더에서 *packages.config* 파일을 제거 하므로 파일의 백업을 만듭니다. 그런 다음 프로젝트 폴더 (또는 원하는 경우 전체 솔루션)에서 다음 명령을 실행 합니다.

```powershell
iwr https://git.io/vdKaV -OutFile Convert-ToPackageReference.ps1
iwr https://git.io/vdKar -OutFile  Convert-ToPackageReference.xsl
./Convert-ToPackageReference.ps1 | Out-Null
```

처음 두 명령은 파일이 로컬로 존재 하도록 다운로드 합니다. 마지막 줄은 스크립트를 실행 합니다. 실행 한 후 새 프로젝트 빌드를 시도 합니다. 오류가 발생 하는 경우가 많습니다. 이를 해결 하려면 일부 참조 (대부분 `Microsoft.AspNet` 및 패키지)를 제거 하 `System` 고 일부 특성을 제거 해야 할 수 있습니다 `xmlns` .

대부분의 ASP.NET MVC 앱에서 부트스트랩 및 jQuery와 같은 많은 클라이언트 쪽 종속성이 NuGet 패키지를 사용 하 여 배포 되었습니다. ASP.NET Core에서 NuGet 패키지는 서버 쪽 기능에만 사용 됩니다. 클라이언트 파일은 다른 방법으로 관리 해야 합니다. `<PackageReference>`추가 및 제거 요소 목록을 검토 하 고 다음을 비롯 한 클라이언트 라이브러리에 대 한 정보를 적어 둡니다.

- 부트스트랩
- jQuery
- jQuery. 유효성 검사
- Modernizr
- popper.js
- 대응

이러한 패키지에 대해 NuGet에 의해 설치 된 정적 클라이언트 파일은 새 프로젝트의 *wwwroot* 폴더에 복사 되 고 여기에서 호스팅됩니다. 앱에서 이러한 파일을 계속 사용 하 고 있는지 여부와이 파일을 계속 호스팅하거나 CDN (content delivery network)을 사용 하는 것이 적절 한지 여부를 고려 하는 것이 좋습니다. 이러한 라이브러리 버전은 [npm](https://www.npmjs.com/) [와 같은 도구](/aspnet/core/client-side/libman/) 를 사용 하 여 빌드 시 관리할 수 있습니다. 그림 4-10은 표시 된 변환 도구를 사용 하 여 패키지 참조를 마이그레이션한 후에 불필요 한 패키지를 제거 하는 전체 *eShopPorted* 파일을 보여 줍니다.

![그림 4-10](media/Figure4-10.png)

**그림 4-10.** *EShopPorted* 파일의 패키지 참조

요소를의 특성으로 만들어 패키지 참조를 추가로 압축할 수 있습니다 `<Version>1.0.0.0</Version>` `Version=1.0.0.0` `<PackageReference>` .

### <a name="migrate-static-files"></a>정적 파일 마이그레이션

타사 스크립트 및 프레임 워크를 비롯 하 여 앱에서 사용 하는 모든 정적 파일 (사용자 지정 이미지 및 스타일 시트)을 이전 프로젝트에서 새 프로젝트에 복사 해야 합니다. ASP.NET MVC 앱에서 파일은 일반적으로 프로젝트 폴더 내에서의 위치에 따라 액세스 됩니다. ASP.NET Core apps에서 이러한 정적 파일은 *wwwroot* 폴더 내에서의 위치에 따라 액세스 됩니다. *EShop* 프로젝트의 경우 다음 폴더에 정적 파일이 있습니다.

* *콘텐츠*
* *글자만*
* *이미지*
* *Pics*
* *스크립트*

이전 단계에서 사용 되는 **빈** 프로젝트 템플릿에는 기본적으로이 폴더가 포함 되지 않으며, 작업에 필요한 미들웨어가 포함 되어 있지 않습니다. 추가 해야 합니다.

프로젝트의 루트에 *wwwroot* 폴더를 추가 합니다.

NuGet 패키지의 버전 2.2.0을 추가 `Microsoft.AspNetCore.StaticFiles` 합니다.

*Startup.cs* 의 메서드에 대 한 호출을 추가 합니다 `app.UseStaticFiles()` `Configure` .

```csharp
public void Configure(IApplicationBuilder app, IHostingEnvironment env)
{
    if (env.IsDevelopment())
    {
        app.UseDeveloperExceptionPage();
    }

    app.UseStaticFiles();

    // ...
}
```

ASP.NET MVC 앱의 *콘텐츠* 폴더를 새 프로젝트의 *wwwroot* 폴더로 복사 합니다.

앱을 실행 하 고 해당 파일의/i o n t i o n *>* 로 이동 하 여 정적 파일이 예상 되는 경로에서 올바르게 처리 되는지 확인 합니다. 정적 파일이 포함 된 나머지 폴더를 새 프로젝트에 계속 복사 합니다. 또한 프로젝트의 루트에서 *wwwroot* 폴더로 *favicon* 파일을 복사 합니다. 그림 4-11에서는 이러한 파일과 해당 폴더가 모두 복사 된 후의 결과를 보여 줍니다.

![그림 4-11](media/Figure4-11.png)

**그림 4-11.** *Wwwroot* 폴더로 복사 되는 정적 폴더.

### <a name="migrate-c-files"></a>C # 파일 마이그레이션

그런 다음 표준 MVC 폴더 및 *컨트롤러*, *모델*, *ViewModel*, *서비스* 등의 내용을 포함 하 여 앱에서 사용 하는 c # 파일을 복사 합니다. 이러한 파일에는 변경 해야 하는 경우가 많습니다. 한 번에 하나의 폴더 (또는 하위 폴더)를 복사 하 여 컴파일할 때 해결 해야 하는 오류를 확인 하는 것이 가장 좋습니다.

*EShop* 샘플의 경우 마이그레이션하려는 첫 번째 폴더는 c # 엔터티와 Entity Framework 클래스를 포함 하는 *모델* 폴더입니다. 이 폴더의 클래스는 대부분 다른 클래스에서 사용 되므로 이러한 클래스가 복사 될 때까지 작동 하지 않습니다. 폴더 및 빌드를 복사 하면 컴파일러가 누락 된 네임 스페이스,에 대 한 `System.Web.Hosting` 관련 액세스 및에 대 한 참조와 관련 된 오류를 표시 합니다 `HostingEnvironment` `ConfigurationManager.AppSettings` . 이러한 문제에 대 한 해결 방법은 필요한 경로 데이터를 전달 하는 것입니다. 지금은 줄 바꿈이 주석 처리 되 고 `TODO:` 각 줄에 주석이 추가 되어 추적할 수 있습니다. 5 개 줄을 변경한 후 **작업 목록** 에는 5 개의 항목과 프로젝트 빌드가 표시 됩니다.

그런 다음, 하나의 클래스를 사용 하 여 *ViewModel* 폴더를 복사 합니다. 이는 간단 하 고 즉시 빌드됩니다.

*서비스* 폴더가에 복사 됩니다. 이 폴더의 클래스는 *모델* 폴더의 Entity Framework 클래스에 종속 되므로 해당 폴더 뒤에 복사 해야 합니다. 다행히 오류가 발생 하지 않고 빌드됩니다.

이는 *컨트롤러* 폴더와 두 개의 클래스를 유지 합니다 `Controller` . 새 프로젝트에 폴더를 복사 하 고 빌드한 후에는 7 개의 빌드 오류가 발생 합니다. 그 중 4 개는 `ViewBag` 액세스 및 오류 보고와 관련 되어 있습니다.

> `Missing compiler required member 'Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo.Create'`

이 오류를 해결 하려면 c #에 대 한 NuGet 패키지 참조를 추가 합니다.

```xml
<PackageReference Include="Microsoft.CSharp" Version="4.7.0" />
```

나머지 세 개의 오류는 참조 되지 않는 어셈블리에 정의 된 형식을 지정 합니다. 특히 다음과 같은 형식입니다.

- `HttpServerUtilityBase`
- `RouteValueDictionary`
- `HttpRequestBase`

각 오류를 하나씩 살펴보겠습니다. `Server`더 이상 존재 하지 않는의 속성을 참조 하는 동안 첫 번째 오류가 발생 합니다 `Controller` . 작업의 목표는 앱의 이미지 파일에 대 한 경로를 가져오는 것입니다.

```csharp
if (item != null)
{
    var webRoot = Server.MapPath("~/Pics"); // compiler error on this line
    var path = Path.Combine(webRoot, item.PictureFileName);

    string imageFileExtension = Path.GetExtension(item.PictureFileName);
    string mimetype = GetImageMimeTypeFromImageFileExtension(imageFileExtension);

    var buffer = System.IO.File.ReadAllBytes(path);

    return File(buffer, mimetype);
}
```

이 문제는 두 가지 방법으로 해결할 수 있습니다. 첫 번째 방법은 기능을 그대로 유지 하는 것입니다. 이 경우를 사용 하는 대신 `Server.MapPath` *wwwroot* 에서 이미지 파일의 위치를 참조 하는 고정 경로를 사용 해야 합니다. 또는이 작업 메서드의 유일한 용도는 정적 이미지 파일을 반환 하는 것 이므로 파일 보기에서이 작업에 대 한 참조를 업데이트 하 여 정적 파일을 직접 참조 하 여 런타임 성능을 향상 시킬 수 있습니다. 이 작업의 일부로 처리가 수행 되지 않으므로 파일을 직접 제공 하지 않아도 됩니다. 이 작업에 대 한 모든 참조를 업데이트 하기 위해 tenable을 사용 하지 않는 경우 정적 파일의 위치에 대 한 리디렉션을 생성 하도록 작업을 다시 작성할 수 있습니다.

다음 두 오류는 동일한 코드 줄의 동일한 private 메서드에서 발생 합니다.

```csharp
private void AddUriPlaceHolder(CatalogItem item)
{
    item.PictureUri = this.Url.RouteUrl(PicController.GetPicRouteName, new { catalogItemId = item.Id }, this.Request.Url.Scheme);
}
```

`this.Url`및 모두 `this.Request` 컴파일러 오류가 발생 합니다. 이 코드를 사용 하는 방법을 살펴보면 `PicController` 이미지 파일을 렌더링 하는 작업에 대 한 링크를 작성 하는 것입니다. 방금 검색 한 것과 동일한 것을 *wwwroot* 에 있는 정적 파일에 대 한 직접 링크로 바꿀 수 있습니다. 지금은이 코드를 주석으로 처리 하 고 다른 사람을 참조 하도록 주석을 추가 하는 것이 좋습니다 `TODO:` .

`Controller`이 코드가 표시 되는 클래스에서 사용 되는 기본 클래스는 `CatalogController` 여전히를 참조 하 고 `System.Web.Mvc.Controller` 있습니다. ASP.NET Core를 사용 하도록 업데이트 한 후에는 수정 하는 데 더 많은 오류가 발생 합니다. 먼저 `using System.Web.Mvc;` 의 문 목록에서 줄을 제거 `using` `CatalogController` 합니다. 그런 다음 NuGet 패키지를 추가 `Microsoft.AspNetCore.Mvc` 합니다. 마지막으로 문을 추가 하 `using Microsoft.AspNetCore.Mvc;` 고 앱을 다시 빌드합니다.

이번에는 16 개 오류가 있습니다.

- `Include` 은 (는) 올바른 명명 된 특성 인수가 아닙니다 (2).
- `HttpStatusCodeResult` 찾을 수 없음 (3)
- `HttpNotFound` 존재 하지 않음 (3)
- `SelectList` 찾을 수 없음 (8)

그 후에는 이러한 오류를 하나씩 검토해 보겠습니다. 첫째,를 `SelectList` 추가 하 여 해결할 수 있습니다 `using Microsoft.AspNetCore.Mvc.Rendering;` . 그러면 오류가 거의 발생 하지 않습니다.

에 대 한 모든 참조 `return HttpNotFound();` 는로 바꾸어야 합니다 `return NotFound();` .

에 대 한 모든 참조 `return new HttpStatusCodeResult(HttpStatusCode.BadRequest);` 는로 바꾸어야 합니다 `return BadRequest();` .

`Include` `[Bind]` 이는 다음과 같은 몇 가지 동작 메서드에서 특성을 사용 하는 것을 그대로 유지 합니다.

```csharp
[HttpPost]
[ValidateAntiForgeryToken]
public ActionResult Create([Bind(Include = "Id,Name,Description,Price,PictureFileName,CatalogTypeId,CatalogBrandId,AvailableStock,RestockThreshold,MaxStockThreshold,OnReorder")] CatalogItem catalogItem)
{
```

위의 코드는 문자열에 나열 된 속성에 대 한 모델 바인딩을 제한 합니다 `Include` . MVC ASP.NET Core `[Bind]` 특성은 여전히 존재 하지만 더 이상 인수가 필요 하지 않습니다 `Include =` . 속성 목록을 특성에 직접 전달 합니다 `[Bind]` .

```csharp
[HttpPost]
[ValidateAntiForgeryToken]
public ActionResult Create([Bind("Id,Name,Description,Price,PictureFileName,CatalogTypeId,CatalogBrandId,AvailableStock,RestockThreshold,MaxStockThreshold,OnReorder")] CatalogItem catalogItem)
{
```

이러한 변경 내용으로 프로젝트를 한 번 더 컴파일합니다. 일반적으로 도메인 모델 또는 데이터 모델 형식에 대 한 모델 바인딩을 직접 사용 하는 대신 컨트롤러 입력에 별도의 모델 유형을 사용 하는 것이 더 좋습니다.

## <a name="migrate-views"></a>뷰 마이그레이션

뷰와 관련 된 가장 큰 두 가지 ASP.NET Core MVC 기능은 [Razor Pages](/aspnet/core/razor-pages/) 및 [태그 도우미](/aspnet/core/mvc/views/tag-helpers/built-in/)입니다. 초기 마이그레이션의 경우 두 기능을 사용 하지 않습니다. 그러나 앱을 마이그레이션한 후에도 계속 지원 하면 기능을 염두에 두어야 합니다. 다음 단계는 원본 프로젝트의 *Views* 폴더를 새 프로젝트에 복사 하는 것입니다. 빌드 후에는 9 개의 오류가 있습니다.

- HttpContext가 없습니다 (2).
- 스크립트가 없습니다 (5).
- 스타일이 존재 하지 않습니다 (1).
- HtmlString을 찾을 수 없습니다 (1).

이러한 오류를 조사 하면 대부분의 작업이 주 *_Layout. cshtml* 에 있고, 스크립트 및 스타일 태그 렌더링과 관련 된 몇 가지를 포함 하거나, 앱을 호스트 하는 서버를 마지막으로 다시 시작한 경우 표시 됩니다. 다음 코드 목록에서는 *_Layout. cshtml* 파일의 문제 영역을 보여 줍니다.

```razor
// other lines omitted; only errors shown
@Styles.Render("~/Content/css")
@Scripts.Render("~/bundles/modernizr")

@{ var sessionInfo = new HtmlString($"{HttpContext.Current.Session["MachineName"]}, {HttpContext.Current.Session["SessionStartTime"]}");}

@Scripts.Render("~/bundles/jquery")
@Scripts.Render("~/bundles/bootstrap")
```

Modernizr에 대 한 참조를 제거할 수 있습니다. 부트스트랩 및 jQuery에 대 한 참조를 CDN 링크를 적절 한 버전으로 바꿀 수 있습니다.

`@Styles.Render`줄을 다음으로 바꾸기:

```html
<link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css" integrity="sha384-ggOyR0iXCbMQv3Xipma34MD+dH/1fQ784/j6cY/iJTQUOhcWr7x9JvoRxT2MZw1T" crossorigin="anonymous">
```

마지막 두 줄을 `Scripts.Render` 다음으로 바꿉니다.

```html
<script src="https://code.jquery.com/jquery-3.3.1.slim.min.js" integrity="sha384-q8i/X+965DzO0rT7abK41JStQIAqVgRVzpbzo5smXKp4YfRvH+8abtTE1Pi6jizo" crossorigin="anonymous"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.7/umd/popper.min.js" integrity="sha384-UO2eT0CpHqdSJQ6hJty5KVphtPhzWj9WO1clHTMGa3JDZwrnQq4sF86dIHNDz0W1" crossorigin="anonymous"></script>
<script src="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/js/bootstrap.min.js" integrity="sha384-JjSmVgyd0p3pXB1rRibZUAYoIIy6OrQ6VrjIEaFf/nJGzIxFDsf4x0xIM+B07jRM" crossorigin="anonymous"></script>
```

마지막으로 부트스트랩 후에 `<link>` `<link>` 앱에서 사용 하는 로컬 스타일에 대 한 추가 요소를 추가 합니다. *EShop* 의 경우 결과는 다음과 같이 표시 됩니다.

```html
<link rel="stylesheet" href="~/Content/custom.css" />
<link rel="stylesheet" href="~/Content/base.css" />
<link rel="stylesheet" href="~/Content/Site.css" />
```

요소가 표시 되는 순서를 결정 하려면 `<link>` 원래 앱의 렌더링 된 HTML을 살펴보세요. 또는 *eShop* 샘플에 대해 적절 한 시퀀스를 나타내는이 코드를 포함 하는 *BundleConfig.cs* 를 검토 합니다.

```csharp
bundles.Add(new StyleBundle("~/Content/css").Include(
          "~/Content/bootstrap.css",
          "~/Content/custom.css",
          "~/Content/base.css",
          "~/Content/site.css"));
```

*만들기* 및 *편집* 보기에서 jQuery 유효성 검사를 로드 하는 중에 다시 빌드하면 하나 이상의 오류가 표시 됩니다. 다음 스크립트로 바꿉니다.

```html
<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery-validate/1.17.0/jquery.validate.min.js" integrity="sha512-O/nUTF5mdFkhEoQHFn9N5wmgYyW323JO6v8kr6ltSRKriZyTr/8417taVWeabVS4iONGk2V444QD0P2cwhuTkg==" crossorigin="anonymous"></script>
```

뷰에서 마지막으로 수정할 사항은 앱이 실행 되는 `Session` 시간 및 해당 컴퓨터를 표시 하는에 대 한 참조입니다. 에서이 데이터를 `Startup` 정적 변수로 수집 하 고 레이아웃 페이지에 변수를 표시할 수 있습니다. *Startup.cs* 에 다음 속성을 추가 합니다.

```csharp
public static DateTime StartTime { get; } = DateTime.UtcNow;
public static string MachineName { get; } = Environment.MachineName;
```

그런 다음 레이아웃의 바닥글 내용을 다음 코드로 바꿉니다.

```razor
<section class="col-sm-6">
    <img class="esh-app-footer-text hidden-xs" src="~/images/main_footer_text.png" width="335" height="26" alt="footer text image" />
    <br />
<small>@eShopPorted.Startup.MachineName - @eShopPorted.Startup.StartTime.ToString() UTC</small>
</section>
```

이 시점에서 앱은 성공적으로 빌드 되었습니다. 그러나이 도구를 실행 하려고 하면 *헬로 월드 됩니다.* **빈** ASP.NET Core 템플릿은 모든 요청에 대 한 응답으로 표시 하도록 구성 되어 있기 때문입니다. 다음 섹션에서는 종속성 주입 및 구성을 비롯 하 여 ASP.NET Core MVC를 사용 하도록 앱을 구성 하 여 마이그레이션을 완료 합니다. 앱이 준비 되 면 앱이 실행 됩니다. 그런 다음 이전에 생성 된 작업을 수정 해야 합니다 `TODO:` .

## <a name="migrate-app-startup-components"></a>앱 시작 구성 요소 마이그레이션

마지막 마이그레이션 단계는 *global.asax에서 앱 시작 작업을 수행* 하 고이 작업을 호출 하는 클래스를 사용 하 여 해당 작업을 해당 하는 ASP.NET Core로 마이그레이션해야 합니다. 이러한 작업에는 MVC 자체의 구성, 종속성 주입 설정 및 새 구성 시스템 사용이 포함 됩니다. ASP.NET Core에서 이러한 작업은 *Startup.cs* 파일에서 처리 됩니다.

### <a name="configure-mvc"></a>MVC 구성

원본 ASP.NET MVC 앱의 `Application_Start` *global.asax* 에는 앱이 시작 될 때 실행 되는 다음 코드가 있습니다.

```csharp
protected void Application_Start()
{
    container = RegisterContainer();
    AreaRegistration.RegisterAllAreas();
    FilterConfig.RegisterGlobalFilters(GlobalFilters.Filters);
    RouteConfig.RegisterRoutes(RouteTable.Routes);
    BundleConfig.RegisterBundles(BundleTable.Bundles);
    ConfigDataBase();
}
```

이러한 줄을 하나씩 살펴보면 메서드는 아래에 `RegisterContainer` 이식할 종속성 주입을 설정 합니다. 다음 세 줄은 MVC의 서로 다른 부분, 즉 영역, 필터 및 경로를 구성 합니다. 번들은 이식 된 앱에서 정적 파일로 대체 됩니다. 마지막 줄은 응용 프로그램에 대 한 데이터 액세스를 설정 합니다 .이에 대해서는 이후 섹션에서 볼 수 있습니다.

이 앱은 실제로 영역을 사용 하지 않으므로 영역 등록 호출을 마이그레이션하기 위해 수행 해야 하는 작업은 없습니다. 앱에서 영역을 마이그레이션해야 하는 경우 문서에서 [ASP.NET Core 영역을 구성 하는 방법을 지정](/aspnet/core/mvc/controllers/areas)합니다.

전역 필터를 등록 하는 호출은 `FilterConfig` 응용 프로그램의 *App_Start* 폴더에 있는 클래스에 대 한 도우미를 호출 합니다.

```csharp
public static void RegisterGlobalFilters(GlobalFilterCollection filters)
{
    filters.Add(new HandleErrorAttribute());
}
```

앱에 추가 되는 유일한 특성은 ASP.NET MVC 필터입니다 `HandleErrorAttribute` . 이 필터는 예외가 요청의 일부로 발생 하는 경우 예외 정보가 아닌 기본 작업 및 뷰가 표시 되도록 합니다. ASP.NET Core에서는 미들웨어를 통해 동일한 기능을 수행 `UseExceptionHandler` 합니다. 자세한 오류 메시지는 기본적으로 사용 하도록 설정 되어 있지 않습니다. 미들웨어를 사용 하 여 구성 해야 합니다 `UseDeveloperExceptionPage` . 원래 앱과 일치 하도록이 동작을 구성 하려면 Startup.cs에서 다음 코드를 메서드의 시작 부분에 추가 해야 합니다 `Configure` . 

```csharp
public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
{
    if (env.IsDevelopment())
    {
        app.UseDeveloperExceptionPage();
    }
    else
    {
        app.UseExceptionHandler("/Error");
    }
    // ...
}
```

이는 eShop 앱에서 사용 하는 유일한 필터를 담당 하며,이 경우 기본 제공 미들웨어를 사용 하 여 수행 되었습니다. 앱에서 구성 해야 하는 전역 필터가 있는 경우이 작업은 `ConfigureServices` 이 챕터의 뒷부분에 나오는 메서드에 MVC가 추가 될 때 수행 됩니다.

마이그레이션해야 하는 MVC 관련 논리의 마지막 부분은 앱의 기본 경로입니다. 에 대 한 호출은 `RouteConfig.RegisterRoutes(RouteTable.Routes)` MVC 경로 테이블을 `RegisterRoutes` 도우미 메서드에 전달 합니다. 그러면 앱이 시작 될 때 다음 코드가 실행 됩니다.

```csharp
public static void RegisterRoutes(RouteCollection routes)
{
    routes.MapMvcAttributeRoutes();
    routes.IgnoreRoute("{resource}.axd/{*pathInfo}");

    routes.MapRoute(
        name: "Default",
        url: "{controller}/{action}/{id}",
        defaults: new { controller = "Catalog", action = "Index", id = UrlParameter.Optional }
    );
}
```

이 코드를 한 줄씩 수행 하면 첫 번째 줄에서 특성 경로에 대 한 지원을 설정 합니다. 이는 ASP.NET Core에 기본 제공 되므로 별도로 구성 하지 않아도 됩니다. 마찬가지로 *{resource}.* s a s 파일은 ASP.NET Core에서 사용 되지 않으므로 이러한 경로를 무시할 필요가 없습니다. `MapRoute`메서드는 일반적인 경로 템플릿을 사용 하는 MVC에 대 한 기본값을 구성 합니다 `{controller}/{action}/{id}` . 또한이 템플릿에 대 한 기본값을 지정 합니다 .이는 `CatalogController` 가 사용 되는 기본 컨트롤러이 `Index` 고 메서드는 기본 동작입니다. 더 큰 앱은 `MapRoute` 추가 경로를 설정 하기 위해에 대 한 추가 호출을 포함 하는 경우가 많습니다.

ASP.NET Core MVC는 [기존 라우팅 및 특성 라우팅을](/aspnet/core/mvc/controllers/routing?preserve-view=true&view=aspnetcore-2.2)지원 합니다. 기존 라우팅은 앞에 나열 된 메서드에서 경로 테이블을 구성 하는 방법과 유사 `RegisterRoutes` 합니다. *EShop* 앱에서 사용 되는 것과 같은 기본 경로를 사용 하 여 기존 라우팅을 설정 하려면 `Configure` *Startup.cs* 에서 메서드의 맨 아래에 다음 코드를 추가 합니다.

```csharp
app.UseMvc(routes =>
{
   routes.MapRoute("default", "{controller=Catalog}/{action=Index}/{id?}");
});
```

> [!NOTE]
> ASP.NET Core 3.0 이상에서는 끝점을 사용 하도록 변경 되었습니다. 2.2 ASP.NET Core 초기 포트의 경우이는 기존 경로를 매핑하기 위한 적절 한 구문입니다.

이러한 변경 내용을 적용 하면 `Configure` 메서드가 거의 완료 됩니다. `app.Run` *헬로 월드* 를 인쇄 하는 원래 템플릿의 메서드 삭제 해야 합니다. 이 시점에서 메서드는 다음과 같이 표시 됩니다.

```csharp
public void Configure(IApplicationBuilder app, IHostingEnvironment env)
{
    if (env.IsDevelopment())
    {
        app.UseDeveloperExceptionPage();
    }
    else
    {
        app.UseExceptionHandler("/Home/Error");
    }

    app.UseStaticFiles();

    app.UseMvc(routes =>
    {
        routes.MapRoute("default", "{controller=Catalog}/{action=Index}/{id?}");
    });
}
```

이제 MVC 서비스를 구성 하 고 나머지 응용 프로그램에서 DI (종속성 주입)를 지원 합니다. 지금까지 *eShopPorted* 프로젝트의 메서드는 `ConfigureServices` 비어 있었습니다. 이제 채우기를 시작할 때입니다.

먼저 ASP.NET Core MVC가 정상적으로 작동 하도록 하려면 다음을 추가 해야 합니다.

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddMvc();
}
```

위의 코드는 MVC 기능을 작동 하는 데 필요한 최소 구성입니다. 이 호출에서 구성할 수 있는 추가 기능이 많이 있지만 지금은 앱을 빌드하는 데 충분 합니다. 이 도구를 실행 하면 기본 요청은 제대로 라우팅됩니다. 그러나 아직 DI를 구성 하지 않았기 때문에 `CatalogController` 형식 구현이 아직 제공 되지 않았기 때문에 활성화 하는 동안 오류가 발생 `ICatalogService` 합니다. 나중에 MVC를 구성 하기 위해를 반환 합니다. 지금은 응용 프로그램의 종속성 주입을 마이그레이션합니다.

#### <a name="migrate-dependency-injection-configuration"></a>종속성 주입 구성 마이그레이션

원래 앱의 *global.asax* 파일은 앱이 시작 될 때 호출 되는 다음 메서드를 정의 합니다.

```csharp
protected IContainer RegisterContainer()
{
  var builder = new ContainerBuilder();

  builder.RegisterControllers(typeof(MvcApplication).Assembly);

  var mockData = bool.Parse(ConfigurationManager.AppSettings["UseMockData"]);
  builder.RegisterModule(new ApplicationModule(mockData));

  var container = builder.Build();
  DependencyResolver.SetResolver(new AutofacDependencyResolver(container));

  return container;
}
```

이 코드는 [autofac](https://autofac.org/) 컨테이너를 구성 하 고, 구성 설정을 읽고, 실제 또는 모의 데이터를 사용할지 여부를 결정 하 고,이 설정을 autofac 모듈 (앱의 */모듈* 디렉터리에 있음)에 전달 합니다. 다행히 Autofac는 .NET Core를 지원 하므로 모듈을 직접 마이그레이션할 수 있습니다. 새 프로젝트에 폴더를 복사 하 고 클래스의 네임 스페이스를 업데이트 하 고 컴파일해야 합니다.

ASP.NET Core는 종속성 주입을 기본적으로 지원 하지만 필요한 경우 Autofac와 같은 타사 컨테이너를 쉽게 연결할 수 있습니다. 이 경우 앱은 이미 Autofac를 사용 하도록 구성 되었으므로 가장 간단한 방법은 사용을 유지 하는 것입니다. 이렇게 하려면를 `ConfigureServices` 반환 하도록 메서드 시그니처를 수정 하 `IServiceProvider` 고, Autofac 컨테이너 인스턴스를 구성 하 여 메서드에서 반환 해야 합니다.

**참고:** .NET Core 3.0 이상에서 타사 DI 컨테이너를 통합 하는 프로세스가 변경 되었습니다.

Autofac를 구성 하는 과정에는를 호출 해야 `builder.Populate(services)` 합니다. 이 확장은 NuGet 패키지에서 찾을 수 `Autofac.Extensions.DependencyInjection` 있습니다 .이 패키지는 코드를 컴파일하기 전에 설치 해야 합니다.

`ConfigureServices`Autofac 컨테이너를 구성 하도록 수정 하 고 나면 다음과 같이 새 메서드가 만들어집니다.

```csharp
public IServiceProvider ConfigureServices(IServiceCollection services)
{
    services.AddMvc();

    // Create Autofac container builder
    var builder = new ContainerBuilder();
    builder.Populate(services);
    bool useMockData = true; // TODO: read from config
    builder.RegisterModule(new ApplicationModule(useMockData));

    ILifetimeScope container = builder.Build();

    return new AutofacServiceProvider(container);
}
```

지금은의 설정이 `useMockData` 로 설정 됩니다 `true` . 이 설정은 잠시 후에 구성에서 읽게 됩니다. 이 시점에서 그림 4-12에 표시 된 것 처럼 앱이 컴파일되고 실행 될 때 성공적으로 로드 됩니다.

![그림 4-12](media/Figure4-12.png)

**그림 4-12.** 모의 데이터를 사용 하 여 로컬로 실행 되는 이식 된 *eShop* 앱입니다.

#### <a name="migrate-app-settings"></a>앱 설정 마이그레이션

ASP.NET Core은 기본적으로 파일 *의appsettings.js* 를 활용 하는 새 [구성 시스템](/aspnet/core/fundamentals/configuration/?preserve-view=true&view=aspnetcore-2.2)을 사용 합니다. `CreateDefaultBuilder` *Program.cs* 에서를 사용 하 여 기본 구성이 이미 앱에 설정 되어 있습니다. 구성에 액세스 하기 위해 클래스는 생성자에서 요청 하기만 하면 됩니다. `Startup`클래스는 예외가 아닙니다. 의 구성과 나머지 앱에 대 한 액세스를 시작 하려면 `Startup` 해당 생성자에서의 인스턴스를 요청 합니다 `IConfiguration` .

```csharp
public Startup(IConfiguration configuration)
{
    Configuration = configuration;
}

public IConfiguration Configuration { get; }
```

원래 앱은를 사용 하 여 해당 설정을 참조 `ConfigurationManager.AppSettings` 했습니다. 이 용어의 모든 참조를 빠르게 검색 하면 새 앱에 필요한 설정 집합이 생성 됩니다. 다음 두 가지 유형만 있습니다.

- `UseMockData`
- `UseCustomizationData`

앱에 더 복잡 한 구성이 있는 경우, 특히 사용자 지정 구성 섹션을 사용 하는 경우에는 응용 프로그램 구성의 다른 부분에 개체를 만들고 바인딩하는 것이 좋습니다. 이러한 형식은 [옵션 패턴](../../core/extensions/options.md)을 사용 하 여 액세스할 수 있습니다. 그러나 참조 된 문서에서 설명한 대로이 패턴은에서 사용 하지 않아야 `ConfigureServices` 합니다. 대신, 이식 된 앱은 `UseMockData` 구성 값을 직접 참조 합니다.

먼저, 이식 된 앱의 파일을 수정 `appsettings.json` 하 고 루트에 두 설정을 추가 합니다.

```json
{
  "Logging": {
    "LogLevel": {
      "Default": "Warning"
    }
  },
  "AllowedHosts": "*",
  "UseMockData": "true",
  "UseCustomizationData" :  "true"
}
```

이제를 수정 `ConfigureServices` 하 여 `UseMockData` 속성에서 설정에 액세스 합니다 `Configuration` (이전에 값을로 설정한 경우 `true` ).

```csharp
  bool useMockData = Configuration.GetValue<bool>("UseMockData");
```

이 시점에서 설정은 구성에서 가져옵니다. 다른 설정인는 `UseCustomizationData` 클래스에서 사용 됩니다 `CatalogDBInitializer` . 이 클래스를 처음 이식 하는 경우에 대 한 액세스를 주석으로 처리 `ConfigurationManager.AppSettings["UseCustomizationData"]` 합니다. 이제 ASP.NET Core 구성을 사용 하도록 수정할 수 있습니다. 다음과 같이의 생성자를 수정 합니다 `CatalogDBInitializer` .

```csharp
  // add using Microsoft.Extensions.Configuration
  public CatalogDBInitializer(CatalogItemHiLoGenerator indexGenerator,
      IConfiguration configuration)
  {
      this.indexGenerator = indexGenerator;
      useCustomizationData = configuration.GetValue<bool>("UseCustomizationData");
  }
```

새 형식을 사용 하려면 웹 앱 내의 모든 구성에 대 한 액세스를 이러한 방식으로 수정 해야 합니다 `IConfiguration` . .NET Framework 구성에 액세스 해야 하는 종속성에는 웹 프로젝트에 추가 된 *app.config* 파일의 이러한 설정이 포함 될 수 있습니다. 종속 프로젝트는와 함께 작동 `ConfigurationManager` 하 여 설정에 액세스할 수 있으며,이 방법을 이미 사용 하는 경우에는 변경이 필요 하지 않습니다. 그러나 ASP.NET Core 앱은 자신의 실행 파일로 실행 되기 때문에 *web.config* 를 참조 하지 않고 *app.config* 됩니다. 레거시 앱의 *web.config* 파일에서 ASP.NET Core 앱의 새 *app.config* 파일로 설정을 마이그레이션하면에서 해당 설정에 액세스 하는 데 사용 하는 구성 요소는 `ConfigurationManager` 계속 제대로 작동 합니다.

앱의 마이그레이션이 거의 완료 되었습니다. 유일 하 게 남은 태스크는 데이터 액세스 구성입니다.
  
## <a name="data-access-considerations"></a>데이터 액세스 고려 사항

.NET Framework에서 실행 되는 ASP.NET Core 앱은 EF (Entity Framework)를 계속 활용할 수 있습니다. 증분 마이그레이션을 수행 하는 경우 EF Core 사용 하기 위해 데이터 액세스를 수신 하기 전에 EF 6을 사용 하 여 앱이 작동 하는 것이 유용할 수 있습니다. 이러한 방식으로 다른 마이그레이션 작업을 시작 하기 전에 앱의 마이그레이션 문제를 식별 하 고 해결할 수 있습니다.

이러한 작업을 수행 하는 동안에는이 작업이 Autofac에서 수행 되었으므로 eShop 샘플 마이그레이션에서 EF 6을 구성 하는 것은 특별 한 작업이 필요 하지 않습니다 `ApplicationModule` . 유일한 문제는 현재 `CatalogDBContext` 클래스가 *web.config* 에서 연결 문자열을 읽으려고 시도 하는 것입니다. 이를 해결 하려면 연결 정보를 *appsettings.js* 에 추가 해야 합니다. 그런 다음 생성 될 때 연결 문자열을에 전달 해야 합니다 `CatalogDBContext` .

연결 문자열을 포함 하도록 *appsettings.js* 를 업데이트 합니다. 전체 파일은 다음 위치에 나열 됩니다.

```json
{
  "ConnectionStrings": {
    "DefaultConnection": "Server=(localdb)\\mssqllocaldb;Database=eShopPorted;Trusted_Connection=True;MultipleActiveResultSets=true"
  },
  "Logging": {
    "LogLevel": {
      "Default": "Warning"
    }
  },
  "AllowedHosts": "*",
  "UseMockData": "false",
  "UseCustomizationData": "true"
}
```

연결 문자열은가 만들어질 때 생성자에 전달 되어야 합니다 `DbContext` . 인스턴스는 Autofac에서 만들어지기 때문에에서 변경 해야 `ApplicationModule` 합니다. 생성자의를 사용 하 여 모듈을 수정 하 `connectionString` 고 필드에 할당 합니다. 그런 다음에 대 한 등록을 수정 `CatalogDBContext` 하 여 연결 문자열을 매개 변수로 추가 합니다.

```csharp
builder.RegisterType<CatalogDBContext>()
  .WithParameter("connectionString", _connectionString)
  .InstancePerLifetimeScope();
```

매개 변수도 새 생성자 오버 로드에 추가 해야 합니다 `CatalogDBContext` .

```csharp
public CatalogDBContext(string connectionString) : base(connectionString)
{
}
```

마지막으로, `ConfigureServices` 에서 연결 문자열을 읽고이를 `Config` 인스턴스화할 때에 전달 해야 합니다 `ApplicationModule` .

```csharp
bool useMockData = Configuration.GetValue<bool>("UseMockData");
string connectionString = Configuration.GetConnectionString("DefaultConnection");
builder.RegisterModule(new ApplicationModule(useMockData, connectionString));
```

이 코드를 사용 하는 경우 앱은 이전과 마찬가지로 실행 되어가 일 때 SQL Server 데이터베이스에 연결 `UseMockData` 합니다 `false` .

이 시점에서 앱을 배포 하 고 프로덕션 환경에서 실행할 수 있습니다 .이 시점에서 ASP.NET Core로 변환 되지만 .NET Framework 및 EF 6에서 계속 실행 됩니다. 원하는 경우 앱을 마이그레이션하여 .NET Core에서 실행 하 고 Entity Framework Core 수 있습니다. 그러면 이전 장에 설명 된 추가 이점이 있습니다. Entity Framework와 관련 하 여 [이 설명서는 EF Core와 EF 6을 비교](/ef/efcore-and-ef6/) 하 고 각 수십 개의 개별 기능을 지 원하는 라이브러리를 보여 주는 표를 포함 합니다.

### <a name="migrate-to-entity-framework-core"></a>Entity Framework Core로 마이그레이션

EF Core로 마이그레이션하도록 결정 하는 것으로 가정 하면 특히 원래 앱에서 코드 기반 모델 접근 방법을 사용 하는 경우 단계가 매우 간단할 수 있습니다. [EF 6에서 EF Core로 포트를 준비할](/ef/efcore-and-ef6/porting/)때 사용할 EF Core 대상 버전의 기능 가용성을 검토 합니다. [및 EDMX 기반 모델과](/ef/efcore-and-ef6/porting/port-edmx) [코드 기반 모델의](/ef/efcore-and-ef6/porting/port-code)포팅 포팅에 대 한 설명서를 검토 합니다.

EF Core 2.2으로 업그레이드 하려면 적절 한 NuGet 패키지를 추가 하 고 네임 스페이스를 업데이트 하는 것이 관련 된 기본 단계입니다. 그런 다음 연결 문자열을 형식으로 전달 하는 방법 및 종속성 주입을 위해 연결 문자열을 연결 하는 `DbContext` 방법을 조정 합니다.

EF Core는 프로젝트에 대 한 패키지 참조로 추가 됩니다.

```xml
<PackageReference Include="Microsoft.EntityFrameworkCore" Version="2.2.6" />
```

EF 6에 대 한 참조가 제거 됩니다.

```xml
<PackageReference Include="EntityFramework" Version="6.2.0" />
```

컴파일러는 및에서 오류를 보고 합니다 `CatalogDBContext` `CatalogDBInitializer` . `CatalogDbContext` 이전 네임 스페이스가 제거 되 고로 대체 되어야 `Microsoft.EntityFrameworkCore` 합니다. 해당 생성자를 제거할 수 있습니다. `DbModelBuilder` 는로 바꾸어야 합니다 `ModelBuilder` . 형식을 구성 하기 위한 도우미 메서드는를 구현 하는 별도의 클래스로 이동 됩니다 `IEntityTypeConfiguration<T>` . 그런 다음 `CatalogDBContext` 클래스의 `OnModelCreating` 메서드는 다음과 같이 됩니다.

```csharp
protected override void OnModelCreating(ModelBuilder builder)
{
    builder.ApplyConfigurationsFromAssembly(Assembly.GetExecutingAssembly());

    base.OnModelCreating(builder);
}
```

관련 된 다른 변경 내용은 다음과 같습니다.

- `HasDatabaseGeneratedOption(DatabaseGeneratedOption.None)` 로 바뀜 `ValueGeneratedNever()`
- `HasRequired<T>` 로 바뀜 `HasOne<T>`
- 설치 된 `Microsoft.EntityFrameworkCore.Relational` 패키지
- 생성자를 추가 하 `CatalogDBContext` 여 `DbContextOptions` 기본 생성자에 전달 합니다.

에 대 한 예제 구성 클래스 `CatalogType` 는 다음과 같습니다.

```csharp
using Microsoft.EntityFrameworkCore;
using Microsoft.EntityFrameworkCore.Metadata.Builders;

namespace eShopPorted.Models.Config
{
    public class CatalogTypeConfig : IEntityTypeConfiguration<CatalogType>
    {
        public void Configure(EntityTypeBuilder<CatalogType> builder)
        {
            builder.ToTable(nameof(CatalogType));

            builder.HasKey(ci => ci.Id);

            builder.Property(ci => ci.Id)
               .IsRequired();

            builder.Property(cb => cb.Type)
                .IsRequired()
                .HasMaxLength(100);
        }
    }
}
```

`CatalogDBInitializer`및 해당 기본 클래스는 `CreateDatabaseIfNotExists<T>` EF Core와 호환 되지 않습니다. 이 클래스의 목적은 데이터베이스를 만들고 시드 하는 것입니다. EF Core를 사용 하면 다음 메서드를 사용 하 여 [에 `DbContext` 대 한 연결 된 데이터베이스를 만들고 삭제할](/ef/core/managing-schemas/ensure-created) 수 있습니다.

```csharp
dbContext.Database.EnsureDeleted();
dbContext.Database.EnsureCreated();
```

EF Core에서 데이터 시드는 수동 스크립트를 사용 하거나 유형 구성의 일부로 수행할 수 있습니다. 다른 엔터티 속성과 함께를 사용 하 여 클래스에서 초기값 데이터를 구성할 수 있습니다 `IEntityTypeConfiguration` `builder.HasData()` . 원래 앱이 *설치* 디렉터리의 CSV 파일에서 초기값 데이터를 로드 했습니다. 항목의 수가 적은 경우에는 이러한 데이터 레코드를 엔터티 구성의 일부로 추가할 수 있습니다. 이 방법은 자주 변경 되지 않는 테이블의 조회 데이터에 적합 합니다. 다음을 `CatalogTypeConfig` 의 메서드에 추가 하면 `Configure` 데이터베이스를 만들 때 연결 된 행이 표시 됩니다.

```csharp
builder.HasData(
    new CatalogType { Id = 1, Type = "Mug" },
    new CatalogType { Id = 2, Type = "T-Shirt" },
    new CatalogType { Id = 3, Type = "Sheet" },
    new CatalogType { Id = 4, Type = "USB Memory Stick" }
);
```

초기 앱에는 `PreconfiguredData` 및에 대 한 데이터를 포함 하는 클래스가 포함 되어 `CatalogBrand` `CatalogType` 있으므로이 메서드를 사용 하 여 `HasData` 호출은 다음과 같이 줄어듭니다.

```csharp
builder.HasData(
    PreconfiguredData.GetPreconfiguredCatalogBrands()
);
```

`CatalogItem`또한에서 데이터를 끌어올 수 `PreconfiguredData` 있으며, 연결 된 이미지가 소스 제어에 유지 되는 것으로 가정 합니다. 즉, 앱이 작동 하는 데 필요한 마지막 테이블입니다. `CatalogDBInitializer`클래스에 대 한 모든 참조와 함께 클래스를 제거할 수 있습니다. `CatalogItemHiLoGenerator`디렉터리의 클래스와 SQL 파일도 `Infrastructure` 제거 됩니다 (의) .이 파일에 대 한 참조도 함께 제거 `CatalogService` 됩니다 `ApplicationModule` .

에 대 한 특수 키 생성기 클래스를 제거 하면 `CatalogItem` 이제에서이 코드가 제거 됩니다 `CatalogItemConfig` .

```csharp
builder.Property(ci => ci.Id)
    .ValueGeneratedNever()
    .IsRequired();
```

이러한 수정 작업을 수행 하면 ASP.NET Core 앱은 빌드되고 아직 종속성 주입을 위해 구성 해야 하는 EF Core에서 작동 하지 않습니다. EF Core를 사용 하 여 구성 하는 가장 간단한 방법은 `ConfigureServices` 다음과 같습니다.

```csharp
public IServiceProvider ConfigureServices(IServiceCollection services)
{
    services.AddMvc();
    bool useMockData = Configuration.GetValue<bool>("UseMockData");
    if (!useMockData)
    {
        string connectionString = Configuration.GetConnectionString("DefaultConnection");

        services.AddDbContext<CatalogDBContext>(options =>
            options.UseSqlServer(connectionString)
        );
    }

    // Create Autofac container builder
    var builder = new ContainerBuilder();
    builder.Populate(services);
    builder.RegisterModule(new ApplicationModule(useMockData));

    ILifetimeScope container = builder.Build();

    return new AutofacServiceProvider(container);
}
```

Autofac의 최종 버전은 `ApplicationModule` 앱이 모의 데이터를 사용 하도록 구성 되었는지 여부에 따라 한 가지 유형만 구성 합니다.

```csharp
public class ApplicationModule : Module
{
    private bool _useMockData;

    public ApplicationModule(bool useMockData)
    {
        _useMockData = useMockData;
    }

    protected override void Load(ContainerBuilder builder)
    {
        if (_useMockData)
        {
            builder.RegisterType<CatalogServiceMock>()
                .As<ICatalogService>()
                .SingleInstance();
        }
        else
        {
            builder.RegisterType<CatalogService>()
                .As<ICatalogService>()
                .InstancePerLifetimeScope();
        }
    }
}
```

이식 된 앱은 실행 되지만 비 모의 데이터를 사용 하도록 구성 된 경우에는 데이터를 표시 하지 않습니다. 를 통해 추가 된 초기값 데이터는 `HasData` 마이그레이션이 적용 될 때만 삽입 됩니다. 원본 앱은 마이그레이션을 사용 하지 않았으며, 있는 경우에는 그대로 마이그레이션하지 않습니다. 가장 좋은 방법은 새 마이그레이션 스크립트를 시작 하는 것입니다. 이렇게 하려면에 대 한 패키지 참조를 추가 하 `Microsoft.EntityFrameworkCore.Design` 고 프로젝트 루트에서 터미널 창을 엽니다. 다음을 실행합니다.

```dotnetcli
dotnet ef migrations add Initial
```

기존 *eShopPorted* 데이터베이스 (있는 경우)를 삭제 하 고 다음을 실행 합니다.

```dotnetcli
dotnet ef database update
```

이렇게 하면 데이터베이스가 만들어지고 시드 됩니다. 이제 몇 개의 작은 업데이트를 처리할 수 있는 몇 개의 작은 업데이트가 실행 될 준비가 되었습니다.

## <a name="fix-all-todo-tasks"></a>모든 TODO 작업 수정

이 시점에서 이식 된 앱을 실행 하면 페이지에 표시 되는 그림이 표시 되지 않습니다. `PictureUri`의 속성이 설정 되지 않기 때문입니다 `CatalogItem` . `TODO`Visual Studio의 **작업 목록** 을 사용 하 여 만든 항목의 목록을 보면 그대로 남아 있는 항목은 `CatalogController` "Wwwroot에서 pic를 참조 하십시오."에 대 한 참고 사항입니다. 문제의 코드는 다음과 같습니다.

```csharp
private void AddUriPlaceHolder(CatalogItem item)
{
    //TODO: Reference pic from wwwroot
    //item.PictureUri = this.Url.RouteUrl(PicController.GetPicRouteName, new { catalogItemId = item.Id }, this.Request.Url.Scheme);
}
```

가장 간단한 픽스는 사이트의 공용 *wwwroot/Pics* 디렉터리에서 공용 이미지 파일을 참조 하는 것입니다. 이 작업을 수행 하려면 메서드를 다음 코드로 바꿉니다.

```csharp
private void AddUriPlaceHolder(CatalogItem item)
{
    item.PictureUri = $"/Pics/{item.Id}.png";
}
```

이러한 변경으로 응용 프로그램을 실행 하면 이미지가 이전 처럼 작동 합니다.

## <a name="additional-mvc-customizations"></a>추가 MVC 사용자 지정

*EShopLegacyMVC* 앱은 매우 간단 하므로 기본 MVC 동작을 기준으로 구성 하는 것이 많지 않습니다. 그러나 CORS, 필터 및 경로 제약 조건과 같은 추가 MVC 구성 요소를 구성 해야 하는 경우 일반적으로가 호출 되는에서이 정보를 제공 `Startup.ConfigureServices` `UseMvc` 합니다. 예를 들어 다음 코드 목록에서는 [CORS](/aspnet/core/security/cors?preserve-view=true&view=aspnetcore-2.2) 를 구성 하 고 전역 작업 필터를 설정 합니다.

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddCors(options =>
    {
        options.AddPolicy(MyAllowSpecificOrigins,
            builder =>
                builder.WithOrigins("http://example.com", "http://www.contoso.com")
                    .AllowAnyHeader()
                    .AllowAnyMethod());
    });

    services.AddMvc(options =>
    {
      options.Filters.Add(new SampleGlobalActionFilter());
    }).SetCompatibilityVersion(CompatibilityVersion.Version_2_2);
}
```

> [!Note]
> CORS 구성을 완료 하려면에서도 호출 해야 합니다 `app.UseCors()` `Configure` .

[사용자 지정 모델 바인더](/aspnet/core/mvc/advanced/custom-model-binding?preserve-view=true&view=aspnetcore-2.2), 포맷터 등을 추가 하는 등의 기타 고급 시나리오는 자세한 ASP.NET Core 문서에 설명 되어 있습니다. 일반적으로 개별 컨트롤러 또는 작업에 적용 되거나 이전 코드 목록에 표시 된 것과 동일한 옵션 방법을 사용 하 여 전역적으로 적용 될 수 있습니다.

## <a name="other-dependencies"></a>기타 종속성

WCF 클라이언트 형식 및 추적 코드와 같이 레거시 구성 모델에 대 한 종속성이 있는 .NET Framework 기능을 사용 하는 종속성은 이식 될 때 수정 해야 합니다. 이러한 형식이 구성 정보를 직접 가져오도록 하는 대신 코드에서 구성 해야 합니다. 예를 들어 ASP.NET 앱의 *web.config* 에 구성 된 WCF 서비스에 대 한 연결은 `basicHttpBinding` 대신 다음 코드를 사용 하 여 프로그래밍 방식으로 구성할 수 있습니다.

```csharp
var binding = new BasicHttpBinding();
binding.MaxReceivedMessageSize = 2_000_000;

var endpointAddress = new EndpointAddress("http://localhost:9200/ExampleService");

var myClient = new MyServiceClient(binding, endpointAddress);
```

WCF 클라이언트와 기타 .NET Framework 형식에는 설정에 대 한 구성 파일을 의존 하는 대신 해당 설정이 코드에 지정 되어 있어야 합니다. 이러한 방식으로 구성 된 이러한 형식은 ASP.NET Core 2.2 앱에서 계속 작동할 수 있습니다.

## <a name="references"></a>참조

- [eShopModernizing GitHub 리포지토리](https://github.com/dotnet-architecture/eShopModernizing)
- [.NET 업그레이드 도우미 도구](https://aka.ms/dotnet-upgrade-assistant)
- [API 및 ViewModels 도메인 모델을 참조할 수 없습니다.](https://ardalis.com/your-api-and-view-models-should-not-reference-domain-models/)
- [개발자 예외 페이지 미들웨어](/aspnet/core/fundamentals/error-handling#developer-exception-page)
- [EF Core HasData 심층 살펴보기](/archive/msdn-magazine/2018/august/data-points-deep-dive-into-ef-core-hasdata-seeding)

>[!div class="step-by-step"]
>[이전](more-migration-scenarios.md)
>[다음](deployment-scenarios.md)
