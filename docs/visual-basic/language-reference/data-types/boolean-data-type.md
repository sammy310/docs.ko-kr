---
description: '자세한 정보: Boolean 데이터 형식 (Visual Basic)'
title: Boolean 데이터 형식
ms.date: 07/20/2015
f1_keywords:
- vb.FALSE
- vb.TRUE
- vb.Boolean
helpviewer_keywords:
- Boolean data type
- Boolean values [Visual Basic], False keyword
- False keyword [Visual Basic]
- True keyword [Visual Basic]
- Boolean values [Visual Basic], True keyword
ms.assetid: 4858e630-4813-4216-a55e-f4d0feb884e4
ms.openlocfilehash: cdda6bc0571eb0a2a9ee6a079ffd276bfc89a9b4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99731411"
---
# <a name="boolean-data-type-visual-basic"></a>Boolean 데이터 형식(Visual Basic)

또는 일 수 있는 값을 `True` 저장 `False` 합니다. 및 키워드 `True` 는 `False` 두 변수의 상태에 해당 합니다 `Boolean` .  
  
## <a name="remarks"></a>설명  

 [Boolean 데이터 형식 (Visual Basic)](boolean-data-type.md) 을 사용 하 여 true/false, 예/아니요 또는 설정/해제와 같은 두 가지 상태 값을 포함 합니다.  
  
 `Boolean` 의 기본값은 `False`입니다.  
  
 `Boolean` 값은 숫자로 저장 되지 않으며 저장 된 값은 숫자와 동일 하지 않습니다. 및에 대해 동일한 숫자 값을 사용 하는 코드를 작성 하면 안 됩니다 `True` `False` . 가능 하면 `Boolean` 변수의 사용을 디자인 된 논리 값으로 제한 해야 합니다.  
  
## <a name="type-conversions"></a>형식 변환  

 Visual Basic 숫자 데이터 형식 값을로 변환 하 `Boolean` 는 경우 0은이 되 `False` 고 다른 모든 값은가 됩니다 `True` . Visual Basic `Boolean` 에서 값을 숫자 형식으로 변환 하는 경우는 `False` 0이 되 고는 `True` -1이 됩니다.  
  
 `Boolean`값과 숫자 데이터 형식 간에 변환 하는 경우 .NET Framework 변환 메서드는 항상 Visual Basic 변환 키워드와 동일한 결과를 생성 하지 않는다는 점을 명심 해야 합니다. Visual Basic 변환은 이전 버전과 호환 되는 동작을 유지 하기 때문입니다. 자세한 내용은 [데이터 형식 문제 해결](../../programming-guide/language-features/data-types/troubleshooting-data-types.md)의 "부울 형식이 숫자 형식으로 정확 하 게 변환 되지 않습니다."를 참조 하세요.  
  
## <a name="programming-tips"></a>프로그래밍 팁  
  
- **음수.** `Boolean` 는 숫자 형식이 아니므로 음수 값을 나타낼 수 없습니다. 어떤 경우에는를 사용 하 여 `Boolean` 숫자 값을 포함 하면 안 됩니다.  
  
- **문자를 입력 합니다.** `Boolean` 에는 리터럴 형식 문자 또는 식별자 형식 문자가 없습니다.  
  
- **Framework 형식.** .NET Framework에서 해당하는 형식은 <xref:System.Boolean?displayProperty=nameWithType> 구조체입니다.  
  
## <a name="example"></a>예제  

 다음 예제에서 `runningVB` 는 `Boolean` 간단한 예/아니요 설정을 저장 하는 변수입니다.  
  
```vb  
Dim runningVB As Boolean  
' Check to see if program is running on Visual Basic engine.  
If scriptEngine = "VB" Then  
    runningVB = True  
End If  
```  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Boolean?displayProperty=nameWithType>
- [데이터 형식](index.md)
- [형식 변환 함수](../functions/type-conversion-functions.md)
- [변환 요약](../keywords/conversion-summary.md)
- [데이터 형식의 효율적 사용](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [데이터 형식 문제 해결](../../programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [CType Function](../functions/ctype-function.md)
