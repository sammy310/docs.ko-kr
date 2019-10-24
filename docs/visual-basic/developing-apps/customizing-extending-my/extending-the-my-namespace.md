---
title: Visual Basic에서 My 네임스페이스 확장
ms.date: 07/20/2015
f1_keywords:
- vb.AddingMyExtensions
helpviewer_keywords:
- My namespace [Visual Basic], customizing
- My namespace
- My namespace [Visual Basic], extending
ms.assetid: 808e8617-b01c-4135-8b21-babe87389e8e
ms.openlocfilehash: 6da0914c9d2d4dc1220ede5d6fa9f1aa6b43426a
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775295"
---
# <a name="extending-the-my-namespace-in-visual-basic"></a>Visual Basic에서 `My` 네임 스페이스 확장

Visual Basic의 `My` 네임 스페이스는 .NET Framework의 강력한 기능을 쉽게 활용할 수 있도록 하는 속성과 메서드를 노출 합니다. @No__t_0 네임 스페이스는 일반적인 프로그래밍 문제를 간소화 하 고, 종종 한 줄의 코드로 어려운 작업을 줄입니다. 또한 `My` 네임 스페이스는 완전히 확장 가능 하므로 `My`의 동작을 사용자 지정 하 고 해당 계층 구조에 새 서비스를 추가 하 여 특정 응용 프로그램 요구 사항에 맞게 조정할 수 있습니다. 이 항목에서는 `My` 네임 스페이스의 기존 멤버를 사용자 지정 하는 방법과 `My` 네임 스페이스에 고유한 사용자 지정 클래스를 추가 하는 방법에 대해 설명 합니다.

## <a name="customizing-existing-my-namespace-members"></a>기존 `My` 네임 스페이스 멤버 사용자 지정

Visual Basic의 `My` 네임 스페이스는 응용 프로그램, 컴퓨터 등에 대 한 자주 사용 되는 정보를 노출 합니다. @No__t_0 네임 스페이스에 있는 개체의 전체 목록은 [My Reference](../../language-reference/keywords/my-reference.md)를 참조 하세요. 응용 프로그램의 요구 사항에 맞게 `My` 네임 스페이스의 기존 멤버를 사용자 지정 해야 할 수 있습니다. 읽기 전용이 아닌 `My` 네임 스페이스에 있는 개체의 모든 속성을 사용자 지정 값으로 설정할 수 있습니다.

예를 들어 응용 프로그램을 실행 하는 사용자의 현재 보안 컨텍스트에 액세스 하는 데 `My.User` 개체를 자주 사용 한다고 가정 합니다. 그러나 회사에서는 사용자 지정 사용자 개체를 사용 하 여 회사 내의 사용자에 대 한 추가 정보 및 기능을 노출 합니다. 이 시나리오에서는 다음 예제와 같이 `My.User.CurrentPrincipal` 속성의 기본값을 사용자 지정 보안 주체 개체의 인스턴스로 바꿀 수 있습니다.

[!code-vb[VbVbcnExtendingMy#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnExtendingMy/VB/Class1.vb#1)]

@No__t_1 개체의 `CurrentPrincipal` 속성을 설정 하면 응용 프로그램이 실행 되는 id가 변경 됩니다. 그러면 `My.User` 개체는 새로 지정 된 사용자에 대 한 정보를 반환 합니다.
  
## <a name="adding-members-to-my-objects"></a>@No__t_0 개체에 멤버 추가

@No__t_0 및 `My.Computer`에서 반환 된 형식은 `Partial` 클래스로 정의 됩니다. 따라서 `MyApplication` 또는 `MyComputer` 이라는 `Partial` 클래스를 만들어 `My.Application` 및 `My.Computer` 개체를 확장할 수 있습니다. 클래스는 `Private` 클래스가 될 수 없습니다. 클래스를 `My` 네임 스페이스의 일부로 지정 하는 경우 `My.Application` 또는 `My.Computer` 개체에 포함 될 속성과 메서드를 추가할 수 있습니다.

다음 예제에서는 `DnsServerIPAddresses` 라는 속성을 `My.Computer` 개체에 추가 합니다.

[!code-vb[VbVbcnExtendingMy#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnExtendingMy/VB/Class2.vb#2)]

## <a name="adding-custom-objects-to-the-my-namespace"></a>@No__t_0 네임 스페이스에 사용자 지정 개체 추가

@No__t_0 네임 스페이스는 일반적인 여러 프로그래밍 작업을 위한 솔루션을 제공 하지만 `My` 네임 스페이스가 해결 하지 않는 작업이 발생할 수 있습니다. 예를 들어 응용 프로그램이 사용자 데이터에 대 한 사용자 지정 디렉터리 서비스에 액세스 하거나 응용 프로그램에서 기본적으로 Visual Basic와 함께 설치 되지 않은 어셈블리를 사용할 수 있습니다. @No__t_0 네임 스페이스를 확장 하 여 사용자 환경에 특정 한 일반 작업에 대 한 사용자 지정 솔루션을 포함할 수 있습니다. @No__t_0 네임 스페이스를 쉽게 확장 하 여 증가 하는 응용 프로그램 요구 사항을 충족 하는 새 멤버를 추가할 수 있습니다. 또한 `My` 네임 스페이스 확장을 다른 개발자에 게 Visual Basic 템플릿으로 배포할 수 있습니다.
  
### <a name="adding-members-to-the-my-namespace"></a>@No__t_0 네임 스페이스에 멤버 추가

@No__t_0는 다른 네임 스페이스와 같이 네임 스페이스 이므로 모듈을 추가 하 고 `My`의 `Namespace` 지정 하 여 최상위 속성을 추가할 수 있습니다. 다음 예제와 같이 `HideModuleName` 특성을 사용 하 여 모듈에 주석을 추가 합니다. @No__t_0 특성은 `My` 네임 스페이스의 멤버가 표시 될 때 IntelliSense에서 모듈 이름을 표시 하지 않도록 합니다.

[!code-vb[VbVbcnExtendingMy#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnExtendingMy/VB/Class1.vb#3)]

@No__t_0 네임 스페이스에 멤버를 추가 하려면 필요에 따라 모듈에 속성을 추가 합니다. @No__t_0 네임 스페이스에 추가 된 각 속성에 대해 형식이 사용자 지정 속성에서 반환 하는 형식인 `ThreadSafeObjectProvider(Of T)` 형식의 전용 필드를 추가 합니다. 이 필드는 `GetInstance` 메서드를 호출 하 여 속성에서 반환할 스레드로부터 안전한 개체 인스턴스를 만드는 데 사용 됩니다. 결과적으로 확장 속성에 액세스 하는 각 스레드는 반환 된 형식의 고유한 인스턴스를 수신 합니다. 다음 예에서는 `SampleExtension` 형식의 `SampleExtension` 라는 속성을 `My` 네임 스페이스에 추가 합니다.

[!code-vb[VbVbcnExtendingMy#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnExtendingMy/VB/Class1.vb#4)]

## <a name="adding-events-to-custom-my-objects"></a>사용자 지정 `My` 개체에 이벤트 추가

@No__t_0 개체를 사용 하 여 `My` 네임 스페이스의 `MyApplication` partial 클래스를 확장 하 여 사용자 지정 `My` 개체에 대 한 이벤트를 노출할 수 있습니다. Windows 기반 프로젝트의 경우 **솔루션 탐색기**에서 프로젝트에 대 한 **내 프로젝트** 노드를 두 번 클릭할 수 있습니다. Visual Basic **프로젝트 디자이너**에서 **응용 프로그램** 탭을 클릭 한 다음 **응용 프로그램 이벤트 보기** 단추를 클릭 합니다. *Applicationevents* 라는 새 파일이 생성 됩니다. @No__t_0 클래스를 확장 하는 다음 코드를 포함 합니다.

[!code-vb[VbVbcnExtendingMy#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnExtendingMy/VB/Class1.vb#5)]

@No__t_1 클래스에 사용자 지정 이벤트 처리기를 추가 하 여 사용자 지정 `My` 개체에 대 한 이벤트 처리기를 추가할 수 있습니다. 사용자 지정 이벤트를 사용 하면 이벤트 처리기가 추가, 제거 또는 이벤트가 발생할 때 실행 되는 코드를 추가할 수 있습니다. 사용자가 이벤트를 처리 하기 위해 코드를 추가 하는 경우에만 사용자 지정 이벤트에 대 한 `AddHandler` 코드를 실행 합니다. 예를 들어 이전 섹션의 `SampleExtension` 개체에는 사용자 지정 이벤트 처리기를 추가 하려는 `Load` 이벤트가 있습니다. 다음 코드 예제에서는 `My.SampleExtension.Load` 이벤트가 발생할 때 호출 되는 `SampleExtensionLoad` 이라는 사용자 지정 이벤트 처리기를 보여 줍니다. 새 `My.SampleExtensionLoad` 이벤트를 처리 하기 위해 코드를 추가 하면이 사용자 지정 이벤트 코드의 `AddHandler` 일부가 실행 됩니다. @No__t_0 메서드는 `My.SampleExtensionLoad` 이벤트를 처리 하는 이벤트 처리기의 예제를 보여 주기 위해 코드 예제에 포함 되어 있습니다. *Applicationevents .vb* 파일을 편집 하는 경우 코드 편집기 위의 왼쪽 드롭다운 목록에서 **내 응용 프로그램 이벤트** 옵션을 선택 하면 `SampleExtensionLoad` 이벤트를 사용할 수 있습니다.

[!code-vb[VbVbcnExtendingMy#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnExtendingMy/VB/Class1.vb#6)]

## <a name="design-guidelines"></a>디자인 지침

@No__t_0 네임 스페이스에 대 한 확장을 개발 하는 경우 다음 지침을 사용 하 여 확장 구성 요소의 유지 관리 비용을 최소화 합니다.

- **확장 논리도 포함 합니다.** @No__t_0 네임 스페이스 확장에 포함 된 논리에는 `My` 네임 스페이스에 필요한 기능을 제공 하는 데 필요한 코드를 포함 해야 합니다. 확장은 사용자 프로젝트에 소스 코드로 상주 하기 때문에 확장 구성 요소를 업데이트 하는 경우 유지 관리 비용이 크게 증가 하므로 가능 하면 피해 야 합니다.
- **프로젝트 가정을 최소화 합니다.** @No__t_0 네임 스페이스의 확장을 만들 때 참조, 프로젝트 수준 가져오기 또는 특정 컴파일러 설정 (예: `Option Strict` 해제)의 집합을 가정 하지 마세요. 대신 `Global` 키워드를 사용 하 여 종속성을 최소화 하 고 모든 형식 참조를 정규화 합니다. 또한 확장에서 오류를 최소화 하기 위해 `Option Strict` 설정 하 여 확장을 컴파일합니다.
- **확장 코드를 격리 합니다.** 코드를 단일 파일에 배치 하면 확장을 Visual Studio 항목 템플릿으로 쉽게 배포할 수 있습니다. 자세한 내용은이 항목의 뒷부분에 나오는 "확장 패키징 및 배포"를 참조 하십시오. 모든 `My` 네임 스페이스 확장 코드를 단일 파일이 나 프로젝트의 별도 폴더에 배치 하면 사용자가 `My` 네임 스페이스 확장을 찾을 수 있습니다.

## <a name="designing-class-libraries-for-my"></a>@No__t_0 클래스 라이브러리 디자인

대부분의 개체 모델을 사용 하는 경우와 마찬가지로 일부 디자인 패턴은 `My` 네임 스페이스에서 잘 작동 하 고 다른 일부는 그렇지 않습니다. @No__t_0 네임 스페이스에 대 한 확장을 디자인 하는 경우 다음 원칙을 고려 하십시오.

- **상태 비저장 메서드.** @No__t_0 네임 스페이스의 메서드는 특정 작업에 대 한 완전 한 솔루션을 제공 해야 합니다. 메서드에 전달 된 매개 변수 값이 특정 작업을 완료 하는 데 필요한 모든 입력을 제공 하는지 확인 합니다. 리소스에 대 한 열린 연결 등 이전 상태를 사용 하는 메서드를 만들지 않도록 합니다.
- **전역 인스턴스입니다.** @No__t_0 네임 스페이스에서 유지 관리 되는 유일한 상태는 프로젝트에 대 한 전역입니다. 예를 들어 `My.Application.Info`는 응용 프로그램 전체에서 공유 되는 상태를 캡슐화 합니다.
- **단순 매개 변수 유형입니다.** 복잡 한 매개 변수 형식을 방지 하 여 작업을 단순하게 유지 합니다. 대신, 매개 변수 입력을 취하지 않거나 문자열, 기본 형식 등의 간단한 입력 형식을 사용 하는 메서드를 만듭니다.
- **팩터리 메서드.** 일부 형식은 인스턴스화 하기 어렵습니다. 팩터리 메서드를 `My` 네임 스페이스에 대 한 확장으로 제공 하면이 범주에 속하는 형식을 보다 쉽게 검색 하 고 사용할 수 있습니다. 잘 작동 하는 팩터리 메서드의 예는 `My.Computer.FileSystem.OpenTextFileReader` 합니다. .NET Framework에서 사용할 수 있는 몇 가지 스트림 유형이 있습니다. 텍스트 파일을 구체적으로 지정 하면 `OpenTextFileReader` 사용자가 사용할 스트림을 이해 하는 데 도움이 됩니다.

이러한 지침에서는 클래스 라이브러리에 대 한 일반적인 디자인 원리를 배제 하지 않습니다. 대신 Visual Basic 및 `My` 네임 스페이스를 사용 하는 개발자에 게 최적화 된 권장 사항입니다. 클래스 라이브러리 만들기에 대 한 일반적인 디자인 원칙은 [프레임 워크 디자인 지침](../../../standard/design-guidelines/index.md)을 참조 하세요.

## <a name="packaging-and-deploying-extensions"></a>확장 패키징 및 배포

Visual Studio 프로젝트 템플릿에 `My` 네임 스페이스 확장을 포함 하거나 확장을 패키지 하 고 Visual Studio 항목 템플릿으로 배포할 수 있습니다. @No__t_0 네임 스페이스 확장을 Visual Studio 항목 템플릿으로 패키지할 경우 Visual Basic에서 제공 하는 추가 기능을 활용할 수 있습니다. 이러한 기능을 사용 하면 프로젝트에서 특정 어셈블리를 참조할 때 확장을 포함 하거나 사용자가 Visual Basic 프로젝트 디자이너의 **내 확장** 페이지를 사용 하 여 `My` 네임 스페이스 확장을 명시적으로 추가할 수 있습니다.

@No__t_0 네임 스페이스 확장을 배포 하는 방법에 대 한 자세한 내용은 [사용자 지정 내 확장 패키징 및 배포](packaging-and-deploying-custom-my-extensions.md)를 참조 하세요.

## <a name="see-also"></a>참조

- [사용자 지정 My 확장명 패키징 및 배포](packaging-and-deploying-custom-my-extensions.md)
- [Visual Basic 애플리케이션 모델 확장](extending-the-visual-basic-application-model.md)
- [My에 사용할 수 있는 개체 사용자 지정](customizing-which-objects-are-available-in-my.md)
- [내 확장명 페이지, 프로젝트 디자이너](/visualstudio/ide/reference/my-extensions-page-project-designer-visual-basic)
- [프로젝트 디자이너, 애플리케이션 페이지(Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)
- [부분](../../language-reference/modifiers/partial.md)
