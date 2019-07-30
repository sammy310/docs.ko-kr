---
title: 클래스의 let 바인딩
description: 클래스 정의에서 ' let ' 바인딩을 사용 하 여 F# 클래스의 전용 필드 및 전용 함수를 정의 하는 방법에 대해 알아봅니다.
ms.date: 05/16/2016
ms.openlocfilehash: 0086d3a91f85395c2bd0555f978c5d951c363357
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627476"
---
# <a name="let-bindings-in-classes"></a><span data-ttu-id="cea14-103">클래스의 let 바인딩</span><span class="sxs-lookup"><span data-stu-id="cea14-103">let Bindings in Classes</span></span>

<span data-ttu-id="cea14-104">클래스 정의에서 바인딩을 사용 하 F# `let` 여 클래스에 대 한 전용 필드 및 전용 함수를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cea14-104">You can define private fields and private functions for F# classes by using `let` bindings in the class definition.</span></span>

## <a name="syntax"></a><span data-ttu-id="cea14-105">구문</span><span class="sxs-lookup"><span data-stu-id="cea14-105">Syntax</span></span>

```fsharp
// Field.
[static] let [ mutable ] binding1 [ and ... binding-n ]

// Function.
[static] let [ rec ] binding1 [ and ... binding-n ]
```

## <a name="remarks"></a><span data-ttu-id="cea14-106">설명</span><span class="sxs-lookup"><span data-stu-id="cea14-106">Remarks</span></span>

<span data-ttu-id="cea14-107">이전 구문은 클래스 머리글 및 상속 선언 뒤에, 그리고 멤버 정의 앞에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cea14-107">The previous syntax appears after the class heading and inheritance declarations but before any member definitions.</span></span> <span data-ttu-id="cea14-108">구문은 클래스 외부 `let` 바인딩의 바인딩과 같지만 클래스에 정의 된 이름의 범위는 클래스로 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cea14-108">The syntax is like that of `let` bindings outside of classes, but the names defined in a class have a scope that is limited to the class.</span></span> <span data-ttu-id="cea14-109">`let` 바인딩은 전용 필드 또는 함수를 만듭니다. 데이터 또는 함수를 공개적으로 노출 하려면 속성 또는 멤버 메서드를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="cea14-109">A `let` binding creates a private field or function; to expose data or functions publicly, declare a property or a member method.</span></span>

<span data-ttu-id="cea14-110">Static이 아닌 `let`바인딩은인스턴스 바인딩 이라고 합니다. `let`</span><span class="sxs-lookup"><span data-stu-id="cea14-110">A `let` binding that is not static is called an instance `let` binding.</span></span> <span data-ttu-id="cea14-111">인스턴스 `let` 바인딩은 개체가 생성 될 때 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cea14-111">Instance `let` bindings execute when objects are created.</span></span> <span data-ttu-id="cea14-112">정적 `let` 바인딩은 형식이 처음 사용 되기 전에 실행 되도록 보장 되는 클래스에 대 한 정적 이니셜라이저의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="cea14-112">Static `let` bindings are part of the static initializer for the class, which is guaranteed to execute before the type is first used.</span></span>

<span data-ttu-id="cea14-113">인스턴스 `let` 바인딩 내의 코드는 기본 생성자의 매개 변수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cea14-113">The code within instance `let` bindings can use the primary constructor's parameters.</span></span>

<span data-ttu-id="cea14-114">특성 및 액세스 가능성 한정자는 클래스의 `let` 바인딩에서 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cea14-114">Attributes and accessibility modifiers are not permitted on `let` bindings in classes.</span></span>

<span data-ttu-id="cea14-115">다음 코드 예제에서는 클래스의 여러 `let` 바인딩 형식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cea14-115">The following code examples illustrate several types of `let` bindings in classes.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3001.fs)]

<span data-ttu-id="cea14-116">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cea14-116">The output is as follows.</span></span>

```
10 52 1 204
```

## <a name="alternative-ways-to-create-fields"></a><span data-ttu-id="cea14-117">필드를 만드는 다른 방법</span><span class="sxs-lookup"><span data-stu-id="cea14-117">Alternative Ways to Create Fields</span></span>

<span data-ttu-id="cea14-118">키워드를 `val` 사용 하 여 전용 필드를 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cea14-118">You can also use the `val` keyword to create a private field.</span></span> <span data-ttu-id="cea14-119">`val` 키워드를 사용 하는 경우 개체를 만들 때 필드에 값을 지정 하지 않고 대신 기본값을 사용 하 여 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="cea14-119">When using the `val` keyword, the field is not given a value when the object is created, but instead is initialized with a default value.</span></span> <span data-ttu-id="cea14-120">자세한 내용은 [명시적 필드: Val 키워드](explicit-fields-the-val-keyword.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="cea14-120">For more information, see [Explicit Fields: The val Keyword](explicit-fields-the-val-keyword.md).</span></span>

<span data-ttu-id="cea14-121">멤버 정의를 사용 하 고 키워드 `private` 를 정의에 추가 하 여 클래스에서 전용 필드를 정의할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cea14-121">You can also define private fields in a class by using a member definition and adding the keyword `private` to the definition.</span></span> <span data-ttu-id="cea14-122">이는 코드를 다시 작성 하지 않고 멤버의 액세스 가능성을 변경 해야 하는 경우에 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cea14-122">This can be useful if you expect to change the accessibility of a member without rewriting your code.</span></span> <span data-ttu-id="cea14-123">자세한 내용은 [액세스 제어](../access-control.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cea14-123">For more information, see [Access Control](../access-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="cea14-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="cea14-124">See also</span></span>

- [<span data-ttu-id="cea14-125">멤버</span><span class="sxs-lookup"><span data-stu-id="cea14-125">Members</span></span>](index.md)
- [<span data-ttu-id="cea14-126">클래스의 `do` 바인딩</span><span class="sxs-lookup"><span data-stu-id="cea14-126">`do` Bindings in Classes</span></span>](do-bindings-in-classes.md)
- [<span data-ttu-id="cea14-127">`let`바인딩하</span><span class="sxs-lookup"><span data-stu-id="cea14-127">`let` Bindings</span></span>](../functions/let-bindings.md)
