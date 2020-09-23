---
title: Value Types and Reference Types
ms.date: 07/20/2015
helpviewer_keywords:
- reference data types [Visual Basic]
- reference types [Visual Basic]
- value types [Visual Basic]
- value data types [Visual Basic]
- types [Visual Basic]
- data types [Visual Basic], value types
- data types [Visual Basic], reference types
ms.assetid: fc82ce15-5a40-4c5c-a1e1-a556830e7391
ms.openlocfilehash: 72cb1455300e1ff00d9d558aa5a9df95f32aa7b0
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91090120"
---
# <a name="value-types-and-reference-types"></a>Value Types and Reference Types

Visual Basic에는 참조 형식 및 값 형식 이라는 두 가지 종류의 형식이 있습니다. 참조 형식의 변수에는 데이터(개체)에 대한 참조가 저장되며, 값 형식의 변수에는 해당 데이터가 직접 포함됩니다. 참조 형식에서는 두 가지 변수가 같은 개체를 참조할 수 있으므로 한 변수에 대한 작업이 다른 변수에서 참조하는 개체에 영향을 미칠 수 있습니다. 값 형식에서는 각 변수에 데이터의 자체 복사본이 있으며 한 변수의 작업이 다른 변수에 영향을 줄 수 없습니다 ( [매개 변수에 대 한 ByRef 한정자](../../../language-reference/modifiers/byref.md)의 경우 제외).
  
## <a name="value-types"></a>값 형식  

 데이터 형식은 자체 메모리 할당 내에 데이터를 저장 하는 경우 *값 형식* 입니다. 값 형식에는 다음이 포함 됩니다.  
  
- 모든 숫자 데이터 형식  
  
- `Boolean`, `Char`, `Date`  
  
- 멤버가 참조 형식인 경우에도 모든 구조체  
  
- 열거형의 기본 형식은 항상,,,,,, `SByte` `Short` `Integer` `Long` `Byte` `UShort` `UInteger` 또는 이기 때문입니다. `ULong`  
  
 참조 형식 멤버가 포함 된 경우에도 모든 구조체는 값 형식입니다. 이러한 이유로 및와 같은 값 형식은 `Char` `Integer` .NET Framework 구조에 의해 구현 됩니다.  
  
 예약 된 키워드 (예:)를 사용 하 여 값 형식을 선언할 수 있습니다 `Decimal` . 키워드를 사용 하 여 `New` 값 형식을 초기화할 수도 있습니다. 이는 형식에 매개 변수를 사용 하는 생성자가 있는 경우 특히 유용 합니다. 이에 대 한 예는 <xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29> 제공 된 파트에서 새 값을 작성 하는 생성자입니다 `Decimal` .  
  
## <a name="reference-types"></a>참조 형식  

 *참조 형식은* 해당 데이터에 대 한 참조를 저장 합니다. 참조 형식에는 다음이 포함 됩니다.  
  
- `String`  
  
- 모든 배열 (해당 요소가 값 형식인 경우에도)  
  
- 클래스 형식 (예:) <xref:System.Windows.Forms.Form>  
  
- 대리자  
  
 클래스는 *참조 형식*입니다. 모든 배열은 멤버가 값 형식인 경우에도 참조 형식입니다.  
  
 모든 참조 형식은 기본 .NET Framework 클래스를 나타내므로 초기화할 때 [New Operator](../../../language-reference/operators/new-operator.md) 키워드를 사용 해야 합니다. 다음 문은 배열을 초기화 합니다.  
  
```vb  
Dim totals() As Single = New Single(8) {}  
```  
  
## <a name="elements-that-are-not-types"></a>형식이 아닌 요소  

 다음 프로그래밍 요소는 선언 된 요소에 대 한 데이터 형식으로 지정할 수 없으므로 형식으로 한정 되지 않습니다.  
  
- 네임스페이스  
  
- 모듈  
  
- 이벤트  
  
- 속성 및 프로시저  
  
- 변수, 상수 및 필드  
  
## <a name="working-with-the-object-data-type"></a>Object 데이터 형식 작업  

 참조 형식 또는 값 형식을 데이터 형식의 변수에 할당할 수 있습니다 `Object` . `Object`변수는 항상 데이터에 대 한 참조를 보유 하며 데이터 자체는 그렇지 않습니다. 그러나 변수에 값 형식을 할당 하는 경우이 값은 자체 데이터를 보유 하는 것 `Object` 처럼 동작 합니다. 자세한 내용은 [Object Data Type](../../../language-reference/data-types/object-data-type.md)을 참조 하세요.  
  
 `Object`변수를 <xref:Microsoft.VisualBasic.Information.IsReference%2A> <xref:Microsoft.VisualBasic.Information> 네임 스페이스 클래스의 메서드에 전달 하 여 변수를 참조 형식 또는 값 형식으로 사용할지 여부를 확인할 수 있습니다 <xref:Microsoft.VisualBasic?displayProperty=nameWithType> . <xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=nameWithType>`True` `Object` 변수의 내용이 참조 형식을 나타내면를 반환 합니다.  
  
## <a name="see-also"></a>참조

- [Nullable 값 형식](nullable-value-types.md)
- [Visual Basic의 형식 변환](type-conversions.md)
- [Structure 문](../../../language-reference/statements/structure-statement.md)
- [데이터 형식의 효율적 사용](efficient-use-of-data-types.md)
- [Object Data Type](../../../language-reference/data-types/object-data-type.md)
- [데이터 형식](index.md)
