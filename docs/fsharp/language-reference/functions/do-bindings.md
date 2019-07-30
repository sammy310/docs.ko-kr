---
title: do 바인딩
description: 함수 또는 값 F# 을 정의 하지 않고 ' do ' 바인딩을 사용 하 여 코드를 실행 하는 방법을 알아봅니다.
ms.date: 05/16/2016
ms.openlocfilehash: f98f523296bfaceeda35d4861eafbfeaa5a60c32
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630536"
---
# <a name="do-bindings"></a><span data-ttu-id="3c89a-103">do 바인딩</span><span class="sxs-lookup"><span data-stu-id="3c89a-103">do Bindings</span></span>

<span data-ttu-id="3c89a-104">`do` 바인딩은 함수나 값을 정의 하지 않고 코드를 실행 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c89a-104">A `do` binding is used to execute code without defining a function or value.</span></span> <span data-ttu-id="3c89a-105">또한 클래스에서 바인딩 사용은 [ `do` 클래스의 바인딩](../members/do-bindings-in-classes.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3c89a-105">Also, do bindings can be used in classes, see [`do` Bindings in Classes](../members/do-bindings-in-classes.md).</span></span>

## <a name="syntax"></a><span data-ttu-id="3c89a-106">구문</span><span class="sxs-lookup"><span data-stu-id="3c89a-106">Syntax</span></span>

```fsharp
[ attributes ]
[ do ]expression
```

## <a name="remarks"></a><span data-ttu-id="3c89a-107">설명</span><span class="sxs-lookup"><span data-stu-id="3c89a-107">Remarks</span></span>

<span data-ttu-id="3c89a-108">함수 또는 값 정의와 별개로 코드를 실행 하려는 경우 바인딩을사용합니다.`do`</span><span class="sxs-lookup"><span data-stu-id="3c89a-108">Use a `do` binding when you want to execute code independently of a function or value definition.</span></span> <span data-ttu-id="3c89a-109">`do` 바인딩의 식은를 반환 `unit`해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c89a-109">The expression in a `do` binding must return `unit`.</span></span> <span data-ttu-id="3c89a-110">최상위 `do` 바인딩의 코드는 모듈이 초기화 될 때 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c89a-110">Code in a top-level `do` binding is executed when the module is initialized.</span></span> <span data-ttu-id="3c89a-111">키워드 `do` 는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="3c89a-111">The keyword `do` is optional.</span></span>

<span data-ttu-id="3c89a-112">최상위 `do` 바인딩에 특성을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c89a-112">Attributes can be applied to a top-level `do` binding.</span></span> <span data-ttu-id="3c89a-113">예를 들어 프로그램에서 COM interop 사용 하는 경우 프로그램에 특성을 적용 `STAThread` 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3c89a-113">For example, if your program uses COM interop, you might want to apply the `STAThread` attribute to your program.</span></span> <span data-ttu-id="3c89a-114">다음 코드와 같이 `do` 바인딩에 특성을 사용 하 여이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c89a-114">You can do this by using an attribute on a `do` binding, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet201.fs)]

## <a name="see-also"></a><span data-ttu-id="3c89a-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="3c89a-115">See also</span></span>

- [<span data-ttu-id="3c89a-116">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="3c89a-116">F# Language Reference</span></span>](../index.md)
- [<span data-ttu-id="3c89a-117">함수</span><span class="sxs-lookup"><span data-stu-id="3c89a-117">Functions</span></span>](index.md)
