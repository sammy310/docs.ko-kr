---
ms.openlocfilehash: d420be76645fc71ac922542fa49f799a473e9a83
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614851"
---
### <a name="accessibility-improvements-in-windows-workflow-foundation-wf-workflow-designer"></a>Windows WF(Workflow Foundation) 워크플로 디자이너의 접근성 개선 사항

#### <a name="details"></a>세부 정보

Windows WF(Workflow Foundation) 워크플로 디자이너는 접근성 기술 작동 방법을 개선합니다. 개선 사항에는 다음과 같은 변경 내용이 포함됩니다.

- 일부 컨트롤에서 왼쪽에서 오른쪽으로, 위쪽에서 아래쪽으로 탭 순서를 변경합니다.
- <xref:System.ServiceModel.Activities.InitializeCorrelation> 작업에 대한 상관 관계 데이터를 설정하는 초기화 상관 관계 창
- <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply> 및 <xref:System.ServiceModel.Activities.ReceiveReply> 작업에 대한 콘텐츠 정의 창
- 바로 가기를 통해 추가 함수가 지원됩니다.
- 작업의 속성을 편집할 때 처음으로 포커스된 경우 바로 가기에서 속성 그룹을 축소할 수 있습니다.
- 이제 경고 아이콘은 바로 가기에서 액세스할 수 있습니다.
- 바로 가기에서 속성 창의 추가 속성 단추에 액세스할 수 있습니다.
- 이제 바로 가기 사용자는 워크플로 디자이너의 인수 및 변수 창에 있는 헤더 항목에 액세스할 수 있습니다.
- 다음과 같은 경우 포커스가 있는 항목의 표시 유형 향상
- 워크플로 디자이너 및 작업 디자이너에서 사용하는 데이터 그리드에 행 추가
- <xref:System.ServiceModel.Activities.ReceiveReply> 및 <xref:System.ServiceModel.Activities.SendReply> 작업에서 필드 누름
- 변수 또는 인수에 대한 기본값 설정
- 이제 화면 읽기 프로그램이 다음 항목을 올바르게 인식합니다.
- 워크플로 디자이너에서 설정된 중단점
- <xref:System.Activities.Statements.FlowSwitch%601>, <xref:System.Activities.Statements.FlowDecision> 및 <xref:System.ServiceModel.Activities.CorrelationScope> 작업
- <xref:System.ServiceModel.Activities.Receive> 작업의 콘텐츠
- <xref:System.Activities.Statements.InvokeMethod> 작업의 대상 유형
- <xref:System.Activities.Statements.TryCatch> 작업의 예외 콤보 상자 및 마지막 섹션
- 메시지 유형 콤보 상자, 상관 관계 이니셜라이저 추가 창의 분할기, 콘텐츠 정의 창 및 메시징 작업의 CorrelatesOn 정의 창(<xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply> 및 <xref:System.ServiceModel.Activities.ReceiveReply>)
- 상태 컴퓨터 전환 및 전환 대상
- <xref:System.Activities.Statements.FlowDecision> 작업의 주석 및 커넥터
- 작업의 팝업(마우스 오른쪽 단추 클릭) 메뉴
- 속성 값 편집기, 검색 정리 단추, 범주별으로 및 사전순 정렬 단추 및 속성 그리드의 식 편집기 대화 상자
- 워크플로 디자이너의 확대/축소 백분율
- <xref:System.Activities.Statements.Parallel> 및 <xref:System.Activities.Statements.Pick> 작업의 구분 기호
- <xref:System.Activities.Statements.InvokeDelegate> 작업
- 사전 작업의 형식 선택 창(`Microsoft.Activities.AddToDictionary&lt;TKey,TValue>`, `Microsoft.Activities.RemoveFromDictionary&lt;TKey,TValue>`등)
- .NET 형식 찾아보기 및 선택 창
- 워크플로 디자이너의 이동 경로
- 고대비 테마를 선택한 사용자는 워크플로 디자이너의 표시 유형에서 여러 개선 사항 및 포커스 요소에 사용되는 요소와 더욱 분명한 선택 영역 상자 사이의 대조율과 같은 해당 컨트롤을 확인합니다.

#### <a name="suggestion"></a>제안 해결 방법

다시 호스트된 워크플로 디자이너에서 애플리케이션을 사용하는 경우 애플리케이션은 다음과 같은 작업 중 하나를 수행하여 이러한 변경 내용을 활요할 수 있습니다.

- .NET Framework 4.7.1을 대상으로 지정하도록 애플리케이션을 다시 컴파일합니다. 이러한 접근성 변경 내용은 기본적으로 활성화됩니다.
- 애플리케이션이 .NET Framework 4.7 이전을 대상으로 하지만 .NET Framework 4.7.1에서 실행되는 경우 다음 예제와 같이 다음 [AppContext 스위치](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)를 app.config 파일의 `<runtime>` 섹션에 추가하고 `false`로 설정하여 이러한 레거시 접근성 동작에서 옵트아웃할 수 있습니다.

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <startup>
    <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.7"/>
  </startup>
  <runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true/false;key2=true/false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false" />
  </runtime>
</configuration>
```

.NET Framework 4.7.1 이상을 대상으로 하고 레거시 액세스 가능성 동작을 유지하려는 애플리케이션은 이 AppContext 스위치를 `true`로 명확하게 설정하여 레거시 액세스 가능성 기능 사용을 옵트인할 수 있습니다.

| 이름    | 값       |
|:--------|:------------|
| Scope   | 부       |
| 버전 | 4.7.1       |
| 형식    | 대상 변경 |
