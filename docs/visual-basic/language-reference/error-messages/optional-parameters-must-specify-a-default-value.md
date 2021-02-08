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
# <a name="bc30812-optional-parameters-must-specify-a-default-value"></a><span data-ttu-id="df63d-103">BC30812: 선택적 매개 변수는 기본값을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="df63d-103">BC30812: Optional parameters must specify a default value</span></span>

<span data-ttu-id="df63d-104">선택적 매개 변수는 호출 하는 프로시저에서 매개 변수를 제공 하지 않는 경우 사용할 수 있는 기본값을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="df63d-104">Optional parameters must provide default values that can be used if no parameter is supplied by a calling procedure.</span></span>

<span data-ttu-id="df63d-105">**오류 ID:** BC30812</span><span class="sxs-lookup"><span data-stu-id="df63d-105">**Error ID:** BC30812</span></span>

## <a name="example"></a><span data-ttu-id="df63d-106">예제</span><span class="sxs-lookup"><span data-stu-id="df63d-106">Example</span></span>

<span data-ttu-id="df63d-107">다음 예제에서는 BC30812를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="df63d-107">The following example generates BC30812:</span></span>

```vb
Sub Proc1(x As Integer, Optional y As String)
    Console.WriteLine("Default argument is: " & y)
End Sub
```

## <a name="to-correct-this-error"></a><span data-ttu-id="df63d-108">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="df63d-108">To correct this error</span></span>

<span data-ttu-id="df63d-109">선택적 매개 변수의 기본값 지정:</span><span class="sxs-lookup"><span data-stu-id="df63d-109">Specify default values for optional parameters:</span></span>

```vb
Sub Proc1(x As Integer, Optional y As String = "Default Value")
    Console.WriteLine("Default argument is: " & y)
End Sub
```

## <a name="see-also"></a><span data-ttu-id="df63d-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="df63d-110">See also</span></span>

- [<span data-ttu-id="df63d-111">선택 사항</span><span class="sxs-lookup"><span data-stu-id="df63d-111">Optional</span></span>](../modifiers/optional.md)
