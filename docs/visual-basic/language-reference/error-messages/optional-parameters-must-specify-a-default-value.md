---
description: '자세히 알아보기: BC30812: 선택적 매개 변수는 기본값을 지정 해야 합니다.'
title: 선택적 매개 변수는 기본값을 지정해야 합니다.
ms.date: 07/20/2015
f1_keywords:
- vbc30812
- bc30812
helpviewer_keywords:
- BC30812
ms.assetid: 5091a250-be66-413b-98a3-2a9974c4d600
ms.openlocfilehash: 1cbed1c0f1297ecacdae94d9234d18a3d268f487
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795536"
---
# <a name="bc30812-optional-parameters-must-specify-a-default-value"></a>BC30812: 선택적 매개 변수는 기본값을 지정 해야 합니다.

선택적 매개 변수는 호출 하는 프로시저에서 매개 변수를 제공 하지 않는 경우 사용할 수 있는 기본값을 제공 해야 합니다.

**오류 ID:** BC30812

## <a name="example"></a>예제

다음 예제에서는 BC30812를 생성 합니다.

```vb
Sub Proc1(x As Integer, Optional y As String)
    Console.WriteLine("Default argument is: " & y)
End Sub
```

## <a name="to-correct-this-error"></a>이 오류를 해결하려면

선택적 매개 변수의 기본값 지정:

```vb
Sub Proc1(x As Integer, Optional y As String = "Default Value")
    Console.WriteLine("Default argument is: " & y)
End Sub
```

## <a name="see-also"></a>참고 항목

- [선택 사항](../modifiers/optional.md)
