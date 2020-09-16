---
title: .NET Framework로 여러 플랫폼 개발
ms.date: 07/18/2018
ms.technology: dotnet-standard
ms.assetid: b153baaa-130c-4169-860b-e580591de91e
ms.openlocfilehash: 770944f69abe2b6d4dcfd7baffcc282dbfb41274
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90547599"
---
# <a name="developing-for-multiple-platforms-with-the-net-framework"></a>.NET Framework로 여러 플랫폼 개발

.NET Framework 및 Visual Studio를 사용하여 Microsoft 플랫폼과 Microsoft 이외의 플랫폼 둘 모두에서 사용할 수 있는 앱을 개발할 수 있습니다.
  
## <a name="options-for-cross-platform-development"></a>플랫폼 간 개발 옵션

[!INCLUDE[standard](../../../includes/pcl-to-standard.md)]
  
 여러 플랫폼용으로 개발하기 위해 소스 코드 또는 바이너리를 공유하고 .NET Framework 코드와 Windows 런타임 API 간에 호출할 수 있습니다.  
  
|다음을 원하는 경우...|다음을 사용...|  
|-----------------------|------------|  
|Windows Phone 8.1과 Windows 8.1 앱 간에 소스 코드 공유|**공유 프로젝트** (Visual Studio 2013, 업데이트 2의 유니버설 응용 프로그램 템플릿).<br /><br /> -현재 Visual Basic 지원 하지 않습니다.<br />-# 문을 사용 하 여 플랫폼별 코드를 구분할 수 있습니다 `if` .<br /><br /> 자세한 내용은 다음을 참조하세요.<br /><br /> -   [코딩 시작](/windows/uwp/get-started/create-uwp-apps)<br />-   [Visual Studio를 사용 하 여 유니버설 XAML 앱 빌드](https://devblogs.microsoft.com/visualstudio/using-visual-studio-to-build-universal-xaml-apps/) (블로그 게시물)<br />-   [Visual Studio를 사용 하 여 XAML 수렴 형 앱 빌드](https://channel9.msdn.com/Events/Build/2014/3-591) (비디오)|  
|여러 플랫폼을 대상으로 하는 앱 간에 바이너리 공유|플랫폼에 구애 받지 않는 코드에 대 한 **이식 가능한 클래스 라이브러리 프로젝트** 입니다.<br /><br /> -일반적으로이 방법은 비즈니스 논리를 구현 하는 코드에 사용 됩니다.<br />-Visual Basic 또는 c #을 사용할 수 있습니다.<br />-API 지원은 플랫폼에 따라 달라 집니다.<br />-Windows 8.1 및 Windows Phone 8.1를 대상으로 하는 이식 가능한 클래스 라이브러리 프로젝트 Windows 런타임 Api 및 XAML을 지원 합니다. 이러한 기능은 이식 가능한 클래스 라이브러리의 이전 버전에서는 사용할 수 없습니다.<br />-필요한 경우 인터페이스 또는 추상 클래스를 사용 하 여 플랫폼별 코드를 추출할 수 있습니다.<br /><br /> 자세한 내용은 다음을 참조하세요.<br /><br /> -   [이식 가능한 클래스 라이브러리](cross-platform-development-with-the-portable-class-library.md)<br />-   [이식 가능한 클래스 라이브러리를 사용 하도록 설정 하는 방법](/archive/blogs/dsplaisted/how-to-make-portable-class-libraries-work-for-you) (블로그 게시물)<br />-   [MVVM와 함께 이식 가능한 클래스 라이브러리 사용](using-portable-class-library-with-model-view-view-model.md) <br />-   [여러 플랫폼을 대상으로 하는 라이브러리의 앱 리소스](app-resources-for-libraries-that-target-multiple-platforms.md) <br />-   [.Net 이식성 분석기](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer) (Visual Studio 확장)|  
|Windows 8.1 및 Windows Phone 8.1 이외 플랫폼용 앱 간에 소스 코드 공유|**링크로 추가 기능을 추가** 합니다.<br /><br /> -이 접근 방식은 어떤 이유로 인해 두 앱에 공통적 이지만 휴대용이 지 않은 앱 논리에 적합 합니다. 이 기능은 C# 또는 Visual Basic 코드에 사용할 수 있습니다.<br />     예를 들어, Windows Phone 8 및 Windows 8은 Windows 런타임 API를 공유하지만 이식 가능한 클래스 라이브러리는 이러한 플랫폼에 Windows 런타임을 지원하지 않습니다. `Add as link`를 사용하여 Windows Phone 8 앱과 Windows 8이 대상인 Windows 스토어 앱 간에 공통 Windows 런타임 코드를 공유할 수 있습니다.<br /><br /> 자세한 내용은 다음을 참조하세요.<br /><br /> -   [링크를 추가 하 여 코드 공유](/previous-versions/windows/apps/jj714082(v=vs.105))<br />-   [방법: 프로젝트에 기존 항목 추가](/previous-versions/visualstudio/visual-studio-2010/9f4t9t92(v=vs.100))|  
|.NET Framework를 사용하여 Windows 스토어 앱 쓰기 또는 .NET Framework 코드에서 Windows 런타임 API 호출|.NET Framework c # 또는 Visual Basic 코드에서 **api를 Windows 런타임** 하 고 .NET Framework를 사용 하 여 Windows 스토어 앱을 만듭니다. 두 플랫폼 간의 API 차이점을 알고 있어야 합니다. 그러나 이러한 차이점을 처리하는 데 도움이 되는 클래스가 있습니다.<br /><br /> 자세한 내용은 다음을 참조하세요.<br /><br /> -   [Windows 스토어 앱 및 Windows 런타임에 대 한 .NET Framework 지원](support-for-windows-store-apps-and-windows-runtime.md) <br />-   [Windows 런타임에 URI 전달](passing-a-uri-to-the-windows-runtime.md) <br />-   <xref:System.IO.WindowsRuntimeStreamExtensions><br />-    <xref:System.WindowsRuntimeSystemExtensions>|  
|Microsoft 이외의 플랫폼용 .NET Framework 앱 빌드|.NET Framework의 **이식 가능한 클래스 라이브러리 참조 어셈블리** 및 Visual Studio 확장 또는 Xamarin과 같은 타사 도구입니다.<br /><br /> 자세한 내용은 다음을 참조하세요.<br /><br /> -   [이제 모든 플랫폼에서 이식 가능한 클래스 라이브러리를 사용할 수 있습니다.](https://devblogs.microsoft.com/dotnet/portable-class-library-pcl-now-available-on-all-platforms/) (블로그 게시물)<br />-   [Xamarin 설명서](/xamarin)|  
|플랫폼 간 개발에 JavaScript 및 HTML 사용|Visual Studio 2013, 업데이트 2의 **범용 앱 템플릿으로** , Windows 8.1 및 Windows Phone 8.1에 대 한 Windows 런타임 api에 대해 개발 합니다. 현재 플랫폼 간 앱을 개발하기 위해 .NET Framework API를 JavaScript 및 HTML과 함께 사용할 수 없습니다.<br /><br /> 자세한 내용은 다음을 참조하세요.<br /><br /> -   [JavaScript 프로젝트 템플릿](/previous-versions/windows/apps/hh758331(v=win.10))<br />-   [JavaScript를 사용 하 여 Windows 런타임 앱 포팅 Windows Phone](/previous-versions/windows/apps/dn636144(v=win.10))|
