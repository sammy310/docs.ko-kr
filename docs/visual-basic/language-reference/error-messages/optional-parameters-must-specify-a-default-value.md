---
title: 선택적 매개 변수는 기본값을 지정해야 합니다.
ms.date: 07/20/2015
f1_keywords:
- vbc30812
- bc30812
helpviewer_keywords:
- BC30812
ms.assetid: 5091a250-be66-413b-98a3-2a9974c4d600
ms.openlocfilehash: 3718fe5c42c8af0948f3b5cb0d120c6876c6f98f
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162455"
---
# <a name="bc30812-optional-parameters-must-specify-a-default-value"></a><span data-ttu-id="27575-102">BC30812: 선택적 매개 변수는 기본값을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="27575-102">BC30812: Optional parameters must specify a default value</span></span>

<span data-ttu-id="27575-103">선택적 매개 변수는 호출 하는 프로시저에서 매개 변수를 제공 하지 않는 경우 사용할 수 있는 기본값을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="27575-103">Optional parameters must provide default values that can be used if no parameter is supplied by a calling procedure.</span></span>

<span data-ttu-id="27575-104">**오류 ID:** BC30812</span><span class="sxs-lookup"><span data-stu-id="27575-104">**Error ID:** BC30812</span></span>

## <a name="example"></a><span data-ttu-id="27575-105">예제</span><span class="sxs-lookup"><span data-stu-id="27575-105">Example</span></span>

<span data-ttu-id="27575-106">다음 예제에서는 BC30812를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="27575-106">The following example generates BC30812:</span></span>

```vb
Sub Proc1(x As Integer, Optional y As String)
    Console.WriteLine("Default argument is: " & y)
End Sub
```

## <a name="to-correct-this-error"></a><span data-ttu-id="27575-107">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="27575-107">To correct this error</span></span>

<span data-ttu-id="27575-108">선택적 매개 변수의 기본값 지정:</span><span class="sxs-lookup"><span data-stu-id="27575-108">Specify default values for optional parameters:</span></span>

```vb
Sub Proc1(x As Integer, Optional y As String = "Default Value")
    Console.WriteLine("Default argument is: " & y)
End Sub
```

## <a name="see-also"></a><span data-ttu-id="27575-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="27575-109">See also</span></span>

- [<span data-ttu-id="27575-110">선택 사항</span><span class="sxs-lookup"><span data-stu-id="27575-110">Optional</span></span>](../modifiers/optional.md)
