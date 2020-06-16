---
title: 이식 가능한 클래스 라이브러리로 크로스 플랫폼 개발
description: .NET에서 이식 가능한 클래스 라이브러리 프로젝트 형식을 사용 하 여 Microsoft 플랫폼용 플랫폼 간 앱 및 라이브러리를 빠르고 쉽게 빌드합니다.
ms.date: 09/17/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- Portable Class Library [.NET Framework]
- targeting multiple platforms
- multiple platforms, targeting
ms.assetid: c31e1663-c164-4e65-b66d-d3aa8750a154
ms.openlocfilehash: be1a49f7da7ce98f9e5e3ff8d927ce5230bfa8d8
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/15/2020
ms.locfileid: "84769147"
---
# <a name="cross-platform-development-with-the-portable-class-library"></a>이식 가능한 클래스 라이브러리를 사용 하 여 플랫폼 간 개발

Visual Studio의 이식 가능한 클래스 라이브러리 프로젝트 형식을 사용 하면 Microsoft 플랫폼용 플랫폼 간 앱 및 라이브러리를 빠르고 쉽게 빌드할 수 있습니다.

[!INCLUDE[standard](../../../includes/pcl-to-standard.md)]

이식 가능한 클래스 라이브러리를 사용하면 코드 개발 및 테스트에 드는 시간과 비용을 줄일 수 있습니다. 이 프로젝트 형식을 사용 하 여 이식 가능한 .NET Framework 어셈블리를 작성 하 고 빌드한 다음 .NET Framework, iOS, Mac 등의 여러 플랫폼을 대상으로 하는 앱에서 해당 어셈블리를 참조 합니다.

Visual Studio에서 이식 가능한 클래스 라이브러리 프로젝트를 만든 다음 해당 프로젝트 개발을 시작한 후에도 대상 플랫폼을 변경할 수 있습니다. Visual Studio는 새 어셈블리를 사용 하 여 라이브러리를 컴파일하여 코드에서 수행 해야 하는 변경 내용을 식별 하는 데 도움이 됩니다.

## <a name="create-a-portable-class-library-project"></a>이식 가능한 클래스 라이브러리 프로젝트 만들기

이식 가능한 클래스 라이브러리를 만들려면 Visual Studio에서 제공 하는 템플릿을 사용 합니다. 새 프로젝트를 만들고 (새 프로젝트**파일**  >  **New Project**) **새 프로젝트** 대화 상자에서 프로그래밍 언어 (Visual c # 또는 Visual Basic)를 선택 합니다. 그런 다음 **클래스 라이브러리 (레거시 이식 가능)** 템플릿을 선택 합니다. 프로젝트의 이름을 입력 하 고 **확인**을 선택 합니다.

**이식 가능한 클래스 라이브러리 추가** 대화 상자가 나타납니다. 대상을 두 개 이상 선택한 다음 **확인**을 선택 합니다.

![Visual Studio에서 이식 가능한 클래스 라이브러리 대상 추가](media/add-portable-class-library.png)

## <a name="change-targets"></a>변경 대상

이식 가능한 클래스 라이브러리 프로젝트를 만들거나 개발을 시작한 후에는 대상 플랫폼을 변경할 수 있습니다. 프로젝트를 만든 후 대상을 변경 하려면 **솔루션 탐색기**에서 이식 가능한 클래스 라이브러리 프로젝트 (솔루션이 아님)에 대 한 바로 가기 메뉴를 열고 **속성**을 선택 합니다. 프로젝트 속성 페이지의 **라이브러리** 탭에는 현재 프로젝트에서 대상으로 하는 플랫폼이 표시 됩니다.

![Visual Studio의 이식 가능한 클래스 라이브러리에 대 한 프로젝트 속성](media/pcl-project-properties.png)

대상을 추가 하거나 제거 하려면 **변경** 단추를 선택한 다음 해당 확인란을 선택 하 고 선택 취소 합니다.

대상을 변경하면 프로젝트 개발에 사용할 수 있는 API가 선택에 맞춰 변경됩니다. Visual Studio에서는 대상 변경의 결과로 발생할 수 있는 오류 및 경고를 보고합니다.

Visual Studio를 변경 하기 전에 어셈블리의 이식성을 평가 하려는 경우 [.Net 이식성 분석기](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer)를 사용할 수 있습니다.

## <a name="supported-types-and-members"></a>지원되는 형식 및 멤버

이식 가능한 클래스 라이브러리 프로젝트에서 사용할 수 있는 형식 및 멤버는 다음과 같이 여러 호환성 요소로 제한됩니다.

- 이들은 선택한 대상 간에 공유되어야 합니다.

- 이들은 이러한 여러 대상에서 유사하게 작동해야 합니다.

- 이들은 사용 중단 후보가 되어서는 안 됩니다.

- 이들은 특히 지원하는 멤버를 이식할 수 없을 때 이식 가능한 환경에서 의미가 있어야 합니다.

멤버가 이식 가능한 클래스 라이브러리에서 그리고 선택한 대상에 대해 지원되는 경우 IntelliSense의 프로젝트에 나타납니다. 그러나 이식 가능한 클래스 라이브러리에서 API가 지원될 수는 있지만 API를 사용할 수 있는지 여부는 선택한 대상에 따라 달라집니다.

## <a name="api-differences-in-the-portable-class-library"></a>이식 가능한 클래스 라이브러리에서의 API 차이점

이식 가능한 클래스 라이브러리 어셈블리가 지원되는 모든 플랫폼에서 호환되도록 하기 위해 이식 가능한 클래스 라이브러리에서 일부 멤버가 약간 변경되었습니다.

## <a name="use-the-portable-class-library"></a>이식 가능한 클래스 라이브러리 사용

이식 가능한 클래스 라이브러리 프로젝트를 빌드한 후에는 다른 프로젝트에서 이 프로젝트를 참조하게 합니다. 액세스하려는 클래스가 포함된 프로젝트 또는 특정 어셈블리를 참조할 수 있습니다.

이식 가능한 클래스 라이브러리 어셈블리를 참조하는 앱을 실행하려면 대상 플랫폼의 필수 버전(또는 이후 버전)이 컴퓨터에 설치되어 있어야 합니다. Visual Studio에는 필요한 모든 프레임워크가 포함되므로 앱을 개발하는 데 사용한 컴퓨터에서 더 이상의 수정 없이 앱을 실행할 수 있습니다.

### <a name="deploy-a-universal-windows-app"></a>유니버설 Windows 앱 배포

이식 가능한 클래스 라이브러리 어셈블리를 참조 하는 유니버설 Windows 앱을 만드는 경우 앱을 배포 하는 데 필요한 모든 항목이 앱 패키지에 포함 되며 추가 단계가 필요 하지 않습니다.

### <a name="deploy-a-net-framework-app"></a>.NET Framework 앱 배포

이식 가능한 클래스 라이브러리 어셈블리를 참조하는 .NET Framework 앱을 배포할 때 종속성을 올바른 .NET Framework 버전에 지정해야 합니다. 이 종속성을 지정하여 응용 프로그램에 필수 버전이 설치되도록 해야 합니다.

- ClickOnce 배포를 사용 하 여 종속성을 만들려면: **솔루션 탐색기**에서 게시할 프로젝트에 대 한 프로젝트 노드를 선택 합니다. 이식 가능한 클래스 라이브러리 프로젝트를 참조 하는 프로젝트입니다. 메뉴 모음에서 **프로젝트**  >  **속성**을 선택한 다음 **게시** 탭을 선택 합니다. **게시** 페이지에서 **필수 구성 요소**를 선택 합니다. 필수 .NET Framework 버전을 필수 구성 요소로 선택합니다.

- 설치 프로젝트를 사용 하 여 종속성을 만들려면: **솔루션 탐색기**에서 설치 프로젝트를 선택 합니다. 메뉴 모음에서 **프로젝트**  >  **속성**  >  **필수 구성 요소**를 선택 합니다. 필수 .NET Framework 버전을 필수 구성 요소로 선택합니다.

.NET Framework 앱을 배포 하는 방법에 대 한 자세한 내용은 [개발자를 위한 배포 가이드](../../framework/deployment/deployment-guide-for-developers.md)를 참조 하세요.

## <a name="see-also"></a>참고 항목

- [MVVM과 함께 이식 가능한 클래스 라이브러리 사용](using-portable-class-library-with-model-view-view-model.md)
- [여러 플랫폼을 대상으로 하는 라이브러리의 앱 리소스](app-resources-for-libraries-that-target-multiple-platforms.md)
- [.NET 이식성 분석기](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer)
- [Windows 스토어 앱 및 Windows 런타임에 대한 .NET Framework 지원](support-for-windows-store-apps-and-windows-runtime.md)
- [배포](../../framework/deployment/net-framework-applications.md)
