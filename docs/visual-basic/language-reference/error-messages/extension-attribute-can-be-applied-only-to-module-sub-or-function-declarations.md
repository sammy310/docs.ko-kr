---
description: "자세한 내용은 다음에 대해 자세히 알아보세요. BC36550: ' Extension ' 특성은 ' Module ', ' Sub ' 또는 ' Function ' 선언에만 적용할 수 있습니다."
title: "'Extension' 특성은 'Module', 'Sub' 또는 'Function' 선언에만 적용할 수 있습니다."
ms.date: 07/20/2015
f1_keywords:
- bc36550
- vbc36550
helpviewer_keywords:
- BC36550
ms.assetid: 4387a51f-733c-45d7-abdb-eb64d4f51078
ms.openlocfilehash: f0c87de34238974229bc572a0f634a16e8cc78d9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796316"
---
# <a name="bc36550-extension-attribute-can-be-applied-only-to-module-sub-or-function-declarations"></a>BC36550: ' Extension ' 특성은 ' Module ', ' Sub ' 또는 ' Function ' 선언에만 적용할 수 있습니다.

Visual Basic에서 데이터 형식을 확장 하는 유일한 방법은 표준 모듈 내에 확장 메서드를 정의 하는 것입니다. 확장 메서드는 `Sub` 프로시저 또는 프로시저일 수 있습니다 `Function` . 모든 확장 메서드는 `<Extension()>` 네임 스페이스에서 확장 특성으로 표시 되어야 합니다 <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> . 필요에 따라 확장 메서드를 포함 하는 모듈을 동일한 방식으로 표시할 수 있습니다. 확장 특성은 사용할 수 없습니다.

**오류 ID:** BC36550

## <a name="to-correct-this-error"></a>이 오류를 해결하려면

- 확장 특성을 제거 합니다.

- 바깥쪽 모듈에 정의 된 메서드로 확장을 다시 디자인 합니다.

## <a name="example"></a>예제

다음 예제에서는 `Print` 데이터 형식에 대 한 메서드를 정의 합니다 `String` .

```vb
Imports StringUtility
Imports System.Runtime.CompilerServices
Namespace StringUtility
    <Extension()>
    Module StringExtensions
        <Extension()>
        Public Sub Print (ByVal str As String)
            Console.WriteLine(str)
        End Sub
    End Module
End Namespace
```

## <a name="see-also"></a>참고 항목

- [특성 개요](../../programming-guide/concepts/attributes/index.md)
- [확장명 메서드](../../programming-guide/language-features/procedures/extension-methods.md)
- [Module 문](../statements/module-statement.md)
