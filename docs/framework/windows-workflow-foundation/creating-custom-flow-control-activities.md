---
title: 사용자 지정 흐름 제어 작업 만들기
ms.date: 03/30/2017
ms.assetid: 27f409f6-2d1d-4cfb-9765-93eb2ad667d5
ms.openlocfilehash: 2be47281335066def5c1d267cd709db5a8ff1187
ms.sourcegitcommit: 69bf8b719d4c289eec7b45336d0b933dd7927841
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57847013"
---
# <a name="creating-custom-flow-control-activities"></a>사용자 지정 흐름 제어 작업 만들기
다양 한 프로그래밍 구조를 추상화 하는 비슷하게 작동 하는 흐름 제어 활동을 포함 하는.NET Framework (같은 <xref:System.Activities.Statements.Flowchart>) 또는 표준 프로그래밍 문 (같은 <xref:System.Activities.Statements.If>). 이 항목에서는 샘플 프로젝트 중 하나의 아키텍처를 설명 [제네릭이 아닌 ForEach](./samples/non-generic-foreach.md)합니다.  
  
## <a name="creating-the-custom-class"></a>사용자 지정 클래스 만들기  
 비제네릭 ForEach 클래스는 자식 작업을 예약해야 하고 <xref:System.Activities.NativeActivity>에서 파생되는 작업에는 이 기능이 없기 때문에 <xref:System.Workflow.Activities.CodeActivity>에서 파생되어야 합니다.  
  
```  
public sealed class ForEach : NativeActivity  
    {  
```  
  
 사용자 지정 클래스에서 작업에 사용되는 데이터를 저장하고 작업의 자식 작업을 실행하는 기능을 제공하려면 여러 멤버가 필요합니다. 여기에는 다음과 같은 멤버가 포함됩니다.  
  
-   `valueEnumerator`: Public이 아닌 <xref:System.Activities.Variable%601> 형식의 <xref:System.Collections.IEnumerator> 항목의 컬렉션을 반복 하는 데 사용 합니다. 이 멤버는 작업에서 내부적으로 사용되기 때문에 이 개체의 원본이 작업 외부에 있는 경우에 사용되는 인수나 공용 속성 대신 <xref:System.Activities.Variable%601> 형식입니다.  
  
-   `OnChildComplete`: 공용 <xref:System.Activities.CompletionCallback> 실행을 완료 하는 각 자식 때 실행 되는 속성입니다. 이 멤버는 작업의 각 인스턴스에 대해 값이 변경되지 않으므로 CLR 속성으로 정의됩니다.  
  
-   `Values`: 자식 활동의 반복에 사용 된 입력의 컬렉션입니다. 이 멤버는 데이터 원본이 작업 외부에 있지만 작업이 실행되는 동안 컬렉션 콘텐츠가 변경되지 않아야 하므로 <xref:System.Activities.InArgument%601> 형식입니다. 작업이 실행되는 동안 이 컬렉션의 콘텐츠를 변경하는 기능(예: 작업 추가 또는 제거)이 작업에 필요한 경우 이 멤버는 <xref:System.Activities.ActivityAction>으로 정의된 다음 액세스할 때마다 평가되므로 작업에서 변경 내용을 사용할 수 있습니다.  
  
-   `Body`: 각 항목에 대해 실행할 활동을 정의 하는이 멤버는 `Values` 컬렉션입니다. 이 멤버는 액세스할 때마다 평가되도록 <xref:System.Activities.ActivityAction>으로 정의됩니다.  
  
-   `Execute`: 이 메서드를 사용 합니다 `InternalExecute`, `OnForEachComplete`, 및 `GetStateAndExecute` 실행을 예약 하 고 본문 멤버에 정의 된 자식 활동의 완료 처리기를 할당 하려면 public이 아닌 멤버입니다.  
  
-   `CacheMetadata`: 이 멤버는 작업을 실행 하는 데 필요한 정보를 런타임에 제공 합니다. 기본적으로 작업의 `CacheMetadata` 메서드가 작업의 모든 공용 멤버를 런타임에 알리지만, 이 작업은 일부 기능에 전용 멤버를 사용하기 때문에 런타임에서 인식할 수 있도록 전용 멤버의 존재를 런타임에 알려야 합니다. 이 경우 전용 `CacheMetadata` 멤버에 액세스할 수 있도록 `valueEnumerator` 함수가 재정의됩니다. 또한 이 멤버는 실행되는 동안 작업에 전달될 수 있도록 작업 값에 대한 인수를 만듭니다.
