---
description: '#error - C# 참조'
title: '#error - C# 참조'
ms.date: 08/24/2020
f1_keywords:
- '#error'
helpviewer_keywords:
- '#error directive [C#]'
ms.assetid: f2a7f3af-4cf9-4111-b369-70204d24b26b
ms.openlocfilehash: 76325901c5e39f340545b186a0aa9546cd853ff8
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2020
ms.locfileid: "89138100"
---
# <a name="error-c-reference"></a><span data-ttu-id="9be42-103">#error(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="9be42-103">#error (C# Reference)</span></span>

<span data-ttu-id="9be42-104">`#error`를 사용하면 코드의 특정 위치에서 [CS1029](../compiler-messages/cs1029.md) 사용자 정의 오류를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9be42-104">`#error` lets you generate a [CS1029](../compiler-messages/cs1029.md) user-defined error from a specific location in your code.</span></span> <span data-ttu-id="9be42-105">예:</span><span class="sxs-lookup"><span data-stu-id="9be42-105">For example:</span></span>

```csharp
#error Deprecated code in this method.
```

> [!NOTE]
> <span data-ttu-id="9be42-106">컴파일러는 `#error version`을 특수한 방식으로 처리하며 사용된 컴파일러 및 언어 버전을 포함한 메시지가 있는 컴파일러 오류 CS8304를 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="9be42-106">The compiler treats `#error version` in a special way and reports a compiler error, CS8304, with a message containing the used compiler and language versions.</span></span>

## <a name="remarks"></a><span data-ttu-id="9be42-107">설명</span><span class="sxs-lookup"><span data-stu-id="9be42-107">Remarks</span></span>

<span data-ttu-id="9be42-108">`#error`는 일반적으로 조건부 지시문에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9be42-108">A common use of `#error` is in a conditional directive.</span></span>

<span data-ttu-id="9be42-109">[#warning](./preprocessor-warning.md)을 사용하여 사용자 정의 경고를 생성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9be42-109">It is also possible to generate a user-defined warning with [#warning](./preprocessor-warning.md).</span></span>

## <a name="example"></a><span data-ttu-id="9be42-110">예제</span><span class="sxs-lookup"><span data-stu-id="9be42-110">Example</span></span>

```csharp
// preprocessor_error.cs
// CS1029 expected
#define DEBUG
class MainClass
{
    static void Main()
    {
#if DEBUG
#error DEBUG is defined
#endif
    }
}
```

## <a name="see-also"></a><span data-ttu-id="9be42-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9be42-111">See also</span></span>

- [<span data-ttu-id="9be42-112">C# 참조</span><span class="sxs-lookup"><span data-stu-id="9be42-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="9be42-113">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="9be42-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="9be42-114">C# 전처리기 지시문</span><span class="sxs-lookup"><span data-stu-id="9be42-114">C# Preprocessor Directives</span></span>](./index.md)
