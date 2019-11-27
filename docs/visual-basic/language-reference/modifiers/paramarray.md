---
title: ParamArray
ms.date: 07/20/2015
f1_keywords:
- vb.ParamArray
- ParamArray
helpviewer_keywords:
- ParamArray keyword [Visual Basic]
- ParamArray keyword [Visual Basic], syntax
ms.assetid: a5f18789-92bd-488f-9c7e-cf3719963635
ms.openlocfilehash: fbc87bffebc265e6062512e96fc29a64334b3c65
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351368"
---
# <a name="paramarray-visual-basic"></a>ParamArray(Visual Basic)
프로시저 매개 변수가 지정 된 형식의 선택적 요소 배열을 사용 하도록 지정 합니다. `ParamArray`는 매개 변수 목록의 마지막 매개 변수 에서만 사용할 수 있습니다.  
  
## <a name="remarks"></a>주의  
 `ParamArray`를 사용 하 여 프로시저에 임의 개수의 인수를 전달할 수 있습니다. `ParamArray` 매개 변수는 항상 [ByVal](../../../visual-basic/language-reference/modifiers/byval.md)을 사용하여 선언됩니다.  
  
 적절 한 데이터 형식의 배열이 나 쉼표로 구분 된 값 목록을 전달 하거나 아무 것도 지정 하지 않으면 `ParamArray` 매개 변수에 하나 이상의 인수를 제공할 수 있습니다. 자세한 내용은 [매개 변수 배열의](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)"ParamArray 호출"을 참조 하십시오.  
  
> [!IMPORTANT]
> 무한정 클 수 있는 배열을 처리할 때마다 응용 프로그램의 내부 용량을 overrunning 위험이 있습니다. 호출 코드에서 매개 변수 배열을 허용 하는 경우 응용 프로그램에 비해 길이를 테스트 하 고, 응용 프로그램에 적합 한 단계를 수행 해야 합니다.  
  
 `ParamArray` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.  
  
 [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [Function 문](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Property 문](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Sub 문](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>참고 항목

- [키워드](../../../visual-basic/language-reference/keywords/index.md)
- [매개 변수 배열](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)
