---
description: '자세한 정보: Visual Basic에서 `My` 네임스페이스 확장'
title: My 네임스페이스 확장
ms.date: 07/20/2015
f1_keywords:
- vb.AddingMyExtensions
helpviewer_keywords:
- My namespace [Visual Basic], customizing
- My namespace
- My namespace [Visual Basic], extending
ms.assetid: 808e8617-b01c-4135-8b21-babe87389e8e
ms.openlocfilehash: 896e85da14e6e8a417c93560b1d3b78a5954b769
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797967"
---
# <a name="extending-the-my-namespace-in-visual-basic"></a>Visual Basic에서 `My` 네임스페이스 확장

Visual Basic의 `My` 네임스페이스는 .NET Framework의 강력한 기능을 손쉽게 활용할 수 있게 하는 속성 및 메서드를 노출합니다. `My` 네임스페이스는 일반적인 프로그래밍 문제를 간소화하여 종종 어려운 작업을 한 줄 코드로 줄입니다. 또한 `My` 네임스페이스는 완전히 확장 가능하므로 `My`의 동작을 사용자 지정하고 해당 계층 구조에 새 서비스를 추가하여 특정 애플리케이션 요구 사항에 맞게 조정할 수 있습니다. 이 항목에서는 `My` 네임스페이스의 기존 멤버를 사용자 지정하는 방법과 `My` 네임스페이스에 고유한 사용자 지정 클래스를 추가하는 방법을 설명합니다.

## <a name="customizing-existing-my-namespace-members"></a>기존 `My` 네임스페이스 멤버 사용자 지정

Visual Basic의 `My` 네임스페이스는 애플리케이션, 컴퓨터 등에 대한 자주 사용되는 정보를 노출합니다. `My` 네임스페이스의 전체 개체 목록은 [내 참조](../../language-reference/keywords/my-reference.md)를 참조하세요. 애플리케이션의 요구 사항에 맞게 `My` 네임스페이스의 기존 멤버를 사용자 지정해야 할 수 있습니다. `My` 네임스페이스에 있는 읽기 전용이 아닌 개체의 모든 속성을 사용자 지정 값으로 설정할 수 있습니다.

예를 들어 애플리케이션을 실행하는 사용자의 현재 보안 컨텍스트에 액세스하는 데 `My.User` 개체를 자주 사용한다고 가정합니다. 그러나 회사에서는 사용자 지정 사용자 개체를 사용하여 회사 내의 사용자에 대한 추가 정보 및 기능을 노출합니다. 이 시나리오에서는 다음 예제와 같이 `My.User.CurrentPrincipal` 속성의 기본값을 사용자 지정 보안 주체 개체의 인스턴스로 바꿀 수 있습니다.

[!code-vb[VbVbcnExtendingMy#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnExtendingMy/VB/Class1.vb#1)]

`My.User` 개체의 `CurrentPrincipal` 속성을 설정하면 애플리케이션이 실행되는 ID가 변경됩니다. 그러면 `My.User` 개체는 새로 지정된 사용자에 대한 정보를 반환합니다.
  
## <a name="adding-members-to-my-objects"></a>`My` 개체에 멤버 추가

`My.Application` 및 `My.Computer`에서 반환된 형식은 `Partial` 클래스로 정의됩니다. 따라서 `MyApplication` 또는 `MyComputer`라는 `Partial` 클래스를 만들어 `My.Application` 및 `My.Computer` 개체를 확장할 수 있습니다. 클래스는 `Private` 클래스가 될 수 없습니다. 클래스를 `My` 네임스페이스의 일부로 지정하는 경우 `My.Application` 또는 `My.Computer` 개체에 포함될 속성과 메서드를 추가할 수 있습니다.

다음 예제에서는 `DnsServerIPAddresses`라는 속성을 `My.Computer` 개체에 추가합니다.

[!code-vb[VbVbcnExtendingMy#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnExtendingMy/VB/Class2.vb#2)]

## <a name="adding-custom-objects-to-the-my-namespace"></a>`My` 네임스페이스에 사용자 지정 개체 추가

`My` 네임스페이스는 여러 일반적인 프로그래밍 작업을 위한 솔루션을 제공하지만 `My` 네임스페이스가 해결하지 않는 작업이 발생할 수 있습니다. 예를 들어 애플리케이션이 사용자 데이터에 대한 사용자 지정 디렉터리 서비스에 액세스하거나 애플리케이션이 기본적으로 Visual Basic과 함께 설치되지 않은 어셈블리를 사용할 수 있습니다. `My` 네임스페이스를 확장하여 사용자 환경에 특정한 공통 작업에 대한 사용자 지정 솔루션을 포함할 수 있습니다. `My` 네임스페이스를 손쉽게 확장하여 증가하는 애플리케이션 요구를 충족하기 위한 새 멤버를 추가할 수 있습니다. 또한 `My` 네임스페이스 확장을 다른 개발자에게 Visual Basic 템플릿으로 배포할 수 있습니다.
  
### <a name="adding-members-to-the-my-namespace"></a>`My` 네임스페이스에 멤버 추가

`My`는 다른 모든 네임스페이스와 마찬가지의 네임스페이스이므로 모듈을 추가하고 `My`의 `Namespace`를 지정하여 최상위 속성을 추가할 수 있습니다. 다음 예제와 같이 `HideModuleName` 특성을 사용하여 모듈에 주석을 추가합니다. `HideModuleName` 특성은 IntelliSense에서 `My` 네임스페이스의 멤버를 표시할 때 모듈 이름을 표시하지 않도록 합니다.

[!code-vb[VbVbcnExtendingMy#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnExtendingMy/VB/Class1.vb#3)]

`My` 네임스페이스에 멤버를 추가하려면 필요에 따라 모듈에 속성을 추가합니다. `My` 네임스페이스에 추가된 각 속성에 대해 `ThreadSafeObjectProvider(Of T)` 형식(사용자 지정 속성에서 반환한 형식)의 전용 필드를 추가합니다. 이 필드는 `GetInstance` 메서드를 호출하여 속성에서 반환할 스레드로부터 안전한 개체 인스턴스를 만드는 데 사용됩니다. 결과적으로 확장 속성에 액세스하는 각 스레드는 반환된 형식의 고유한 인스턴스를 수신합니다. 다음 예제에서는 `SampleExtension`이라는 `SampleExtension` 형식의 속성을 `My` 네임스페이스에 추가합니다.

[!code-vb[VbVbcnExtendingMy#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnExtendingMy/VB/Class1.vb#4)]

## <a name="adding-events-to-custom-my-objects"></a>사용자 지정 `My` 개체에 이벤트 추가

`My.Application` 개체를 사용하여 `My` 네임스페이스의 `MyApplication` partial 클래스를 확장해 사용자 지정 `My` 개체에 대한 이벤트를 노출할 수 있습니다. Windows 기반 프로젝트의 경우 **솔루션 탐색기** 에서 프로젝트에 대한 **내 프로젝트** 노드를 두 번 클릭할 수 있습니다. Visual Basic **프로젝트 디자이너** 에서 **애플리케이션** 탭을 클릭한 다음 **애플리케이션 이벤트 보기** 단추를 클릭합니다. *ApplicationEvents.vb* 라는 새 파일이 생성됩니다. 여기에 `MyApplication` 클래스를 확장하는 다음 코드가 포함되어 있습니다.

[!code-vb[VbVbcnExtendingMy#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnExtendingMy/VB/Class1.vb#5)]

`MyApplication` 클래스에 사용자 지정 이벤트 처리기를 추가하여 사용자 지정 `My` 개체에 대한 이벤트 처리기를 추가할 수 있습니다. 사용자 지정 이벤트를 사용하면 이벤트 처리기가 추가 또는 제거될 때나 이벤트가 발생할 때 실행되는 코드를 추가할 수 있습니다. 사용자 지정 이벤트에 대한 `AddHandler` 코드는 사용자가 이벤트를 처리하기 위해 코드를 추가하는 경우에만 실행됩니다. 예를 들어 이전 섹션의 `SampleExtension` 개체에 사용자 지정 이벤트 처리기를 추가하려는 `Load` 이벤트가 있다고 가정합니다. 다음 코드 예제에서는 `My.SampleExtension.Load` 이벤트가 발생할 때 호출되는 `SampleExtensionLoad`라는 사용자 지정 이벤트 처리기를 보여 줍니다. 새 `My.SampleExtensionLoad` 이벤트를 처리하기 위해 코드를 추가하면 이 사용자 지정 이벤트 코드의 `AddHandler` 일부가 실행됩니다. `My.SampleExtensionLoad` 이벤트를 처리하는 이벤트 처리기의 예제를 보여 주기 위해 코드 예제에 `MyApplication_SampleExtensionLoad` 메서드가 포함되어 있습니다. `SampleExtensionLoad` 이벤트는 *ApplicationEvents.vb* 파일을 편집할 때 코드 편집기 위의 왼쪽 드롭다운 목록에서 **내 애플리케이션 이벤트** 옵션을 선택하면 사용할 수 있습니다.

[!code-vb[VbVbcnExtendingMy#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnExtendingMy/VB/Class1.vb#6)]

## <a name="design-guidelines"></a>디자인 지침

`My` 네임스페이스의 확장을 개발하는 경우 다음 지침을 사용하여 확장 구성 요소의 유지 관리 비용을 최소화합니다.

- **확장 논리만 포함합니다.** `My` 네임스페이스 확장에 포함된 논리에는 `My` 네임스페이스에 필요한 기능을 노출하는 데 필요한 코드만 포함되어야 합니다. 확장은 사용자 프로젝트에 소스 코드로 상주하기 때문에 확장 구성 요소를 업데이트할 경우 유지 관리 비용이 많이 발생하므로 가능한 한 업데이트를 피해야 합니다.
- **프로젝트 가정을 최소화합니다.** `My` 네임스페이스의 확장을 만들 때 참조, 프로젝트 수준 가져오기 또는 특정 컴파일러 설정(예: `Option Strict` 해제) 집합을 가정하지 마세요. 대신 `Global` 키워드를 사용하여 종속성을 최소화하고 모든 형식 참조를 정규화합니다. 또한 `Option Strict`를 설정한 상태로 확장을 컴파일하여 오류를 최소화합니다.
- **확장 코드를 격리합니다.** 코드를 단일 파일에 배치하면 확장을 Visual Studio 항목 템플릿으로 쉽게 배포할 수 있습니다. 자세한 내용은 이 항목의 뒷부분에 나오는 "확장 패키징 및 배포"를 참조하세요. 모든 `My` 네임스페이스 확장 코드를 단일 파일이나 프로젝트의 별도 폴더에 배치하면 사용자가 `My` 네임스페이스 확장을 찾는 데에도 도움이 됩니다.

## <a name="designing-class-libraries-for-my"></a>`My`용 클래스 라이브러리 디자인

대부분의 개체 모델과 마찬가지로 일부 디자인 패턴은 `My` 네임스페이스에서 잘 작동하고 다른 디자인 패턴은 그렇지 않습니다. `My` 네임스페이스에 대한 확장을 디자인하는 경우 다음 원칙을 고려하세요.

- **상태 비저장 메서드.** `My` 네임스페이스의 메서드는 특정 작업에 대한 완전한 솔루션을 제공해야 합니다. 메서드에 전달된 매개 변수 값이 특정 작업을 완료하는 데 필요한 모든 입력을 제공하는지 확인합니다. 리소스에 대한 열린 연결 등 이전 상태를 사용하는 메서드를 만들지 않아야 합니다.
- **전역 인스턴스.** `My` 네임스페이스에서 유지 관리되는 유일한 상태는 프로젝트에 대해 전역입니다. 예를 들어 `My.Application.Info`는 애플리케이션 전체에서 공유되는 상태를 캡슐화합니다.
- **간단한 매개 변수 형식.** 복잡한 매개 변수 형식을 방지하여 작업을 단순하게 유지합니다. 대신 매개 변수 입력을 취하지 않거나 문자열, 기본 형식 등의 간단한 입력 형식을 사용하는 메서드를 만듭니다.
- **팩터리 메서드.** 일부 형식은 인스턴스화하기 어렵습니다. 팩터리 메서드를 `My` 네임스페이스에 대한 확장으로 제공하면이 범주에 속하는 형식을 보다 쉽게 검색하고 사용할 수 있습니다. 잘 작동하는 팩터리 메서드의 예로는 `My.Computer.FileSystem.OpenTextFileReader`가 있습니다. .NET Framework에서 사용할 수 있는 몇 가지 스트림 유형이 있습니다. 텍스트 파일을 구체적으로 지정하여 `OpenTextFileReader`는 사용자가 어떤 스트림을 사용해야 할지 이해하는 데 도움이 됩니다.

다음 지침에서는 클래스 라이브러리에 대한 일반적인 디자인 원칙을 배제하지 않습니다. 오히려 Visual Basic 및 `My` 네임스페이스를 사용하는 개발자에게 최적화된 권장 사항입니다. 클래스 라이브러리 만들기에 대한 일반적인 디자인 원칙은 [프레임워크 디자인 지침](../../../standard/design-guidelines/index.md)을 참조하세요.

## <a name="packaging-and-deploying-extensions"></a>확장 패키징 및 배포

Visual Studio 프로젝트 템플릿에 `My` 네임스페이스 확장을 포함하거나 확장을 패키지하고 Visual Studio 항목 템플릿으로 배포할 수 있습니다. `My` 네임스페이스 확장을 Visual Studio 항목 템플릿으로 패키지할 경우 Visual Basic에서 제공하는 추가 기능을 활용할 수 있습니다. 이러한 기능을 사용하면 프로젝트에서 특정 어셈블리를 참조할 때 확장을 포함하거나 사용자가 Visual Basic 프로젝트 디자이너의 **My 확장** 페이지를 사용하여 `My` 네임스페이스 확장을 명시적으로 추가할 수 있습니다.

`My` 네임스페이스 확장을 배포하는 방법에 대한 자세한 내용은 [사용자 지정 My 확장 패키징 및 배포](packaging-and-deploying-custom-my-extensions.md)를 참조하세요.

## <a name="see-also"></a>참조

- [사용자 지정 My 확장명 패키징 및 배포](packaging-and-deploying-custom-my-extensions.md)
- [Visual Basic 애플리케이션 모델 확장](extending-the-visual-basic-application-model.md)
- [My에 사용할 수 있는 개체 사용자 지정](customizing-which-objects-are-available-in-my.md)
- [내 확장명 페이지, 프로젝트 디자이너](/visualstudio/ide/reference/my-extensions-page-project-designer-visual-basic)
- [프로젝트 디자이너, 애플리케이션 페이지(Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)
- [부분](../../language-reference/modifiers/partial.md)
