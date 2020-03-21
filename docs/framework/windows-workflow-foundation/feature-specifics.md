---
title: Windows Workflow Foundation 기능 특성
ms.date: 03/30/2017
ms.assetid: e84d12da-a055-45f6-b4d1-878d127b46b6
ms.openlocfilehash: 11bde5edea44f09ef1a5658cdf0e20ec1349c84b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182918"
---
# <a name="windows-workflow-foundation-feature-specifics"></a>Windows Workflow Foundation 기능 특성

.NET 프레임워크 4는 Windows 워크플로 우로 파운데이션에 여러 기능을 추가합니다. 이 문서에서는 여러 새로운 기능을 설명하고 이러한 기능이 유용할 수 있는 시나리오에 대한 세부 정보를 제공합니다.

## <a name="messaging-activities"></a>메시징 활동

메시징 활동<xref:System.ServiceModel.Activities.Receive>(, <xref:System.ServiceModel.Activities.Send> <xref:System.ServiceModel.Activities.ReceiveReply>" <xref:System.ServiceModel.Activities.SendReply>) 은 워크플로에서 WCF 메시지를 보내고 받는 데 사용됩니다. <xref:System.ServiceModel.Activities.Receive>및 <xref:System.ServiceModel.Activities.SendReply> 활동은 표준 WCF 웹 서비스와 마찬가지로 WSDL을 통해 노출되는 WCF(Windows 통신 재단) 서비스 작업을 형성하는 데 사용됩니다. <xref:System.ServiceModel.Activities.Send>WCF와 <xref:System.ServiceModel.Activities.ReceiveReply> <xref:System.ServiceModel.ChannelFactory>유사한 웹 서비스를 사용하는 데 사용됩니다. 사전 구성된 활동을 생성하는 워크플로 재단에 대해서도 **서비스 참조 추가** 환경이 있습니다.

### <a name="getting-started-with-messaging-activities"></a>메시징 작업 시작

- Visual Studio 2012에서 WCF 워크플로 우론 서비스 응용 프로그램 프로젝트를 만듭니다. <xref:System.ServiceModel.Activities.Receive> 및 <xref:System.ServiceModel.Activities.SendReply> 쌍이 캔버스에 배치됩니다.

- 프로젝트를 마우스 오른쪽 단추로 클릭하고 **서비스 참조 추가를**선택합니다. 기존 웹 서비스 WSDL을 가리키고 **확인을**클릭합니다. 프로젝트를 빌드하여 도구 상자에 생성된 <xref:System.ServiceModel.Activities.Send> 활동(및 <xref:System.ServiceModel.Activities.ReceiveReply>구현)을 표시합니다.

- [워크플로 서비스 문서](../wcf/feature-details/workflow-services.md)

### <a name="messaging-activities-example-scenario"></a>메시징 작업 예제 시나리오

서비스는 `BestPriceFinder` 특정 노선에 가장 적합한 항공권 가격을 찾기 위해 여러 항공사 서비스를 호출합니다. 이 시나리오를 구현하려면 메시지 활동을 사용하여 가격 요청을 받고, 백 엔드 서비스에서 가격을 검색하고, 최적의 가격으로 가격 요청에 회신해야 합니다. 또한 다른 즉시 사용 활동을 사용하여 최적의 가격을 계산하기 위한 비즈니스 논리를 만들어야 합니다.

## <a name="workflowservicehost"></a>WorkflowServiceHost

여러 <xref:System.ServiceModel.WorkflowServiceHost> 인스턴스, 구성 및 WCF 메시징을 지원하는 즉시 사용 가능 워크플로 호스트입니다(워크플로가 호스팅되기 위해 메시징을 사용할 필요는 없음). 서비스 동작의 집합을 통해 지속성, 추적 및 인스턴스 제어와 통합됩니다. WCF와 <xref:System.ServiceModel.ServiceHost>마찬가지로 콘솔/WinForms/WPF 응용 프로그램 또는 Windows 서비스에서 자체 호스팅되거나 IIS 또는 WAS에서 웹 호스팅(.xamlx 파일)으로 호스팅할 <xref:System.ServiceModel.WorkflowServiceHost> 수 있습니다.

### <a name="getting-started-with-workflow-service-host"></a>워크플로 서비스 호스트 시작

- Visual Studio 2010에서 WCF 워크플로 우호 서비스 응용 프로그램 <xref:System.ServiceModel.WorkflowServiceHost> 프로젝트를 만듭니다.

- 메시징이 아닌 워크플로를 호스트하려면 메시지를 기반으로 하는 인스턴스를 만들 사용자 지정 <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint>를 추가합니다.

- <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>에 <xref:System.ServiceModel.WorkflowServiceHost>를 추가한 다음 <xref:System.ServiceModel.Activities.WorkflowControlClient>를 사용하여 워크플로 인스턴스를 제어(예: 일시 중단 또는 종료)할 수 있습니다.

- <xref:System.ServiceModel.WorkflowServiceHost>에 대한 샘플은 다음 단원에서 확인할 수 있습니다.

  - [실행](./samples/execution.md)

  - 응용 프로그램: [일시 중단된 인스턴스 관리](./samples/suspended-instance-management.md)

- [호스팅 워크플로 서비스 개요](../wcf/feature-details/hosting-workflow-services-overview.md)

### <a name="workflowservicehost-scenario"></a>WorkflowServiceHost 시나리오

BestPriceFinder 서비스는 특정 노선에 가장 적합한 항공권 가격을 찾기 위해 여러 항공사 서비스를 호출합니다. 이 시나리오를 구현하려면 에서 워크플로를 호스트해야 합니다. <xref:System.ServiceModel.WorkflowServiceHost> 또한 메시지 활동을 사용하여 가격 요청을 받고, 백 엔드 서비스에서 가격을 검색하고, 최적의 가격으로 가격 요청에 회신합니다.

## <a name="correlation"></a>Correlation

상관 관계는 다음 두 가지 중 하나입니다.

- 메시지를 그룹화하는 방법(즉, 요청 메시지와 회신 간의 관계)

- 데이터를 서비스 인스턴스에 매핑하는 방법

### <a name="getting-started"></a>시작하기

- 상관 관계를 시작하려면 Visual Studio에서 새 프로젝트를 만듭니다. <xref:System.ServiceModel.Activities.CorrelationHandle> 형식의 변수를 만듭니다.

- 메시지를 그룹화하는 데 사용되는 상관 관계의 예로 메시지를 그룹화하는 요청-회신 상관 관계가 있습니다.

  - 활동에서 <xref:System.ServiceModel.Activities.Receive> <xref:System.ServiceModel.Activities.Receive.CorrelationInitializers%2A> 속성을 클릭하고 위의 첫 <xref:System.ServiceModel.Activities.RequestReplyCorrelationInitializer> 번째 단계에서 만든 CorrelationHandle을 사용하여 추가합니다.

  - "SendReply 만들기"를 마우스 <xref:System.ServiceModel.Activities.Receive> 오른쪽 단추로 클릭하고 클릭하여 <xref:System.ServiceModel.Activities.SendReply> 활동을 만듭니다. 워크플로에서 <xref:System.ServiceModel.Activities.Receive> 작업 뒤에 이 작업을 붙여 넣습니다.

- 데이터를 서비스 인스턴스에 매핑하는 예로 데이터(예: 주문 ID)를 특정 워크플로 인스턴스에 매핑하는 콘텐츠 기반 상관 관계가 있습니다.

  - 아무 메시징 작업에서나 `CorrelationInitializers` 속성을 클릭하고 위에서 만든 <xref:System.ServiceModel.Activities.QueryCorrelationInitializer> 변수를 사용하여 <xref:System.ServiceModel.Activities.CorrelationHandle>를 추가합니다. 드롭다운 메뉴에서 원하는 메시지 속성(예: OrderID)을 두 번 클릭합니다. `CorrelatesWith` 속성을 위에서 사용한 <xref:System.ServiceModel.Activities.CorrelationHandle> 변수로 설정합니다.

- [상관 관계 개념 설명서](../wcf/feature-details/correlation.md)

### <a name="correlation-scenario"></a>상관 관계 시나리오

주문 처리 워크플로는 새 주문 생성을 처리하고 진행 중인 기존 주문을 업데이트하는 데 사용됩니다. 이 시나리오를 구현하려면 워크플로를 <xref:System.ServiceModel.WorkflowServiceHost> 호스트하고 메시징 활동을 사용해야 합니다. 또한 올바른 워크플로에 `orderId` 대한 업데이트가 이루어지도록 하기 위해 에 기반한 상관 관계가 필요합니다.

## <a name="simplified-configuration"></a>단순화된 구성

WCF 구성 스키마는 복잡하며 사용자에게 찾기 어려운 많은 기능을 제공합니다. 에서 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]우리는 WCF 사용자가 다음과 같은 기능을 사용하여 서비스를 구성할 수 있도록 돕는 데 중점을 두었습니다.

- 서비스별 명시적 구성의 필요성을 제거합니다. \<서비스에 대한 서비스> 요소를 구성하지 않고 서비스가 프로그래밍 방식으로 어떤 끝점을 정의하지 않는 경우, 엔드포인트 세트는 서비스 기준 주소당 하나씩, 서비스에서 구현한 계약당 하나씩 서비스에 자동으로 추가됩니다.

- 사용자가 명시적 구성 없이 서비스에 적용될 WCF 바인딩 및 동작의 기본값을 정의할 수 있도록 합니다.

- 표준 엔드포인트는 하나 이상의 엔드포인트 속성(주소, 바인딩 및 계약)에 대한 고정 값이 있는 미리 구성된 다시 사용 가능 엔드포인트를 정의하며 사용자 지정 속성 정의를 허용합니다.

- 마지막으로 WCF 클라이언트 구성의 중앙 관리를 <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> 수행할 수 있으며, 응용 프로그램 도메인 로드 시간 후에 구성을 선택하거나 변경하는 시나리오에서 유용합니다.

### <a name="getting-started"></a>시작하기

- [WCF 4.0 개발자 가이드](https://docs.microsoft.com/previous-versions/dotnet/articles/ee354381(v=msdn.10))

- [구성 채널 팩터리](xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601)

- [표준 엔드포인트 요소](xref:System.ServiceModel.Configuration.StandardEndpointElement)

- [.NET 프레임워크 4의 서비스 구성 개선 사항](https://docs.microsoft.com/archive/blogs/endpoint/service-configuration-improvements-in-net-4)

- [.NET 4의 일반적인 사용자 오류: WF/WCF 서비스 구성 이름의 잘못된 입력](https://docs.microsoft.com/archive/blogs/endpoint/common-user-mistake-in-net-4-mistyping-the-wfwcf-service-configuration-name)

### <a name="simplified-configuration-scenarios"></a>단순화된 구성 시나리오

- 숙련된 ASMX 개발자가 WCF 사용을 시작하려고 합니다. 그러나 WCF는 너무 복잡해 보입니다! 구성 파일을 작성하는 데 필요한 모든 정보는 무엇입니까? .NET 4에서는 구성 파일을 전혀 사용하지 않을 수도 있습니다.

- 기존의 WCF 서비스 집합은 구성 및 유지 관리가 매우 어려웠습니다. 구성 파일에는 수천 줄의 XML 코드가 있으며 수정하는 것이 매우 위험합니다. 관리하기 쉽도록 코드 양을 줄이기 위한 도움이 필요합니다.

## <a name="data-contract-resolver"></a>데이터 계약 확인자

.NET 3.5의 알려진 형식 디자인에는 몇 가지 제한이 있었습니다.

- serialization 및 deserialization 중에 알려진 형식을 동적으로 추가할 수 없었습니다.

- 직렬 변환기에서 알 수 없는 xsi:type 정보를 처리할 수 없었습니다.

- 사용자가 회선의 serialization 인스턴스 크기를 더 작게 만들기 위해 회선에 표시할 xsi:type을 지정할 수 없었습니다.

[데이터 계약 해결프로그램은](../wcf/samples/datacontractresolver.md) .NET 4.5에서 이러한 문제를 해결합니다.

### <a name="getting-started"></a>시작하기

- [데이터 계약 확인자 API 설명서](xref:System.Runtime.Serialization.DataContractResolver)

- [데이터 계약 확인자 소개](https://docs.microsoft.com/archive/blogs/youssefm/configuring-known-types-dynamically-introducing-the-datacontractresolver)

- 샘플:

  - [DataContractResolver](../wcf/samples/datacontractresolver.md)

  - [KnownAssemblyAttribute](../wcf/samples/knownassemblyattribute.md)

### <a name="data-contract-resolver-scenarios"></a>데이터 계약 확인자 시나리오

- 서비스에서 수십 개의 <xref:System.Runtime.Serialization.KnownTypeAttribute> 개체를 선언할 필요가 없도록 합니다.

- XML blob의 크기를 줄입니다.

## <a name="flowchart"></a>순서도

순서도는 도메인 문제를 시각적으로 나타내는 잘 알려진 패러다임입니다. .NET 4에서 소개하는 새로운 컨트롤 플로우 스타일입니다. 순서도의 핵심 특성은 주어진 시간에 항상 작업 한 개만 실행된다는 것입니다. 순서도는 루프 및 대체 결과를 표현할 수 있지만 여러 노드의 동시 실행은 기본적으로 표현할 수 없습니다.

### <a name="getting-started"></a>시작하기

- Visual Studio 2012에서 워크플로 콘솔 응용 프로그램을 만듭니다. 워크플로 디자이너에서 순서도를 추가합니다.

- 순서도 기능은 다음 클래스를 사용합니다.

  - <xref:System.Activities.Statements.Flowchart>

  - <xref:System.Activities.Statements.FlowNode>

  - <xref:System.Activities.Statements.FlowDecision>

  - <xref:System.Activities.Statements.FlowStep>

  - <xref:System.Activities.Statements.FlowSwitch%601>

- 샘플:

  - [Flowchart 작업에서 TryCatch를 사용하여 오류 처리](./samples/fault-handling-in-a-flowchart-activity-using-trycatch.md)

  - [채용 프로세스](./samples/hiring-process.md)

- 디자이너 설명서:

  - [순서도 활동 디자이너](/visualstudio/workflow-designer/flowchart-activity-designers)

### <a name="flowchart-scenarios"></a>순서도 시나리오

순서도 작업을 사용하여 추측 게임을 구현할 수 있습니다. 추측 게임은 매우 단순합니다. 컴퓨터가 임의 숫자를 선택하고 플레이어가 해당 숫자를 추측해야 합니다. 플레이어가 각 추측을 제출할 때 컴퓨터는 힌트를 표시합니다(예: "더 낮은 숫자를 시도하십시오"). 플레이어가 7회 미만의 시도에서 숫자를 발견하면 컴퓨터에서 특별한 축하를 받습니다. 다음 절차 작업의 조합을 통해 이 게임을 구현할 수 있습니다.

- <xref:System.Activities.Statements.Sequence>

- <xref:System.Activities.Statements.While>

- <xref:System.Activities.Statements.Switch%601>

- <xref:System.Activities.Statements.TryCatch>

- <xref:System.Activities.Statements.Assign%601>

- <xref:System.Activities.Statements.If>

## <a name="procedural-activities-sequence-if-foreach-switch-assign-dowhile-while"></a>절차 작업(Sequence, If, ForEach, Switch, Assign, DoWhile, While)

절차 작업은 프로그래머에게 익숙한 개념을 사용하여 순차 제어 흐름을 모델링하는 메커니즘을 제공합니다. 이러한 활동을 사용하면 전통적으로 구조화된 프로그래밍 언어 구문이 가능하고 적절한 경우 C# 및 Visual Basic과 같은 일반적인 절차 언어와 언어 패리티를 제공합니다.

### <a name="getting-started"></a>시작하기

- Visual Studio 2012에서 워크플로 콘솔 응용 프로그램을 만듭니다. Workflow Designer에서 절차 작업을 추가합니다.

- 샘플:

  - [채용 프로세스](./samples/hiring-process.md)

  - [기업 구매 프로세스](./samples/corporate-purchase-process.md)

- 디자이너 설명서:

  - [Parallel 활동 디자이너](/visualstudio/workflow-designer/parallel-activity-designer)

  - [병렬ForEach\<t> 활동 디자이너](/visualstudio/workflow-designer/parallelforeach-t-activity-designer)

### <a name="procedural-activity-scenarios"></a>절차 작업 시나리오

- <xref:System.Activities.Statements.Parallel>: 인트라넷 문서 관리 시스템에 문서 승인 워크플로가 있습니다. 여러 부서의 사용자가 문서를 승인해야 인트라넷에 게시할 수 있습니다. 승인에 대한 정해진 순서가 없습니다. 문서가 "승인 보류 중" 단계에 있는 동안 언제든지 발생할 수 있습니다. 사용자가 검토를 위해 문서를 제출할 때 직접 관리자, 인트라넷 관리자 및 내부 통신 관리자의 승인을 받아야 합니다.

- <xref:System.Activities.Statements.ParallelForEach%601>: WF 애플리케이션이 대기업 내의 회사 구매를 관리합니다. 회사 규칙은 모든 구매 작업을 계획하기 전에 3개 공급업체를 평가하도록 규정합니다. 구매 부서의 직원이 회사의 공급업체 목록에서 세 개의 공급업체를 선택합니다. 공급업체를 선택하고 알린 후 회사는 합리적 제안서를 기다립니다. 제안서는 임의 순서로 도착할 수 있습니다. WF에서 이 시나리오를 구현하기 위해 공급업체 컬렉션을 반복하고 합리적 제안서를 요청하는 <xref:System.Activities.Statements.ParallelForEach%601>를 사용합니다. 모든 제안이 수집된 후 최상의 제안이 선택되고 표시됩니다.

## <a name="invokemethod"></a>InvokeMethod

<xref:System.Activities.Statements.InvokeMethod> 작업을 사용하면 범위 내의 개체나 형식에서 공용 메서드를 호출할 수 있습니다. 이 작업은 매개 변수(매개 변수 배열 포함)를 사용하거나 사용하지 않는 인스턴스 및 정적 메서드 호출과 제네릭 메서드 호출을 지원합니다. 동기 및 비동기로 메서드를 실행할 수도 있습니다.

### <a name="getting-started"></a>시작하기

- Visual Studio 2012에서 워크플로 콘솔 응용 프로그램을 만듭니다. 워크플로 디자이너에서 <xref:System.Activities.Statements.InvokeMethod> 작업을 추가하고 정적 및 인스턴스 메서드를 구성합니다.

- 디자이너 설명서: [호출 메서드 활동 디자이너](/visualstudio/workflow-designer/invokemethod-activity-designer)

### <a name="invokemethod-scenarios"></a>InvokeMethod 시나리오

- 범위 내의 개체에서 메서드를 호출해야 합니다. 예를 들어, 사전에 값을 추가해야 합니다. 사전 인스턴스의 Add 메서드가 호출되고 키와 값이 제공됩니다.

- 레거시 CLR 개체에서 메서드를 호출해야 합니다. 레거시 클래스 호출을 래핑할 사용자 지정 작업을 만드는 대신 워크플로 실행 중에 범위 내에 있는 경우 <xref:System.Activities.Statements.InvokeMethod>를 사용할 수 있습니다.

## <a name="error-handling-activities"></a>오류 처리 작업

이 <xref:System.Activities.Statements.TryCatch> 활동은 포함된 활동 집합을 실행하는 동안 발생하는 예외를 catch하는 메커니즘을 제공합니다(C# 및 Visual Basic의 Try/Catch 구문과 유사). <xref:System.Activities.Statements.TryCatch>는 워크플로 수준에서 예외 처리를 제공합니다. 처리되지 않은 예외가 throw되면 워크플로가 중단되고 Finally 블록이 실행되지 않습니다. 이 동작은 C#과 일치합니다.

### <a name="getting-started"></a>시작하기

- Visual Studio 2012에서 워크플로 콘솔 응용 프로그램을 만듭니다. Workflow Designer에서 <xref:System.Activities.Statements.TryCatch> 작업을 추가합니다.

- 샘플: [tryCatch를 사용한 순서도 활동의 오류 처리](./samples/fault-handling-in-a-flowchart-activity-using-trycatch.md)

- 디자이너 설명서: [오류 처리 활동 디자이너](/visualstudio/workflow-designer/error-handling-activity-designers)

### <a name="error-handling-scenarios"></a>오류 처리 시나리오

일련의 작업을 실행해야 하며, 오류가 발생할 경우 특정 논리를 실행해야 합니다. 오류 처리 논리 중에 오류를 복구할 수 없다는 것이 발견되면 예외가 다시 throw되고 부모 작업(또는 호스트)이 문제를 처리합니다.

## <a name="pick-activity"></a>Pick 작업

<xref:System.Activities.Statements.Pick> 작업은 WF에서 이벤트 기반 제어 흐름 모델링을 제공합니다. <xref:System.Activities.Statements.Pick>에는 각 분기가 실행되기 전에 특정 이벤트의 발생을 기다리는 많은 분기가 포함되어 있습니다. 이 설치에서 <xref:System.Activities.Statements.Pick>은 작업이 수신 대기 중인 이벤트 집합 중 하나만 실행하는 <xref:System.Activities.Statements.Switch%601>와 유사하게 동작합니다. 각 분기는 이벤트 구동 방식이며 처음 발생하는 이벤트는 해당 분기를 실행합니다. 다른 분기는 모두 이벤트 수신 대기를 취소하고 중지합니다.

### <a name="getting-started"></a>시작하기

- Visual Studio 2012에서 워크플로 콘솔 응용 프로그램을 만듭니다. Workflow Designer에서 <xref:System.Activities.Statements.Pick> 작업을 추가합니다.

- 샘플: [선택 활동 사용](./samples/using-the-pick-activity.md)

- 디자이너 문서: [활동 디자이너 선택](/visualstudio/workflow-designer/pick-activity-designer)

### <a name="pick-scenario"></a>Pick 시나리오

사용자에게 입력을 요청하는 메시지를 표시해야 합니다. 정상적인 상황에서 는 개발자는 사용자의 입력을 묻는 메시지를 표시 하기 위해 같은 <xref:System.Console.ReadLine%2A> 메서드 호출을 사용 합니다. 이 설치와 관련된 문제는 사용자가 입력할 때까지 프로그램이 기다린다는 것입니다. 이 시나리오에서는 차단 작업의 차단을 해제하기 위해 시간 제한이 필요합니다. 일반적인 시나리오에서는 지정된 기간 내에 작업을 완료해야 합니다. 차단 작업 시간 초과는 Pick에서 많은 값을 추가하는 시나리오입니다.

## <a name="wcf-routing-service"></a>WCF 라우팅 서비스

라우팅 서비스는 WCF 메시지가 클라이언트와 서비스 간에 흐르는 방식을 제어할 수 있는 일반 소프트웨어 라우터로 설계되었습니다. 라우팅 서비스를 사용하면 클라이언트를 서비스에서 분리할 수 있으므로 지원할 수 있는 구성과 서비스를 호스팅하는 방법을 고려할 때 유연성을 훨씬 더 자유롭게 사용할 수 있습니다. .NET 3.5에서는 클라이언트와 서비스가 긴밀하게 결합되었습니다. 클라이언트는 대화하는 데 필요한 모든 서비스와 위치 파악에 대해 알아야 했습니다. 또한 .NET Framework 3.5의 WCF에는 다음과 같은 제한 사항이 있습니다.

- 이 논리를 클라이언트 프로그램에 하드 코딩해야 했으므로 오류 처리가 복잡했습니다.

- 클라이언트와 서비스에서 항상 동일한 바인딩을 사용해야 했습니다.

- 서비스가 제대로 팩터링되지 않았습니다. 클라이언트가 여러 서비스 중에서 선택하는 대신 모든 기능을 구현하는 서비스 하나에 통신하도록 하는 것이 더 쉽습니다.

.NET 4의 라우팅 서비스는 이러한 문제를 보다 쉽게 해결할 수 있도록 설계되었습니다. 새 라우팅 서비스에는 다음과 같은 기능이 있습니다.

1. 콘텐츠 기반 라우팅(<xref:System.ServiceModel.Dispatcher.MessageFilter> 개체가 메시지를 검사하여 보낼 위치를 결정함)

2. 프로토콜 브리징(전송 & 메시지)

3. 오류 처리(라우터가 통신 예외를 catch하고 백업 엔드포인트로 장애 조치됨)

4. <xref:System.ServiceModel.Dispatcher.MessageFilterTable%601> 및 라우팅 구성의 동적(메모리 내) 업데이트

### <a name="getting-started"></a>시작하기

1. 설명서: [라우팅](../wcf/feature-details/routing.md)

2. 샘플: [WCF 샘플 &#91;라우팅 서비스&#93;](../wcf/samples/routing-services.md)

3. 블로그: [라우팅 규칙!](https://docs.microsoft.com/archive/blogs/RoutingRules/)

### <a name="routing-scenarios"></a>라우팅 시나리오

라우팅 서비스는 다음과 같은 시나리오에서 유용합니다.

- 클라이언트가 직접 주소를 모두 지정하지 않고 여러 서비스에 통신할 수 있습니다.

- 클라이언트가 클라이언트 요청에서 추가 논리를 수행하여 라우팅 위치를 결정할 수 있습니다.

- 클라이언트를 리팩터링하지 않고 클라이언트가 수행하는 작업을 여러 서비스 구현으로 분해합니다.

- 클라이언트와 서비스가 서로 다른 보안 설정으로 서로 다른 바인딩을 통신할 수 있습니다.

- 클라이언트가 서비스를 사용할 수 없는 경우나 오류에 대해 보다 강력하도록 설정할 수 있습니다.

## <a name="wcf-discovery"></a>WCF 검색

WCF Discovery는 응용 프로그램 인프라에 검색 메커니즘을 통합할 수 있는 프레임워크 기술입니다. 이 기술을 사용하여 서비스를 검색 가능하게 만들고 서비스를 검색하도록 클라이언트를 구성할 수 있습니다. 엔드포인트를 사용하여 클라이언트를 더 이상 하드 코딩할 필요가 없으므로 애플리케이션의 견고성과 내결함성이 강화됩니다. Discovery는 자동 구성 기능을 애플리케이션에 빌드하는 완벽한 플랫폼입니다.

이 제품은 WS-Discovery 표준을 기반으로 하며 상호 운용 가능하고 확장 가능하며 일반화되도록 설계되었습니다. 이 제품에서는 다음 두 가지 작업 모드가 지원됩니다.

1. 관리: 네트워크에 기존 서비스에 대해 알고 있는 엔터티가 있는 경우 클라이언트가 직접 정보를 쿼리합니다. 이것은 Active Directory와 유사합니다.

2. 임시: 클라이언트가 멀티캐스트 메시지를 사용하여 서비스를 찾습니다.

또한 검색 메시지는 네트워크 프로토콜에 관계없이 작동하므로 모드 요구 사항을 지원하는 모든 프로토콜에서 사용할 수 있습니다. 예를 들어 검색 멀티캐스트 메시지는 UDP 채널 또는 멀티캐스트 메시징을 지원하는 다른 네트워크를 통해 전송될 수 있습니다. 이러한 설계 포인트를 기능 유연성과 결합하여 검색을 솔루션에 맞게 조정할 수 있습니다.

### <a name="getting-started"></a>시작하기

- 문서: [WCF 검색](../wcf/feature-details/wcf-discovery.md)

- 샘플: [검색(샘플)](../wcf/samples/discovery-samples.md)

### <a name="discovery-scenarios"></a>Discovery 시나리오

서비스를 사용할 수 있게 될 시기를 알 수 없기 때문에 개발자가 엔드포인트를 하드 코딩하는 대신 런타임에 서비스를 선택하려고 합니다. 애플리케이션 구성 요소 간에 분리, 견고성 및 자동 구성이 더 필요합니다.

## <a name="tracking"></a>추적

워크플로 추적은 워크플로 인스턴스 실행에 대한 통찰력을 제공합니다. 추적 이벤트는 워크플로 인스턴스 수준에서 워크플로및 워크플로 내의 활동이 실행될 때 워크플로에서 내보전됩니다. 추적 레코드를 구독하려면 워크플로 추적 참가자를 워크플로 호스트에 추가해야 합니다. 추적 레코드는 추적 프로필을 사용하여 필터링됩니다. .NET 프레임워크는 ETW(Windows용 이벤트 추적) 추적 참가자를 제공하며 기본 프로필이 machine.config 파일에 설치됩니다.

### <a name="getting-started"></a>시작하기

1. Visual Studio 2010에서 WCF 워크플로 서비스 애플리케이션 프로젝트를 만듭니다. 먼저 <xref:System.ServiceModel.Activities.Receive> 및 <xref:System.ServiceModel.Activities.SendReply> 쌍이 캔버스에 배치됩니다.

2. web.config를 열고 프로필 없이 ETW 추적 동작을 추가합니다.

    1. 기본 프로필이 사용됩니다.

    2. 이벤트 뷰어를 열고 다음 노드에서 분석 채널을 활성화합니다: **이벤트 뷰어,** **응용 프로그램 및 서비스 로그,** **Microsoft,** **Windows,** **응용 프로그램 서버 응용 프로그램**. **분석** 클릭하고 **로그 사용 을**선택합니다.

    3. 워크플로 서비스를 실행합니다.

    4. 이벤트 뷰어에서 워크플로 추적 이벤트를 확인합니다.

3. 샘플: [추적](./samples/tracking.md)

4. 개념 문서: [워크플로 추적 및 추적](workflow-tracking-and-tracing.md)

## <a name="sql-workflow-instance-store"></a>SQL 워크플로 인스턴스 저장소

<xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>는 인스턴스 저장소의 SQL Server 기반 구현입니다. 인스턴스 저장소는 해당 인스턴스를 로드하고 다시 시작하는 데 필요한 모든 데이터와 함께 실행 중인 인스턴스의 상태를 저장합니다. 서비스 호스트는 워크플로가 유지되는 경우 인스턴스 상태를 저장하도록 인스턴스 저장소에 지시하고, 해당 인스턴스에 대한 메시지가 도착하거나 지연 작업이 만료되면 인스턴스 상태를 로드하도록 인스턴스 저장소에 지시합니다.

### <a name="getting-started"></a>시작하기

1. Visual Studio 2012에서 암시적 또는 명시적 <xref:System.Activities.Statements.Persist> 활동을 포함하는 워크플로를 만듭니다. 워크플로 서비스 호스트에 <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> 동작을 추가합니다. 이 작업은 코드나 애플리케이션 구성 파일에서 수행할 수 있습니다.

2. 샘플: [지속성](/previous-versions/dotnet/netframework-4.0/dd699769(v%3dvs.100))

3. 개념 설명서: [SQL 워크플로 인스턴스 저장소.](sql-workflow-instance-store.md)
