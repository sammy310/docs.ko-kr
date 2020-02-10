---
title: External RuleSet Toolkit
ms.date: 03/30/2017
ms.assetid: a306d283-a031-475e-aa01-9ae86e7adcb0
ms.openlocfilehash: eb59b02d469788b23126f4e02c5b7ae5a63081f0
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2020
ms.locfileid: "77094672"
---
# <a name="external-ruleset-toolkit"></a>External RuleSet Toolkit

일반적으로 워크플로 애플리케이션 내에서 규칙이 사용될 경우 해당 규칙은 어셈블리의 일부입니다. 일부 시나리오에서는 워크플로 어셈블리를 다시 빌드하고 배포하지 않고도 RuleSet을 업데이트할 수 있도록 어셈블리와 별도로 RuleSet을 유지할 수 있습니다. 이 샘플에서는 데이터베이스에 있는 RuleSet을 관리하고 편집하며 런타임에 워크플로에서 이러한 RuleSet에 액세스할 수 있습니다. 따라서 워크플로 인스턴스를 실행하여 RuleSet 변경 내용을 자동으로 통합할 수 있습니다.

External RuleSet Toolkit 샘플에는 데이터베이스에서 RuleSet 버전을 관리하고 편집하는 데 사용할 수 있는 Windows Forms 기반 도구가 포함되어 있으며, 해당 규칙을 실행하는 호스트 서비스 및 활동도 포함되어 있습니다.

> [!NOTE]
> 이 샘플에는 [Microsoft SQL Server](/sql)필요 합니다.

Visual Studio는 Windows Workflow Foundation (WF)의 일부로 규칙 집합 편집기를 제공 합니다. 이 편집기는 워크플로의 `Policy` 활동을 두 번 클릭하여 시작할 수 있으며 정의된 RuleSet 개체를 워크플로와 연결된 .rules 파일로 serialize합니다. `Policy` 활동은 워크플로에 대해 RuleSet 인스턴스를 실행합니다. .rules 파일은 워크플로 프로젝트를 빌드할 때 리소스로 어셈블리에 컴파일됩니다.

이 샘플의 구성 요소는 다음과 같습니다.

- 데이터베이스에서 RuleSet 버전을 편집하고 관리하는 데 사용할 수 있는 RuleSet 그래픽 사용자 인터페이스

- 호스트 애플리케이션에서 구성되고 데이터베이스에서 RuleSet에 액세스하는 RuleSet 서비스

- RuleSet 서비스에서 RuleSet을 요청하고 워크플로에 대해 RuleSet을 실행하는 `ExternalPolicy` 활동

구성 요소의 상호 작용은 다음 그림에 나와 있습니다. 그 뒤에 나오는 단원에서는 각 구성 요소에 대해 설명합니다.

![외부 규칙 집합 도구 키트 샘플 개요를 보여 주는 다이어그램입니다.](./media/external-ruleset-toolkit/ruleset-toolkit-overview.gif)

> [!IMPORTANT]
> 컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> 이 디렉터리가 없으면 [.NET Framework 4에 대 한 Windows Communication Foundation (wcf) 및 Windows Workflow Foundation (WF) 샘플](https://www.microsoft.com/download/details.aspx?id=21459) 로 이동 하 여 모든 WINDOWS COMMUNICATION FOUNDATION (wcf) 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 다운로드 합니다. 이 샘플은 다음 디렉터리에 있습니다.
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ExternalRuleSetToolKit`

## <a name="ruleset-tool"></a>RuleSet 도구

다음 이미지는 규칙 집합 도구의 스크린샷입니다. **규칙 저장소** 메뉴를 통해 데이터베이스에서 사용 가능한 규칙 집합을 로드 하 고 수정 된 규칙 집합을 저장소에 다시 저장할 수 있습니다. 애플리케이션 구성 파일에서는 RuleSet 데이터베이스에 대한 데이터베이스 연결 문자열을 제공합니다. 도구를 시작하면 구성된 데이터베이스에서 RuleSet이 자동으로 로드됩니다.

![규칙 집합 브라우저를 보여 주는 스크린샷](./media/external-ruleset-toolkit/ruleset-browser-dialog.gif)

RuleSet 도구에서는 RuleSet에 주 버전 및 부 버전 번호를 적용하여 동시에 여러 버전을 유지하고 저장할 수 있게 합니다. 이 도구에서는 버전 관리 기능 이외에 잠금이나 기타 구성 관리 기능을 제공하지 않습니다. 이 도구를 사용하여 새 RuleSet 버전을 만들거나 기존 버전을 삭제할 수 있습니다. **새로 만들기**를 클릭 하면 도구에서 새 규칙 집합 이름을 만들고 버전 1.0을 적용 합니다. 버전을 복사하면 도구에서 포함된 규칙을 비롯하여 선택한 RuleSet 버전의 복사본을 만들고 고유한 새 버전 번호를 할당합니다. 이러한 버전 번호는 기존 RuleSet의 버전 번호를 기반으로 합니다. 양식에서 연결된 필드를 사용하여 RuleSet 이름 및 버전 번호를 변경할 수 있습니다.

**규칙 편집**을 클릭 하면 다음 이미지와 같이 규칙 집합 편집기가 시작 됩니다.

![규칙 집합 편집기를 보여 주는 스크린샷](./media/external-ruleset-toolkit/ruleset-editor-dialog.gif)

이는 Visual Studio 추가 기능 Windows Workflow Foundation의 일부인 편집기 대화 상자를 다시 호스팅하는 것입니다. Intellisense 지원을 비롯하여 편집기 대화 상자와 동일한 기능을 제공합니다. 규칙은 도구에서 규칙 집합에 연결 된 대상 유형 (예: 워크플로)에 대해 작성 됩니다. 주 도구 대화 상자에서 **찾아보기** 를 클릭 하면 그림 4에 표시 된 것 처럼 **워크플로/형식 선택기** 대화 상자가 나타납니다.

![워크플로 &#47;유형 선택](./media/71f08d57-e8f2-499e-8151-ece2cbdcabfd.gif "71f08d57-e8f2-499e-8151-ece2cbdcabfd")

그림 4: 워크플로/형식 선택기

**워크플로/형식 선택기** 대화 상자를 사용 하 여 어셈블리와 해당 어셈블리 내의 특정 형식을 지정할 수 있습니다. 이 형식은 규칙이 제작 및 실행되는 대상 형식입니다. 대부분의 경우 대상 형식은 워크플로나 다른 활동 형식입니다. 그러나 .NET 형식에 대해 RuleSet을 실행할 수 있습니다.

데이터베이스에서 규칙 집합이 검색 될 때 도구에서 대상 형식을 자동으로 로드 하도록 데이터베이스에서 어셈블리 파일 및 형식 `name are stored with the` 규칙 집합의 경로입니다.

**워크플로/형식 선택기** 대화 상자에서 **확인** 을 클릭 하면 대상 형식에 규칙에서 참조 하는 모든 멤버가 포함 되도록 규칙 집합에 대해 선택한 형식의 유효성을 검사 합니다. 오류는 **유효성 검사 오류** 대화 상자에 표시 됩니다. 오류가 발생 하더라도 변경을 계속 하도록 선택 하거나 **취소**를 클릭할 수 있습니다. 주 도구 대화 상자의 **도구** 메뉴에서 **유효성 검사** 를 클릭 하 여 대상 활동에 대해 규칙 집합 버전의 유효성을 다시 검사할 수 있습니다.

![유효성 검사 오류 대화 상자를 보여 주는 스크린샷](./media/external-ruleset-toolkit/validation-errors-dialog.png)

도구의 **데이터** 메뉴에서 규칙 집합을 가져오고 내보낼 수 있습니다. **가져오기**를 클릭 하면 rules 파일을 선택할 수 있는 파일 선택 대화 상자가 나타납니다. 이 파일은 처음에 Visual Studio에서 만든 파일 일 수도 있고 그렇지 않을 수도 있습니다. .rules 파일에는 조건 컬렉션과 RuleSet 컬렉션을 포함하는 serialize된 `RuleDefinitions` 인스턴스가 포함되어야 합니다. 도구는 조건 컬렉션을 사용 하지 않지만 Visual Studio 환경과의 상호 작용을 허용 하려면 `RuleDefinitions` 형식을 사용 합니다.

Rules 파일을 선택한 후에는 규칙 **집합 선택기** 대화 상자가 나타납니다. 이 대화 상자를 사용하여 파일에서 가져올 RuleSet을 선택할 수 있습니다. 기본적으로 모든 RuleSet으로 지정되어 있습니다. WF 프로젝트 내의 버전 관리는 어셈블리의 버전과 동일하기 때문에 .rules 파일의 RuleSet에는 버전 번호가 없습니다. 가져오기 프로세스 중에이 도구는 사용 가능한 다음 주 버전 번호를 자동으로 할당 합니다 (가져온 후 변경 가능). **규칙 집합 선택기** 목록에서 할당 된 버전 번호를 볼 수 있습니다.

도구는 가져오는 각 RuleSet에 대해 RuleSet에 사용된 멤버를 기반으로 .rules 파일(있는 경우)의 위치 아래에 있는 bin\Debug 폴더에서 연결된 형식을 찾으려고 합니다. RuleSet 도구에서 일치하는 형식을 여러 개 찾으면 .rules 파일 이름과 형식 이름이 일치하는 형식을 선택하려고 합니다. 예를 들어 `Workflow1` 형식은 Workflow1.rules에 대응합니다. 일치하는 항목이 여러 개 있으면 형식을 선택하라는 메시지가 표시됩니다. 이 자동 식별 메커니즘이 일치 하는 어셈블리나 유형을 찾지 못한 경우, 가져온 후 주 도구 대화 상자에서 **찾아보기** 를 클릭 하 여 연결 된 유형을 탐색할 수 있습니다. 다음 그림은 규칙 집합 선택기를 보여 줍니다.

![규칙 집합 선택 대화 상자를 보여 주는 스크린샷](./media/external-ruleset-toolkit/ruleset-selector-dialog.gif)

주 도구 메뉴에서 **데이터-내보내기** 를 클릭 하면 **규칙 집합 선택** 대화 상자가 다시 표시 됩니다 .이 대화 상자에서 내보낼 데이터베이스의 규칙 집합을 확인할 수 있습니다. **확인**을 클릭 하면 결과 파일의 이름과 위치를 지정할 수 있는 **파일 저장** 대화 상자가 나타납니다. .rules 파일에는 버전 정보가 저장되지 않으므로 지정된 RuleSet 이름을 사용하는 RuleSet 버전을 하나만 선택할 수 있습니다.

## <a name="policyfromservice-activity"></a>PolicyFromService 활동

`PolicyFromService` 활동에 대한 코드는 간단합니다. 이 활동은 WF와 함께 제공되는 `Policy` 활동과 매우 유사하게 작동하지만 .rules 파일에서 대상 RuleSet을 검색하는 대신 호스트 서비스를 호출하여 RuleSet 인스턴스를 가져옵니다. 그런 다음 루트 워크플로 활동 인스턴스에 대해 RuleSet을 실행합니다.

워크플로에서 활동을 사용하려면 워크플로 프로젝트에서 `PolicyActivities` 및 `RuleSetService` 어셈블리에 참조를 추가합니다. 도구 상자에 활동을 추가하는 방법에 대한 자세한 내용은 이 항목의 끝에 나오는 절차를 참조하세요.

워크플로에 활동을 배치한 후에는 실행할 RuleSet의 이름을 제공해야 합니다. 리터럴 값으로 이름을 입력하거나 다른 활동의 워크플로 변수나 속성에 바인딩할 수 있습니다. 선택적으로 실행할 특정 RuleSet의 버전 번호를 입력할 수 있습니다. 주 버전 및 부 버전 번호의 기본값 0을 유지하면 데이터베이스의 최신 버전 번호가 자동으로 활동에 제공됩니다.

## <a name="ruleset-service"></a>RuleSet 서비스

이 서비스는 데이터베이스에서 RuleSet 버전을 검색하고 호출 활동에 반환합니다. 앞에서 설명한 대로 `GetRuleSet` 호출에서 전달된 주 버전 및 부 버전 값이 둘 다 0이면 서비스에서는 최신 버전을 검색합니다. 이때 RuleSet 정의나 인스턴스의 캐시가 없으며 마찬가지로 RuleSet 버전을 "배포됨"으로 표시하여 진행 중인 RuleSet과 구분하는 기능도 없습니다.

서비스에서 액세스할 데이터베이스는 애플리케이션 구성 파일을 사용하여 호스트에서 구성해야 합니다.

#### <a name="to-run-the-tool"></a>도구를 실행하려면

1. 도구 및 서비스에서 사용하는 RuleSet 테이블을 설정하는 폴더에 Setup.sql 파일이 포함되어 있습니다. Setup.cmd 배치 파일을 실행하여 SQL Express에 규칙 데이터베이스를 만들고 RuleSet 테이블을 설정할 수 있습니다.

2. 배치 파일이나 Setup.sql을 편집하고 SQL Express를 사용하지 않거나 `Rules`가 아닌 다른 이름의 데이터베이스에 테이블을 배치하도록 지정할 경우 RuleSet 도구와 `UsageSample` 프로젝트의 애플리케이션 구성 파일을 같은 정보로 편집해야 합니다.

3. Setup.sql 스크립트를 실행한 후에는 `ExternalRuleSetToolkit` 솔루션을 빌드하고 ExternalRuleSetTool 프로젝트에서 RuleSet 도구를 시작할 수 있습니다.

4. `RuleSetToolkitUsageSample` 순차 워크플로 콘솔 애플리케이션에는 샘플 워크플로가 포함되어 있습니다. 워크플로는 대상 RuleSet이 실행되는 `PolicyFromService` 활동 및 두 가지 변수인 `orderValue`와 `discount`로 구성되어 있습니다.

5. 샘플을 사용하려면 `RuleSetToolkitUsageSample` 솔루션을 빌드합니다. 그런 다음 규칙 집합 도구 주 메뉴에서 **데이터-가져오기** 를 클릭 하 고 RuleSetToolkitUsageSample 폴더에 있는 DiscountRuleSet 파일을 가리킵니다. **규칙 저장소-저장** 메뉴 옵션을 클릭 하 여 가져온 규칙 집합을 데이터베이스에 저장 합니다.

6. `PolicyActivities` 어셈블리는 샘플 워크플로 프로젝트에서 참조되므로 `PolicyFromService` 활동이 워크플로에 나타납니다. 그러나 기본적으로 도구 상자에는 나타나지 않습니다. 도구 상자에 추가하려면 다음을 수행합니다.

    - 도구 상자를 마우스 오른쪽 단추로 클릭 하 고 **항목 선택** 을 선택 합니다 (시간이 오래 걸릴 수 있음).

    - **도구 상자 항목 선택** 대화 상자가 나타나면 **작업** 탭을 클릭 합니다.

    - `ExternalRuleSetToolkit` 솔루션에서 `PolicyActivities` 어셈블리로 이동 하 고 **열기**를 클릭 합니다.

    - **도구 상자 항목 선택** 대화 상자에서 `PolicyFromService` 작업이 선택 되어 있는지 확인 한 다음 **확인**을 클릭 합니다.

    - 이제 활동은 **RuleSetToolkitUsageSample Components** 범주의 도구 상자에 표시 됩니다.

7. RuleSet 서비스는 Program.cs에서 다음 문을 사용하여 콘솔 애플리케이션 호스트에 이미 구성되어 있습니다.

    ```csharp
    workflowRuntime.AddService(new RuleSetService());
    ```

8. 구성 파일을 사용하여 호스트에 서비스를 구성할 수도 있습니다. 자세한 내용은 SDK 설명서를 참조하세요.

9. 애플리케이션 구성 파일이 워크플로 프로젝트에 추가되어 서비스에서 사용할 데이터베이스에 대한 연결 문자열을 지정합니다. 이 문자열은 RuleSet 도구에서 사용하는 연결 문자열과 동일해야 합니다. RuleSet 도구에서 사용하는 연결 문자열은 RuleSet 테이블을 포함하는 데이터베이스를 가리킵니다.

10. 이제 다른 모든 워크플로 콘솔 애플리케이션처럼 `RuleSetToolkitUsageSample` 프로젝트를 실행할 수 있습니다. Visual Studio 내에서 F5 또는 Ctrl + F5 키를 누르거나 RuleSetToolkitUsageSample 파일을 직접 실행 합니다.

    > [!NOTE]
    > RuleSet 도구에서는 사용 샘플 어셈블리를 로드하므로 사용 샘플을 다시 컴파일하려면 도구를 닫아야 합니다.
