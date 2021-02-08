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
# <a name="bc36550-extension-attribute-can-be-applied-only-to-module-sub-or-function-declarations"></a><span data-ttu-id="13edb-103">BC36550: ' Extension ' 특성은 ' Module ', ' Sub ' 또는 ' Function ' 선언에만 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13edb-103">BC36550: 'Extension' attribute can be applied only to 'Module', 'Sub', or 'Function' declarations</span></span>

<span data-ttu-id="13edb-104">Visual Basic에서 데이터 형식을 확장 하는 유일한 방법은 표준 모듈 내에 확장 메서드를 정의 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="13edb-104">The only way to extend a data type in Visual Basic is to define an extension method inside a standard module.</span></span> <span data-ttu-id="13edb-105">확장 메서드는 `Sub` 프로시저 또는 프로시저일 수 있습니다 `Function` .</span><span class="sxs-lookup"><span data-stu-id="13edb-105">The extension method can be a `Sub` procedure or a `Function` procedure.</span></span> <span data-ttu-id="13edb-106">모든 확장 메서드는 `<Extension()>` 네임 스페이스에서 확장 특성으로 표시 되어야 합니다 <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="13edb-106">All extension methods must be marked with the extension attribute, `<Extension()>`, from the <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="13edb-107">필요에 따라 확장 메서드를 포함 하는 모듈을 동일한 방식으로 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13edb-107">Optionally, a module that contains an extension method may be marked in the same way.</span></span> <span data-ttu-id="13edb-108">확장 특성은 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="13edb-108">No other use of the extension attribute is valid.</span></span>

<span data-ttu-id="13edb-109">**오류 ID:** BC36550</span><span class="sxs-lookup"><span data-stu-id="13edb-109">**Error ID:** BC36550</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="13edb-110">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="13edb-110">To correct this error</span></span>

- <span data-ttu-id="13edb-111">확장 특성을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="13edb-111">Remove the extension attribute.</span></span>

- <span data-ttu-id="13edb-112">바깥쪽 모듈에 정의 된 메서드로 확장을 다시 디자인 합니다.</span><span class="sxs-lookup"><span data-stu-id="13edb-112">Redesign your extension as a method, defined in an enclosing module.</span></span>

## <a name="example"></a><span data-ttu-id="13edb-113">예제</span><span class="sxs-lookup"><span data-stu-id="13edb-113">Example</span></span>

<span data-ttu-id="13edb-114">다음 예제에서는 `Print` 데이터 형식에 대 한 메서드를 정의 합니다 `String` .</span><span class="sxs-lookup"><span data-stu-id="13edb-114">The following example defines a `Print` method for the `String` data type.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="13edb-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="13edb-115">See also</span></span>

- [<span data-ttu-id="13edb-116">특성 개요</span><span class="sxs-lookup"><span data-stu-id="13edb-116">Attributes overview</span></span>](../../programming-guide/concepts/attributes/index.md)
- [<span data-ttu-id="13edb-117">확장명 메서드</span><span class="sxs-lookup"><span data-stu-id="13edb-117">Extension Methods</span></span>](../../programming-guide/language-features/procedures/extension-methods.md)
- [<span data-ttu-id="13edb-118">Module 문</span><span class="sxs-lookup"><span data-stu-id="13edb-118">Module Statement</span></span>](../statements/module-statement.md)
