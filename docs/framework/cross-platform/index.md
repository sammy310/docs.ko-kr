---
description: '자세한 정보: .NET Framework로 여러 플랫폼 개발'
title: .NET Framework로 여러 플랫폼 개발
ms.date: 10/21/2020
ms.assetid: b153baaa-130c-4169-860b-e580591de91e
ms.openlocfilehash: 6223da53a4b2bf26e793ac01f31d9d1bfeb03f9d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786481"
---
# <a name="develop-for-multiple-platforms-with-net-framework"></a>.NET Framework로 여러 플랫폼 개발

.NET Framework 및 Visual Studio를 사용하여 Microsoft 플랫폼과 Microsoft 이외의 플랫폼 둘 모두에서 사용할 수 있는 앱을 개발할 수 있습니다.

[!INCLUDE [net-framework-future](../../../includes/net-framework-future.md)]

## <a name="options-for-cross-platform-development"></a>플랫폼 간 개발 옵션

[!INCLUDE[standard](../../../includes/pcl-to-standard.md)]

여러 플랫폼용으로 개발하기 위해 소스 코드 또는 바이너리를 공유하고 .NET Framework 코드와 Windows 런타임 API 간에 호출할 수 있습니다.

|다음을 원하는 경우...|다음을 사용...|
|-----------------------|------------|
|Windows Phone 8.1과 Windows 8.1 앱 간에 소스 코드 공유|**공유된 프로젝트**(Visual Studio 2013 업데이트 2의 유니버설 앱 템플릿).<br /><br /> - 현재 Visual Basic은 지원되지 않습니다.<br />- #`if` 문을 사용하여 플랫폼별 코드를 구분할 수 있습니다.<br /><br /> 자세한 내용은 다음을 참조하세요.<br /><br /> -   [코딩 시작](/windows/uwp/get-started/create-uwp-apps)<br />-   [Using Visual Studio to build Universal XAML Apps](https://devblogs.microsoft.com/visualstudio/using-visual-studio-to-build-universal-xaml-apps/)(Visual Studio를 사용하여 유니버설 XAML 앱 빌드)(블로그 게시물)<br />-   [Visual Studio를 사용한 XAML 컨버지드 앱 빌드](https://channel9.msdn.com/Events/Build/2014/3-591)(동영상)|
|여러 플랫폼을 대상으로 하는 앱 간에 바이너리 공유|플랫폼 제약이 없는 코드를 위한 **이식 가능한 클래스 라이브러리 프로젝트**.<br /><br /> - 이 접근 방식은 일반적으로 비즈니스 논리를 구현하는 코드에 사용됩니다.<br />- Visual Basic 또는 C#을 사용할 수 있습니다.<br />- API 지원은 플랫폼별로 다릅니다.<br />- Windows 8.1 및 Windows Phone 8.1을 대상으로 하는 이식 가능한 클래스 라이브러리 프로젝트는 Windows 런타임 API 및 XAML을 지원합니다. 이러한 기능은 이식 가능한 클래스 라이브러리의 이전 버전에서는 사용할 수 없습니다.<br />- 필요한 경우 인터페이스 또는 추상 클래스를 사용하여 플랫폼별 코드를 추출할 수 있습니다.<br /><br /> 자세한 내용은 다음을 참조하세요.<br /><br /> -   [이식 가능한 클래스 라이브러리](portable-class-library.md)<br />-   [How to Make Portable Class Libraries Work for You](/archive/blogs/dsplaisted/how-to-make-portable-class-libraries-work-for-you)(이식 가능한 클래스 라이브러리가 작동하도록 설정하는 방법)(블로그 게시물)<br />-   [MVVM과 함께 이식 가능한 클래스 라이브러리 사용](using-portable-class-library-with-model-view-view-model.md) <br />-   [여러 플랫폼을 대상으로 하는 라이브러리의 앱 리소스](app-resources-for-libraries-that-target-multiple-platforms.md) <br />-   [.NET 이식성 분석기](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer)(Visual Studio 확장)|
|Windows 8.1 및 Windows Phone 8.1 이외 플랫폼용 앱 간에 소스 코드 공유|**링크로 추가** 기능.<br /><br /> - 이 접근 방식은 몇 가지 이유로 두 앱에 공통으로 적용되지만 이식은 가능하지 않은 앱 논리에 적합합니다. 이 기능은 C# 또는 Visual Basic 코드에 사용할 수 있습니다.<br />     예를 들어, Windows Phone 8 및 Windows 8은 Windows 런타임 API를 공유하지만 이식 가능한 클래스 라이브러리는 이러한 플랫폼에 Windows 런타임을 지원하지 않습니다. `Add as link`를 사용하여 Windows Phone 8 앱과 Windows 8이 대상인 Windows 스토어 앱 간에 공통 Windows 런타임 코드를 공유할 수 있습니다.<br /><br /> 자세한 내용은 다음을 참조하세요.<br /><br /> -   [Share code with Add as Link](/previous-versions/windows/apps/jj714082(v=vs.105))(링크로 추가 기능을 통해 코드 공유)<br />-   [방법: 프로젝트에 기존 항목 추가](/previous-versions/visualstudio/visual-studio-2010/9f4t9t92(v=vs.100))|
|.NET Framework를 사용하여 Windows 스토어 앱 쓰기 또는 .NET Framework 코드에서 Windows 런타임 API 호출|.NET Framework C# 또는 Visual Basic 코드의 **Windows 런타임 API** .NET Framework를 사용하여 Windows 스토어 앱을 만듭니다. 두 플랫폼 간의 API 차이점을 알고 있어야 합니다. 그러나 이러한 차이점을 처리하는 데 도움이 되는 클래스가 있습니다.<br /><br /> 자세한 내용은 다음을 참조하세요.<br /><br /> -   [Windows 스토어 앱 및 Windows 런타임에 대한 .NET Framework 지원](support-for-windows-store-apps-and-windows-runtime.md) <br />-   [Windows 런타임에 URI 전달](passing-a-uri-to-the-windows-runtime.md) <br />-   <xref:System.IO.WindowsRuntimeStreamExtensions><br />-    <xref:System.WindowsRuntimeSystemExtensions>|
|Microsoft 이외의 플랫폼용 .NET Framework 앱 빌드|.NET Framework의 **이식 가능한 클래스 라이브러리 참조 어셈블리** 및 Visual Studio 확장 또는 Xamarin과 같은 타사 도구.<br /><br /> 자세한 내용은 다음을 참조하세요.<br /><br /> -   [Portable Class Library now available on all platforms](https://devblogs.microsoft.com/dotnet/portable-class-library-pcl-now-available-on-all-platforms/)(이제 모든 플랫폼에서 이식 가능한 클래스 라이브러리 사용) (블로그 게시물)<br />-   [Xamarin 설명서](/xamarin)|
|플랫폼 간 개발에 JavaScript 및 HTML 사용|Windows 8.1 및 Windows Phone 8.1용 Windows 런타임 API에 대해 개발하기 위한 Visual Studio 2013 업데이트 2의 **유니버설 앱 템플릿**. 현재 플랫폼 간 앱을 개발하기 위해 .NET Framework API를 JavaScript 및 HTML과 함께 사용할 수 없습니다.<br /><br /> 자세한 내용은 다음을 참조하세요.<br /><br /> -   [JavaScript 프로젝트 템플릿](/previous-versions/windows/apps/hh758331(v=win.10))<br />-   [JavaScript를 사용하여 Windows Phone에 Windows 런타임 앱 포팅](/previous-versions/windows/apps/dn636144(v=win.10))|
