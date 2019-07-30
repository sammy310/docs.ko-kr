---
title: 형식 약어
description: 코드를 F# 보다 쉽게 읽을 수 있도록 형식에 더 의미 있는 이름을 지정 하는 형식 약어에 대해 알아봅니다.
ms.date: 05/16/2016
ms.openlocfilehash: 339b22a675e3f1ad8a3da207053e611942b55a22
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630205"
---
# <a name="type-abbreviations"></a><span data-ttu-id="c6421-103">형식 약어</span><span class="sxs-lookup"><span data-stu-id="c6421-103">Type Abbreviations</span></span>

<span data-ttu-id="c6421-104">*형식 약어* 는 형식에 대 한 별칭 또는 대체 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c6421-104">A *type abbreviation* is an alias or alternate name for a type.</span></span>

## <a name="syntax"></a><span data-ttu-id="c6421-105">구문</span><span class="sxs-lookup"><span data-stu-id="c6421-105">Syntax</span></span>

```fsharp
type [accessibility-modifier] type-abbreviation = type-name
```

## <a name="remarks"></a><span data-ttu-id="c6421-106">설명</span><span class="sxs-lookup"><span data-stu-id="c6421-106">Remarks</span></span>

<span data-ttu-id="c6421-107">코드를 보다 쉽게 읽을 수 있도록 형식 약어를 사용 하 여 형식에 더 의미 있는 이름을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6421-107">You can use type abbreviations to give a type a more meaningful name, in order to make code easier to read.</span></span> <span data-ttu-id="c6421-108">이를 사용 하 여 작성 하기 어려운 형식에 대해 사용 하기 쉬운 이름을 만들 수도 있습니다. 또한 형식을 사용 하는 모든 코드를 변경 하지 않고 형식 약어를 사용 하 여 기본 형식을 쉽게 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6421-108">You can also use them to create an easy to use name for a type that is otherwise cumbersome to write out. Additionally, you can use type abbreviations to make it easier to change an underlying type without changing all the code that uses the type.</span></span> <span data-ttu-id="c6421-109">다음은 단순 형식 약어입니다.</span><span class="sxs-lookup"><span data-stu-id="c6421-109">The following is a simple type abbreviation.</span></span>

<span data-ttu-id="c6421-110">약어 형식의 액세스 가능성은 기본적 `public`으로로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6421-110">Accessibility of type abbreviations defaults to `public`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2301.fs)]

<span data-ttu-id="c6421-111">형식 약어에는 다음 코드와 같이 제네릭 매개 변수가 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6421-111">Type abbreviations can include generic parameters, as in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2302.fs)]

<span data-ttu-id="c6421-112">이전 코드 `Transform` 에서는 모든 형식의 단일 인수를 사용 하 고 동일한 형식의 단일 값을 반환 하는 함수를 나타내는 형식 약어입니다.</span><span class="sxs-lookup"><span data-stu-id="c6421-112">In the previous code, `Transform` is a type abbreviation that represents a function that takes a single argument of any type and that returns a single value of that same type.</span></span>

<span data-ttu-id="c6421-113">형식 약어는 .NET Framework MSIL 코드에서 유지 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c6421-113">Type abbreviations are not preserved in the .NET Framework MSIL code.</span></span> <span data-ttu-id="c6421-114">따라서 다른 .NET Framework 언어의 F# 어셈블리를 사용 하는 경우 형식 약어에 대해 기본 형식 이름을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6421-114">Therefore, when you use an F# assembly from another .NET Framework language, you must use the underlying type name for a type abbreviation.</span></span>

<span data-ttu-id="c6421-115">형식 약어를 측정 단위에 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6421-115">Type abbreviations can also be used on units of measure.</span></span> <span data-ttu-id="c6421-116">자세한 내용은 [측정 단위](units-of-measure.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c6421-116">For more information, see [Units of Measure](units-of-measure.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c6421-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="c6421-117">See also</span></span>

- [<span data-ttu-id="c6421-118">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="c6421-118">F# Language Reference</span></span>](index.md)
