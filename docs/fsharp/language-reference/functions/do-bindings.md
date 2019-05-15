---
title: do 바인딩
description: 에 대해 알아봅니다 어떻게는 F# 함수 또는 값을 정의 하지 않고 코드를 실행 하는 바인딩 ' 않습니다'.
ms.date: 05/16/2016
ms.openlocfilehash: 0755e36912fc4e5a645e55eb4bee5c730a56cadf
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641905"
---
# <a name="do-bindings"></a><span data-ttu-id="db1e0-103">do 바인딩</span><span class="sxs-lookup"><span data-stu-id="db1e0-103">do Bindings</span></span>

<span data-ttu-id="db1e0-104">`do` 함수 또는 값을 정의 하지 않고 코드를 실행 하려면 바인딩이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="db1e0-104">A `do` binding is used to execute code without defining a function or value.</span></span> <span data-ttu-id="db1e0-105">또한 수행 바인딩 수 있습니다 참조 클래스를 사용 [ `do` 클래스에 바인딩](../members/do-bindings-in-classes.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="db1e0-105">Also, do bindings can be used in classes, see [`do` Bindings in Classes](../members/do-bindings-in-classes.md).</span></span>

## <a name="syntax"></a><span data-ttu-id="db1e0-106">구문</span><span class="sxs-lookup"><span data-stu-id="db1e0-106">Syntax</span></span>

```fsharp
[ attributes ]
[ do ]expression
```

## <a name="remarks"></a><span data-ttu-id="db1e0-107">설명</span><span class="sxs-lookup"><span data-stu-id="db1e0-107">Remarks</span></span>

<span data-ttu-id="db1e0-108">사용 된 `do` 함수 또는 값의 정의 의존 하지 않고 코드를 실행 하려는 경우 바인딩.</span><span class="sxs-lookup"><span data-stu-id="db1e0-108">Use a `do` binding when you want to execute code independently of a function or value definition.</span></span> <span data-ttu-id="db1e0-109">식에는 `do` 바인딩을 반환 해야 합니다 `unit`합니다.</span><span class="sxs-lookup"><span data-stu-id="db1e0-109">The expression in a `do` binding must return `unit`.</span></span> <span data-ttu-id="db1e0-110">코드에서 최상위 `do` 바인딩 모듈 초기화 될 때 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="db1e0-110">Code in a top-level `do` binding is executed when the module is initialized.</span></span> <span data-ttu-id="db1e0-111">키워드 `do` 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="db1e0-111">The keyword `do` is optional.</span></span>

<span data-ttu-id="db1e0-112">최상위 수준에 특성을 적용할 수 있습니다 `do` 바인딩.</span><span class="sxs-lookup"><span data-stu-id="db1e0-112">Attributes can be applied to a top-level `do` binding.</span></span> <span data-ttu-id="db1e0-113">예를 들어, 프로그램 COM interop를 사용 하는 경우 적용할는 `STAThread` 프로그램 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="db1e0-113">For example, if your program uses COM interop, you might want to apply the `STAThread` attribute to your program.</span></span> <span data-ttu-id="db1e0-114">특성을 사용 하 여이 수행할 수는 `do` 다음 코드 에서처럼 바인딩.</span><span class="sxs-lookup"><span data-stu-id="db1e0-114">You can do this by using an attribute on a `do` binding, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet201.fs)]

## <a name="see-also"></a><span data-ttu-id="db1e0-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="db1e0-115">See also</span></span>

- [<span data-ttu-id="db1e0-116">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="db1e0-116">F# Language Reference</span></span>](../index.md)
- [<span data-ttu-id="db1e0-117">함수</span><span class="sxs-lookup"><span data-stu-id="db1e0-117">Functions</span></span>](index.md)
