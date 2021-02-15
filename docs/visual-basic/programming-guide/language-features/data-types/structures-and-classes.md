---
description: '자세한 정보: 구조체 및 클래스 (Visual Basic)'
title: 구조체와 클래스
ms.date: 07/20/2015
helpviewer_keywords:
- classes [Visual Basic], vs. structures
- structures [Visual Basic]
- classes [Visual Basic]
- structures [Visual Basic], compared to classes
- structures [Visual Basic], structure variables
- structure variables [Visual Basic]
ms.assetid: a221e74a-ffcf-4bdc-a0f6-a088a9bf26cc
ms.openlocfilehash: 129948bd9a16309ffea5b1e4c690d8883c450b74
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100430627"
---
# <a name="structures-and-classes-visual-basic"></a>구조체와 클래스(Visual Basic)

Visual Basic는 구조체와 클래스에 대 한 구문을 통합 하며, 두 엔터티 모두 동일한 기능을 대부분 지원 합니다. 그러나 구조와 클래스 사이에는 중요 한 차이점도 있습니다.  
  
 클래스는 참조 형식이 될 수 있다는 장점이 있습니다. 참조를 전달 하는 것은 구조체 변수를 모든 데이터와 함께 전달 하는 것 보다 효율적입니다. 반면에 구조체는 전역 힙에서 메모리를 할당할 필요가 없습니다.  
  
 구조체에서 상속할 수 없으므로 구조체는 확장 하지 않아도 되는 개체에만 사용 해야 합니다. 만들려는 개체의 인스턴스 크기가 작은 경우 구조체를 사용 하 고 클래스와 구조체의 성능 특성을 고려해 야 합니다.  
  
## <a name="similarities"></a>비슷하며  

 구조체와 클래스는 다음과 같은 점에서 유사 합니다.  
  
- 둘 다 *컨테이너* 형식입니다. 즉, 다른 형식을 멤버로 포함 합니다.  
  
- 둘 다에는 생성자, 메서드, 속성, 필드, 상수, 열거형, 이벤트 및 이벤트 처리기를 포함할 수 있는 멤버가 있습니다. 그러나 이러한 멤버를 구조체의 선언 된 *요소* 와 혼동 해서는 안 됩니다.  
  
- 두 멤버 모두 개별화 된 액세스 수준을 가질 수 있습니다. 예를 들어 한 멤버를 선언 하 고 다른 멤버를 선언할 수 있습니다 `Public` `Private` .  
  
- 둘 다 인터페이스를 구현할 수 있습니다.  
  
- 둘 다 매개 변수를 포함 하거나 포함 하지 않는 공유 생성자를 가질 수 있습니다.  
  
- 속성에 하나 이상의 매개 변수가 사용 되는 경우 둘 다 *기본 속성* 을 노출할 수 있습니다.  
  
- 둘 다 이벤트를 선언 하 고 발생 시킬 수 있으며 둘 다 대리자를 선언할 수 있습니다.  
  
## <a name="differences"></a>차이점  

 구조체와 클래스는 다음 인스턴스와 관련 사항을 다릅니다.  
  
- 구조체는 *값 형식* 입니다. 클래스는 *참조 형식* 입니다. 구조체 형식의 변수에는 클래스 형식의 데이터에 대 한 참조를 포함 하는 대신 구조체의 데이터가 포함 됩니다.  
  
- 구조체는 스택 할당을 사용 합니다. 클래스는 힙 할당을 사용 합니다.  
  
- 모든 구조체 요소는 `Public` 기본적으로입니다. 클래스 변수와 상수는 기본적으로 이며 `Private` 다른 클래스 멤버는 `Public` 기본적으로입니다. 클래스 멤버에 대 한이 동작은 기본값 Visual Basic 6.0 시스템과의 호환성을 제공 합니다.  
  
- 구조체에는 하나 이상의 비공유 변수나 비공유 noncustom event 요소가 있어야 합니다. 클래스는 완전히 비어 있을 수 있습니다.  
  
- 구조체 요소는로 선언할 수 없습니다. `Protected` 클래스 멤버는 일 수 있습니다.  
  
- 구조 프로시저는 [공유](../../../language-reference/modifiers/shared.md) 프로시저인 경우에만 이벤트를 처리할 수 있으며, AddHandler 문을 통해서만 이벤트를 처리할 수 있습니다 `Sub` . 모든 클래스 프로시저는 [Handles](../../../language-reference/statements/handles-clause.md) 키워드 또는 문을 사용 하 여 이벤트를 처리할 수 있습니다 [](../../../language-reference/statements/addhandler-statement.md) `AddHandler` . 자세한 내용은 [이벤트](../events/index.md)를 참조하세요.  
  
- 구조체 변수 선언에서 배열의 초기값 또는 초기 크기를 지정할 수 없습니다. 클래스 변수 선언에는를 사용할 수 있습니다.  
  
- 구조체는 클래스에서 암시적으로 상속 <xref:System.ValueType?displayProperty=nameWithType> 되며 다른 형식에서 상속할 수 없습니다. 클래스는 이외의 클래스 또는 클래스에서 상속할 수 있습니다 <xref:System.ValueType?displayProperty=nameWithType> .  
  
- 구조체는 상속할 수 없습니다. 클래스는입니다.  
  
- 구조체는 절대 끝나지 않으므로 CLR (공용 언어 런타임)은 모든 구조에서 메서드를 호출 하지 않습니다. <xref:System.Object.Finalize%2A> 클래스는 GC (가비지 수집기)에 의해 종료 됩니다 .이는 <xref:System.Object.Finalize%2A> 남아 있는 활성 참조가 없는 경우 클래스에서를 호출 합니다.  
  
- 구조체에는 생성자가 필요 하지 않습니다. 클래스는입니다.  
  
- 구조체는 매개 변수를 사용 하는 경우에만 비공유 생성자를 포함할 수 있습니다. 클래스는 매개 변수를 포함 하거나 포함 하지 않을 수 있습니다.  
  
 모든 구조체에는 매개 변수가 없는 암시적 public 생성자가 있습니다. 이 생성자는 모든 구조체의 데이터 요소를 기본값으로 초기화 합니다. 이 동작은 다시 정의할 수 없습니다.  
  
## <a name="instances-and-variables"></a>인스턴스 및 변수  

 구조체는 값 형식 이므로 각 구조체 변수는 개별 구조체 인스턴스에 영구적으로 바인딩됩니다. 그러나 클래스는 참조 형식이 며 개체 변수는 다양 한 시간에 다양 한 클래스 인스턴스를 참조할 수 있습니다. 이러한 차이는 다음과 같은 방법으로 구조 및 클래스 사용에 영향을 줍니다.  
  
- **초기.** 구조체 변수에는 구조체의 매개 변수가 없는 생성자를 사용 하 여 요소를 초기화 하는 작업이 암시적으로 포함 됩니다. 따라서 `Dim s As struct1` 는와 동일 `Dim s As struct1 = New struct1()` 합니다.  
  
- **변수 할당.** 구조체 변수 하나를 다른 구조체 변수에 할당 하거나 구조 인스턴스를 프로시저 인수에 전달 하는 경우 모든 변수 요소의 현재 값이 새 구조체로 복사 됩니다. 한 개체 변수를 다른 변수에 할당 하거나 개체 변수를 프로시저에 전달 하면 참조 포인터만 복사 됩니다.  
  
- **아무 것도 할당 하지 않습니다.** 구조체 변수에 [Nothing](../../../language-reference/nothing.md) 값을 할당할 수 있지만 인스턴스는 변수와 계속 연결 됩니다. 변수 요소는 할당에 의해 다시 초기화 되지만 여전히 해당 메서드를 호출 하 고 해당 데이터 요소에 액세스할 수 있습니다.  
  
     반면, 개체 변수를로 설정 하는 경우 `Nothing` 클래스 인스턴스로부터 분리 하 고 다른 인스턴스를 할당할 때까지 변수를 통해 멤버에 액세스할 수 없습니다.  
  
- **여러 인스턴스.** 개체 변수에는 서로 다른 클래스 인스턴스가 할당 될 수 있으며, 여러 개체 변수가 동시에 동일한 클래스 인스턴스를 참조할 수 있습니다. 클래스 멤버의 값에 대 한 변경 내용은 동일한 인스턴스를 가리키는 다른 변수를 통해 액세스할 때 해당 멤버에 영향을 줍니다.  
  
     그러나 구조체 요소는 자체 인스턴스 내에서 격리 됩니다. 해당 값에 대 한 변경 내용은 다른 구조체 변수에는 적용 되지 않습니다. 동일한 선언의 다른 인스턴스에서도 마찬가지 `Structure` 입니다.  
  
- **연산.** 두 구조체의 같음 테스트는 요소 및 요소 테스트를 사용 하 여 수행 해야 합니다. 메서드를 사용 하 여 두 개체 변수를 비교할 수 있습니다 <xref:System.Object.Equals%2A> . <xref:System.Object.Equals%2A> 두 변수가 동일한 인스턴스를 가리키도록 할지 여부를 나타냅니다.  
  
## <a name="see-also"></a>추가 정보

- [데이터 형식](index.md)
- [복합 데이터 형식](composite-data-types.md)
- [Value Types and Reference Types](value-types-and-reference-types.md)
- [구조체](structures.md)
- [데이터 형식 문제 해결](troubleshooting-data-types.md)
- [구조체 및 기타 프로그래밍 요소](structures-and-other-programming-elements.md)
- [개체 및 클래스](../objects-and-classes/index.md)
