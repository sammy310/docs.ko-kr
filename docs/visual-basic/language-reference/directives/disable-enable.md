---
description: '다음에 대 한 자세한 정보: #Disable 및 #Enable 지시문 (Visual Basic)'
title: 지시문 사용 및 사용 안 함
ms.date: 01/28/2021
helpviewer_keywords:
- directives, enable
- directives, disable
- disable directive
ms.openlocfilehash: d600cc959639a3f70bca5678fbc81aae0806c9cc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797265"
---
# <a name="disable-and-enable-directives-visual-basic"></a><span data-ttu-id="314c7-103">#Disable 및 #Enable 지시문 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="314c7-103">#Disable and #Enable directives (Visual Basic)</span></span>

<span data-ttu-id="314c7-104">`#Disable`및 `#Enable` 지시문은 Visual Basic 소스 코드 컴파일러 지시문입니다.</span><span class="sxs-lookup"><span data-stu-id="314c7-104">The `#Disable` and `#Enable` directives are Visual Basic source code compiler directives.</span></span> <span data-ttu-id="314c7-105">이러한 코드는 코드 영역에 대 한 특정 경고를 사용 하지 않도록 설정 하 고 다시 활성화 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="314c7-105">They are used to disable and re-enable specific warnings for regions of code.</span></span>

```vb
' Suppress warning about no awaits in this method.
#Disable Warning BC42356
    Async Function TestAsync() As Task
        Console.WriteLine("testing")
    End Function
#Enable Warning BC42356
```

<span data-ttu-id="314c7-106">쉼표로 구분 된 경고 코드 목록을 사용 하지 않도록 설정 하 고 사용 하도록 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="314c7-106">You can also disable and enable a comma-separated list of warning codes.</span></span>

## <a name="see-also"></a><span data-ttu-id="314c7-107">참조</span><span class="sxs-lookup"><span data-stu-id="314c7-107">See also</span></span>

- [<span data-ttu-id="314c7-108">Visual Basic 언어 참조</span><span class="sxs-lookup"><span data-stu-id="314c7-108">Visual Basic Language Reference</span></span>](../index.md)
- [<span data-ttu-id="314c7-109">코드 분석 경고를 표시하지 않는 방법</span><span class="sxs-lookup"><span data-stu-id="314c7-109">How to suppress code analysis warnings</span></span>](../../../fundamentals/code-analysis/suppress-warnings.md)
