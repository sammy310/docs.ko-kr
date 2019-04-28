---
title: 개체 데이터 형식 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Object
- vb.Variant
helpviewer_keywords:
- object variables [Visual Basic], Object type
- data types [Visual Basic], assigning
- Object data type
- Object data type [Visual Basic], reference
ms.assetid: 61ea4a7c-3b3d-48d4-adc4-eacfa91779b2
ms.openlocfilehash: 616110145db2796e05509094b1c023daacd68f03
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61751678"
---
# <a name="object-data-type"></a>Object Data Type
개체를 참조 하는 주소를 저장 합니다. 참조 형식 (문자열, 배열, 클래스 또는 인터페이스)를 할당할 수 있습니다는 `Object` 변수입니다. `Object` 변수 값 형식의 데이터도 참조할 수 있습니다 (숫자 `Boolean`를 `Char`, `Date`, 구조체 또는 열거형)입니다.  
  
## <a name="remarks"></a>설명  
 `Object` 데이터 형식은 응용 프로그램에서 인식 하는 모든 개체 인스턴스를 포함 하 여 모든 데이터 형식의 데이터를 가리킬 수 있습니다. 사용 하 여 `Object` 컴파일 타임에 모르는 경우 어떤 데이터 형식 변수 가리킬 수 있습니다.  
  
 기본값인 `Object` 는 `Nothing` (null 참조).  
  
## <a name="data-types"></a>데이터 형식  
 변수, 상수 또는 모든 데이터 형식의 식을 할당할 수는 `Object` 변수입니다. 데이터 형식을 확인 하는 `Object` 참조 현재 변수를 사용할 수 있습니다 합니다 <xref:System.Type.GetTypeCode%2A> 메서드의 <xref:System.Type?displayProperty=nameWithType> 클래스. 다음은 이에 대한 예입니다.  
  
```  
Dim myObject As Object  
' Suppose myObject has now had something assigned to it.  
Dim datTyp As Integer  
datTyp = Type.GetTypeCode(myObject.GetType())  
```  
  
 `Object` 데이터 형식은 참조 형식입니다. 그러나 Visual Basic 처리는 `Object` 값 형식의 데이터를 참조할 때 값 형식으로 변수입니다.  
  
## <a name="storage"></a>스토리지  
 참조 하는 데이터 형식에 관계 없이 `Object` 자체 이지만 값에 대 한 포인터 대신 변수 데이터 값이 포함 되지 않습니다. 항상 컴퓨터 메모리에 4 바이트를 사용 하지만이 변수의 값을 나타내는 데이터 저장소를 다루지 않습니다. 데이터를 찾는 데 포인터를 사용 하는 코드로 인해 `Object` 값 형식을 있는 변수는 형식화 된 변수 보다 명시적으로 액세스 하려면 다소 느립니다.  
  
## <a name="programming-tips"></a>프로그래밍 팁  
  
- **Interop 고려 사항입니다.** 예제에서는 자동화 개체나 COM 개체에 대 한.NET Framework 용으로 작성 되지 구성 요소와 상호 작용 하는 경우 염두에 포인터 형식이 다른 환경에서 Visual Basic을 사용 하 여 호환 되지 않음을 `Object` 형식입니다.  
  
- **성능.** 사용 하 여 선언 된 변수는 `Object` 형식은 모든 개체에 대 한 참조를 포함할 만큼 충분히 유연 합니다. 그러나 메서드 또는 속성에 이러한 변수를 호출 하면 항상 발생 *런타임에 바인딩* (런타임에). 강제로 *초기 바인딩* 컴파일 시간 및 성능 향상, 특정 클래스 이름 사용 하 여 변수를 선언 하거나 특정 데이터 형식으로 캐스팅 합니다.  
  
     개체 변수를 선언 하면 예를 들어 특정 클래스 형식을 사용 하려고 <xref:System.OperatingSystem>를 일반화 하는 대신 `Object` 형식입니다. 와 같은 사용 가능한 가장 구체적인 클래스도 사용 해야 <xref:System.Windows.Forms.TextBox> 대신 <xref:System.Windows.Forms.Control>속성 및 메서드에 액세스할 수 있도록 합니다. 일반적으로 사용할 수 있습니다 합니다 **클래스** 목록에 **개체 브라우저** 사용할 수 있는 클래스 이름을 찾을 수 있습니다.  
  
- **확대 합니다.** 모든 데이터 형식 및 모든 참조 형식으로 확장 된 `Object` 데이터 형식입니다. 즉, 모든 형식을 변환할 수 있습니다 `Object` 발생 없이 <xref:System.OverflowException?displayProperty=nameWithType> 오류입니다.  
  
     그러나 값 형식 간에 변환 하는 경우 및 `Object`, 작업을 수행 하는 Visual Basic *boxing* 하 고 *unboxing*, 실행 속도가 느린를 활용 하는 합니다.  
  
- **형식 문자입니다.** `Object` 에 리터럴 형식 문자 또는 식별자 형식 문자가 없습니다.  
  
- **Framework 형식입니다.** .NET Framework의 해당 형식은 <xref:System.Object?displayProperty=nameWithType> 클래스입니다.  
  
## <a name="example"></a>예제  
 다음 예제는 `Object` 개체 인스턴스를 가리키는 변수입니다.  
  
```  
Dim objDb As Object  
Dim myCollection As New Collection()  
' Suppose myCollection has now been populated.  
objDb = myCollection.Item(1)  
```  
  
## <a name="see-also"></a>참고자료

- <xref:System.Object>
- [데이터 형식](../../../visual-basic/language-reference/data-types/index.md)
- [형식 변환 함수](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [변환 요약](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [데이터 형식의 효율적 사용](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [방법: 두 개체가 관련이 있는지 여부를 결정 합니다.](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)
- [방법: 두 개체가 동일한 지 여부를 결정 합니다.](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
