---
title: 이 인수에서 형식 매개 변수의 데이터 형식을 유추할 수 없습니다.
description: BC36647 및 BC36644에 대 한 자세한 정보:이 인수에서 형식 매개 변수의 데이터 형식을 유추할 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- bc36644
- bc36647
- vbc36647
- vbc36644
helpviewer_keywords:
- BC36644
- BC36647
ms.assetid: 0e0050f2-2039-4311-b260-f0ebfde84189
ms.openlocfilehash: 26b4358dc2059aaff0a6a72d1489216c854f79a6
ms.sourcegitcommit: 1dbe25ff484a02025d5c34146e517c236f7161fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "104653675"
---
# <a name="bc36647-and-bc36644-data-types-of-the-type-parameters-cannot-be-inferred-from-these-arguments"></a>BC36647 및 BC36644:이 인수에서 형식 매개 변수의 데이터 형식을 유추할 수 없습니다.

이 인수에서 형식 매개 변수의 데이터 형식을 유추할 수 없습니다. 데이터 형식을 명시적으로 지정하면 이 오류를 해결할 수 있습니다.

이 오류는 오버로드 확인에 실패한 경우에 발생합니다. 특정 오버로드 후보가 제거된 이유를 나타내는 하위 메시지로 발생합니다. 오류 메시지는 컴파일러에서 형식 유추를 사용 하 여 형식 매개 변수에 대 한 데이터 형식을 찾을 수 없음을 설명 합니다.

> [!NOTE]
> 인수 지정이 옵션이 아닌 경우(예: 쿼리 식의 쿼리 연산자) 두 번째 문장 없이 오류 메시지가 나타납니다.

다음 코드에서는 오류를 보여 줍니다.

```vb
Module Module1

    Sub Main()

        '' Not Valid.
        'OverloadedGenericMethod("Hello", "World")

    End Sub

    Sub OverloadedGenericMethod(Of T)(ByVal x As String,
                                      ByVal y As InterfaceExample(Of T))
    End Sub

    Sub OverloadedGenericMethod(Of T, R)(ByVal x As T,
                                         ByVal y As InterfaceExample(Of R))
    End Sub

End Module

Interface InterfaceExample(Of T)
End Interface
```

**오류 ID:** BC36647 및 BC36644

## <a name="to-correct-this-error"></a>이 오류를 해결하려면

형식 유추를 사용하지 않고 형식 매개 변수에 대한 데이터 형식을 지정할 수 있습니다.

## <a name="see-also"></a>참고 항목

- [완화된 대리자 변환](../../programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
- [Visual Basic의 제네릭 프로시저](../../programming-guide/language-features/data-types/generic-procedures.md)
- [Visual Basic의 형식 변환](../../programming-guide/language-features/data-types/type-conversions.md)
