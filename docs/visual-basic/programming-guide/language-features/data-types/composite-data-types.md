---
title: 복합 데이터 형식
ms.date: 04/25/2017
helpviewer_keywords:
- classes [Visual Basic], composite data types
- composite types [Visual Basic]
- composite data types [Visual Basic]
- data types [Visual Basic], composite
- arrays [Visual Basic], composite data types
- structures [Visual Basic], composite data types
- classes [Visual Basic], composite types
- types [Visual Basic], composite
ms.assetid: 62970f2e-52c0-4369-8963-613820f1f434
ms.openlocfilehash: 842b74aa7cc99c8196fdfb1eb6c976d9e72a4fa4
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91077165"
---
# <a name="composite-data-types-visual-basic"></a>복합 데이터 형식(Visual Basic)

기본 데이터 형식 Visual Basic 제공 하는 것 외에도 다양 한 형식의 항목을 조합 하 여 구조, 배열 및 클래스와 같은 *복합 데이터 형식을* 만들 수 있습니다. 기본 형식 및 다른 복합 형식에서 복합 데이터 형식을 빌드할 수 있습니다. 예를 들어 구조체 요소 배열 또는 배열 멤버가 포함 된 구조체를 정의할 수 있습니다.  
  
## <a name="data-types"></a>데이터 형식  

 복합 형식은 해당 구성 요소의 데이터 형식과 다릅니다. 예를 들어 `Integer` 요소 배열은 `Integer` 데이터 형식이 아닙니다.  
  
 배열 데이터 형식은 일반적으로 필요에 따라 요소 형식, 괄호 및 쉼표를 사용 하 여 표현 됩니다. 예를 들어, 요소의 1 차원 배열은 `String` 로 표시 되 `String()` 고 요소의 2 차원 배열은 `Boolean` 로 표시 됩니다 `Boolean(,)` .  
  
## <a name="structure-types"></a>구조체 형식  

 모든 구조를 구성 하는 단일 데이터 형식은 없습니다. 대신 두 구조체가 동일한 요소를 동일한 순서로 정의 하더라도 구조체의 각 정의는 고유한 데이터 형식을 나타냅니다. 그러나 동일한 구조에서 둘 이상의 인스턴스를 만들 경우 Visual Basic는 동일한 데이터 형식으로 간주 합니다.  
  
## <a name="tuples"></a>튜플

튜플은 미리 정의 된 형식이 있는 두 개 이상의 필드를 포함 하는 간단한 구조입니다. 튜플은 Visual Basic 2017부터 지원 됩니다. 튜플은 참조로 인수를 전달 하거나 더 많은 중량 클래스 또는 구조체에서 반환 된 필드를 패키지할 필요 없이 단일 메서드 호출에서 여러 값을 반환 하는 데 가장 일반적으로 사용 됩니다. 튜플에 대 한 자세한 내용은 [튜플](tuples.md) 항목을 참조 하세요.

## <a name="array-types"></a>배열 유형  

 모든 배열을 구성 하는 단일 데이터 형식은 없습니다. 배열의 특정 인스턴스에 대 한 데이터 형식은 다음에 의해 결정 됩니다.  
  
- 배열이 되는 사실입니다.  
  
- 배열의 순위 (차원의 수)입니다.  
  
- 배열의 요소 형식입니다.  
  
 특히 지정 된 차원의 길이는 인스턴스의 데이터 형식에 포함 되지 않습니다. 다음은 이에 대한 예입니다.  
  
```vb  
Dim arrayA( ) As Byte = New Byte(12) {}  
Dim arrayB( ) As Byte = New Byte(100) {}  
Dim arrayC( ) As Short = New Short(100) {}  
Dim arrayD( , ) As Short  
Dim arrayE( , ) As Short = New Short(4, 10) {}  
```  
  
 위의 예제에서 배열 변수 `arrayA` 및 `arrayB` 은 `Byte()` 다른 길이로 초기화 되더라도 동일한 데이터 형식으로 간주 됩니다. 변수와 `arrayB` `arrayC` 의 요소 형식이 다르기 때문에 동일한 형식이 아닙니다. 및 변수는 `arrayC` `arrayD` 순위가 다르기 때문에 동일한 형식이 아닙니다. `arrayD` `arrayE` `Short(,)` 가 아직 초기화 되지 않은 경우에도의 순위 및 요소 형식은 동일 하기 때문에 및 변수는 동일한 형식 `arrayD` 입니다.  
  
 배열에 대 한 자세한 내용은 [배열](../arrays/index.md)을 참조 하세요.  
  
## <a name="class-types"></a>클래스 형식  

 모든 클래스를 구성 하는 단일 데이터 형식은 없습니다. 한 클래스가 다른 클래스에서 상속 될 수 있지만 각 클래스는 별도의 데이터 형식입니다. 동일한 클래스의 여러 인스턴스는 동일한 데이터 형식입니다. 한 클래스 인스턴스 변수를 다른 클래스에 할당 하는 경우 데이터 형식이 같을 뿐만 아니라 메모리의 동일한 클래스 인스턴스를 가리킵니다.  
  
 클래스에 대 한 자세한 내용은 [개체 및 클래스](../objects-and-classes/index.md)를 참조 하세요.  
  
## <a name="see-also"></a>참조

- [데이터 형식](index.md)
- [기본 데이터 형식](elementary-data-types.md)
- [Visual Basic의 제네릭 형식](generic-types.md)
- [Value Types and Reference Types](value-types-and-reference-types.md)
- [Visual Basic의 형식 변환](type-conversions.md)
- [구조체](structures.md)
- [데이터 형식 문제 해결](troubleshooting-data-types.md)
- [방법: 변수에 두 개 이상의 값 사용](how-to-hold-more-than-one-value-in-a-variable.md)
