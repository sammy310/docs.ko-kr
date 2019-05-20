---
title: '방법: 포인터 변수의 값 가져오기 - C# 프로그래밍 가이드'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointer expressions [C#], indirection
- pointers [C#], indirection
- variables [C#], pointers
- pointers [C#], * operator
ms.assetid: 460a813a-4995-44c1-9de2-213b91dc7668
ms.openlocfilehash: 9a10bcc809f3ecbc9a0fa9b917940b8e030fab8f
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65635095"
---
# <a name="how-to-obtain-the-value-of-a-pointer-variable-c-programming-guide"></a><span data-ttu-id="7c9db-102">방법: 포인터 변수의 값 가져오기(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="7c9db-102">How to: obtain the value of a pointer variable (C# Programming Guide)</span></span>

<span data-ttu-id="7c9db-103">포인터 간접 참조 연산자를 사용하여 포인터가 가리키는 위치에 있는 변수를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c9db-103">Use the pointer indirection operator to obtain the variable at the location pointed to by a pointer.</span></span> <span data-ttu-id="7c9db-104">식의 형식은 다음과 같습니다. 여기서 `p`는 포인터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="7c9db-104">The expression takes the following form, where `p` is a pointer type:</span></span>  

```csharp
*p;  
```

<span data-ttu-id="7c9db-105">포인터 형식이 아닌 식에서는 단항 간접 참조 연산자를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7c9db-105">You cannot use the unary indirection operator on an expression of any type other than the pointer type.</span></span> <span data-ttu-id="7c9db-106">또한 [void](../../../csharp/language-reference/keywords/void.md) 포인터에는 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7c9db-106">Also, you cannot apply it to a [void](../../../csharp/language-reference/keywords/void.md) pointer.</span></span>  

<span data-ttu-id="7c9db-107">[null](../../../csharp/language-reference/keywords/null.md) 포인터에 간접 참조 연산자를 적용할 때의 결과는 구현에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="7c9db-107">When you apply the indirection operator to a [null](../../../csharp/language-reference/keywords/null.md) pointer, the result depends on the implementation.</span></span>  

## <a name="example"></a><span data-ttu-id="7c9db-108">예제</span><span class="sxs-lookup"><span data-stu-id="7c9db-108">Example</span></span>

<span data-ttu-id="7c9db-109">다음 예제에서는 다양한 형식의 포인터를 사용하여 `char` 형식의 변수에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="7c9db-109">In the following example, a variable of the type `char` is accessed by using pointers of different types.</span></span> <span data-ttu-id="7c9db-110">변수에 할당되는 물리적 주소가 변경될 수 있으므로 `theChar`의 주소는 실행할 때마다 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="7c9db-110">Note that the address of `theChar` will vary from run to run, because the physical address allocated to a variable can change.</span></span>  

 [!code-csharp[csProgGuidePointers#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers2.cs#5)]  

 [!code-csharp[csProgGuidePointers#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#6)]  
  
<span data-ttu-id="7c9db-111">**Value of theChar = Z**</span><span class="sxs-lookup"><span data-stu-id="7c9db-111">**Value of theChar = Z**</span></span>  
<span data-ttu-id="7c9db-112">**Address of theChar = 12F718**</span><span class="sxs-lookup"><span data-stu-id="7c9db-112">**Address of theChar = 12F718**</span></span>  
<span data-ttu-id="7c9db-113">**Value of pChar = Z**</span><span class="sxs-lookup"><span data-stu-id="7c9db-113">**Value of pChar = Z**</span></span>  
<span data-ttu-id="7c9db-114">**Value of pInt = 90**</span><span class="sxs-lookup"><span data-stu-id="7c9db-114">**Value of pInt = 90**</span></span>  

## <a name="see-also"></a><span data-ttu-id="7c9db-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7c9db-115">See also</span></span>

- [<span data-ttu-id="7c9db-116">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="7c9db-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="7c9db-117">포인터 형식</span><span class="sxs-lookup"><span data-stu-id="7c9db-117">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="7c9db-118">유형</span><span class="sxs-lookup"><span data-stu-id="7c9db-118">Types</span></span>](../../../csharp/language-reference/keywords/types.md)
- [<span data-ttu-id="7c9db-119">unsafe</span><span class="sxs-lookup"><span data-stu-id="7c9db-119">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)
- [<span data-ttu-id="7c9db-120">fixed 문</span><span class="sxs-lookup"><span data-stu-id="7c9db-120">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="7c9db-121">stackalloc</span><span class="sxs-lookup"><span data-stu-id="7c9db-121">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
