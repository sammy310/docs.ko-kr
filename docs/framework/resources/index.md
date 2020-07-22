---
title: .NET 앱의 리소스
description: .NET 앱의 리소스를 이해합니다. 리소스는앱과 함께 논리적으로 배포되는 실행 불가능한 데이터입니다.
ms.date: 07/25/2018
helpviewer_keywords:
- deploying applications [.NET Framework], resources
- deploying applications [.NET Core], resources
- application resources
- resource files
- satellite assemblies
- localization
- packaging application resources
- localizing resources
ms.assetid: 8ad495d4-2941-40cf-bf64-e82e85825890
ms.openlocfilehash: 105325170389917bfb2022314791aa1ed5923db3
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/21/2020
ms.locfileid: "86865166"
---
# <a name="resources-in-net-apps"></a>.NET 앱의 리소스

거의 모든 프로덕션 품질 앱은 리소스를 사용합니다. 리소스는 앱과 함께 논리적으로 배포되는 실행 불가능한 데이터입니다. 리소스는 앱에서 오류 메시지로 표시되거나 사용자 인터페이스의 일부로 표시될 수 있습니다. 리소스에는 문자열, 이미지, 지속형 개체 등 수많은 형식의 데이터가 포함될 수 있습니다. (리소스 파일에 지속형 개체를 쓰려면 개체를 직렬화할 수 있어야 합니다.) 리소스 파일에 데이터를 저장하면 전체 앱을 다시 컴파일하지 않고도 데이터를 변경할 수 있습니다. 또한 데이터를 단일 위치에 저장할 수 있고, 여러 위치에 저장되어 있는 하드 코딩된 데이터를 사용하지 않아도 됩니다.

.NET Framework 및 .NET Core에서는 리소스 만들기 및 지역화를 포괄적으로 지원합니다. .NET은 지역화된 리소스를 패키징하고 배포하는 간단한 모델 또한 지원합니다.

ASP.NET의 리소스에 대한 자세한 내용은 [ASP.NET 페이지 리소스 개요](https://docs.microsoft.com/previous-versions/aspnet/ms227427(v=vs.100))를 참조하세요.

## <a name="create-and-localize-resources"></a>리소스 만들기 및 지역화

지역화되지 않은 앱에서 리소스 파일을 앱 데이터 리포지토리로 사용할 수 있습니다. 이는 특히 소스 코드의 여러 위치에서 하드 코딩해야 하는 문자열의 경우 유용합니다. 가장 일반적으로, 텍스트(.txt) 또는 XML(.resx) 파일 같은 리소스를 만들고 [Resgen.exe(리소스 파일 생성기)](../tools/resgen-exe-resource-file-generator.md)를 사용하여 이진 .resources 파일로 컴파일할 수 있습니다. 그런 다음 언어 컴파일러로 이러한 파일을 앱의 실행 파일에 포함할 수 있습니다. 리소스 파일 만들기에 대한 자세한 내용은 [리소스 파일 만들기](creating-resource-files-for-desktop-apps.md)를 참조하세요.

앱의 리소스를 특정 문화권에 맞게 지역화할 수도 있습니다. 이 경우 지역화된(번역된) 버전의 앱을 빌드할 수 있습니다. 지역화된 리소스를 사용하는 앱을 개발할 때, 중립적이거나 대체적인 역할을 하는 문화권을 지정하여 적절한 리소스를 사용할 수 없을 때 해당 문화권의 리소스를 사용해야 합니다. 일반적으로 중립 문화권의 리소스는 앱의 실행 파일에 저장됩니다. 지역화된 개별 문화권에 대한 나머지 리소스는 독립 실행형 위성 어셈블리에 저장됩니다. 자세한 내용은 [위성 어셈블리 만들기](creating-satellite-assemblies-for-desktop-apps.md)를 참조하세요.

## <a name="package-and-deploy-resources"></a>리소스 패키징 및 배포

지역화된 앱 리소스를 [위성 어셈블리](packaging-and-deploying-resources-in-desktop-apps.md)에 배포합니다. 위성 어셈블리는 단일 문화권의 리소스를 포함하지만 앱 코드는 포함하지 않습니다. 위성 어셈블리 배포 모델에서는 기본 어셈블리(보통 주 어셈블리) 하나와 앱에서 지원하는 각 문화권에 대한 위성 어셈블리 하나가 포함된 앱을 만들 수 있습니다. 위성 어셈블리는 주 어셈블리의 일부가 아니므로 앱의 주 어셈블리를 바꾸지 않고도 특정 문화권에 해당하는 리소스를 손쉽게 바꾸거나 업데이트할 수 있습니다.

앱의 기본 리소스 어셈블리를 구성할 리소스를 결정할 때는 주의해야 합니다. 기본 리소스 어셈블리는 주 어셈블리의 일부이므로 이 어셈블리를 변경하려면 주 어셈블리를 바꾸어야 합니다. 기본 리소스를 제공하지 않으면 [리소스 대체 프로세스](packaging-and-deploying-resources-in-desktop-apps.md)에서 리소스를 찾을 때 예외가 발생합니다. 잘 설계된 앱의 경우 리소스를 사용해도 예외가 발생하지 않습니다.

자세한 내용은 [리소스 패키징 및 배포](packaging-and-deploying-resources-in-desktop-apps.md)를 참조하세요.

## <a name="retrieve-resources"></a>리소스 검색

앱은 런타임에 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=nameWithType> 속성으로 지정된 문화권에 따라 적절하게 지역화된 리소스를 스레드별로 로드합니다. 이 속성 값은 다음과 같은 방식으로 파생됩니다.

- 지역화된 문화권을 나타내는 <xref:System.Globalization.CultureInfo> 개체를 <xref:System.Threading.Thread.CurrentUICulture%2A?displayProperty=nameWithType> 속성에 직접 할당합니다.

- 문화권이 명시적으로 할당되지 않은 경우에는 <xref:System.Globalization.CultureInfo.DefaultThreadCurrentUICulture%2A?displayProperty=nameWithType> 속성에서 기본 스레드 UI 문화권을 검색합니다.

- 기본 스레드 UI 문화권이 명시적으로 할당되지 않은 경우 로컬 컴퓨터의 현재 사용자에 대한 문화권을 검색합니다. Windows에서 실행되는 .NET 구현은 Windows [`GetUserDefaultUILanguage`](/windows/desktop/api/winnls/nf-winnls-getuserdefaultuilanguage) 함수를 호출하여 검색합니다.

현재 UI 문화권을 설정하는 방법에 대한 자세한 내용은 <xref:System.Globalization.CultureInfo> 및 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=nameWithType> 페이지를 참조하세요.

이후 <xref:System.Resources.ResourceManager?displayProperty=nameWithType> 클래스를 사용해 현재 UI 문화권 또는 특정 문화권에 대한 리소스를 검색할 수도 있습니다. 리소스를 검색하는 데 가장 일반적으로 사용되는 것은 <xref:System.Resources.ResourceManager> 클래스지만, <xref:System.Resources?displayProperty=nameWithType> 네임스페이스에는 리소스를 검색하는 데 사용할 수 있는 추가 형식이 포함되어 있습니다. 여기에는 다음이 포함됩니다.

- <xref:System.Resources.ResourceReader> 클래스: 어셈블리에 포함되거나 독립 실행형 이진 .resources 파일에 저장된 리소스를 열거할 수 있습니다. 런타임에 사용할 수 있는 리소스의 정확한 이름을 모르는 경우 유용합니다.

- <xref:System.Resources.ResXResourceReader> 클래스: XML(.resx) 파일에서 리소스를 검색할 수 있습니다.

- <xref:System.Resources.ResourceSet> 클래스: 대체 규칙을 준수하지 않고 특정 문화권의 리소스를 검색할 수 있습니다. 리소스는 어셈블리 또는 독립 실행형 이진 .resources 파일에 저장할 수 있습니다. <xref:System.Resources.IResourceReader> 클래스를 사용하여 다른 소스에서 리소스를 검색할 수 있도록 하는 <xref:System.Resources.ResourceSet> 구현을 개발할 수도 있습니다.

- <xref:System.Resources.ResXResourceSet> 클래스: 메모리에서 XML 리소스 파일에 있는 모든 항목을 검색할 수 있습니다.

## <a name="see-also"></a>참조

- <xref:System.Globalization.CultureInfo>
- <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=nameWithType>
- [리소스 파일 만들기](creating-resource-files-for-desktop-apps.md)
- [리소스 패키징 및 배포](packaging-and-deploying-resources-in-desktop-apps.md)
- [위성 어셈블리 만들기](creating-satellite-assemblies-for-desktop-apps.md)
- [리소스 검색](retrieving-resources-in-desktop-apps.md)
