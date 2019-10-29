---
title: 선택적 매개 변수는 기본값을 지정해야 합니다.
ms.date: 07/20/2015
f1_keywords:
- vbc30812
- bc30812
helpviewer_keywords:
- BC30812
ms.assetid: 5091a250-be66-413b-98a3-2a9974c4d600
ms.openlocfilehash: eb782b2fa1fb73c7407b57a0942e5eebb30474ff
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040934"
---
# <a name="optional-parameters-must-specify-a-default-value"></a><span data-ttu-id="6f241-102">선택적 매개 변수는 기본값을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f241-102">Optional parameters must specify a default value</span></span>

<span data-ttu-id="6f241-103">선택적 매개 변수는 호출 하는 프로시저에서 매개 변수를 제공 하지 않는 경우 사용할 수 있는 기본값을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f241-103">Optional parameters must provide default values that can be used if no parameter is supplied by a calling procedure.</span></span>

<span data-ttu-id="6f241-104">**오류 ID:** BC30812</span><span class="sxs-lookup"><span data-stu-id="6f241-104">**Error ID:** BC30812</span></span>

## <a name="example"></a><span data-ttu-id="6f241-105">예제</span><span class="sxs-lookup"><span data-stu-id="6f241-105">Example</span></span>

<span data-ttu-id="6f241-106">다음 예제에서는 BC30812를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f241-106">The following example generates BC30812:</span></span>

```vb
Sub Proc1(x As Integer, Optional y As String)
    Console.WriteLine("Default argument is: " & y)
End Sub
```

## <a name="to-correct-this-error"></a><span data-ttu-id="6f241-107">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="6f241-107">To correct this error</span></span>

<span data-ttu-id="6f241-108">선택적 매개 변수의 기본값 지정:</span><span class="sxs-lookup"><span data-stu-id="6f241-108">Specify default values for optional parameters:</span></span>

```vb
Sub Proc1(x As Integer, Optional y As String = "Default Value")
    Console.WriteLine("Default argument is: " & y)
End Sub
```

## <a name="see-also"></a><span data-ttu-id="6f241-109">참조</span><span class="sxs-lookup"><span data-stu-id="6f241-109">See also</span></span>

- [<span data-ttu-id="6f241-110">Optional</span><span class="sxs-lookup"><span data-stu-id="6f241-110">Optional</span></span>](../modifiers/optional.md)
