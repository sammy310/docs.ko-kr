---
title: 대리자를 결합하는 방법(멀티캐스트 대리자) - C# 프로그래밍 가이드
description: 대리자를 결합하여 멀티캐스트 대리자를 만드는 방법을 알아봅니다. 코드 예제를 살펴보고 사용 가능한 추가 리소스를 확인합니다.
ms.date: 07/20/2015
helpviewer_keywords:
- delegates [C#], combining
- multicast delegates [C#]
ms.assetid: 4e689450-6d0c-46de-acfd-f961018ae5dd
ms.openlocfilehash: d23ea758c9da2c3399f5d98e81360cc250b428a1
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302739"
---
# <a name="how-to-combine-delegates-multicast-delegates-c-programming-guide"></a><span data-ttu-id="d8bc6-104">대리자를 결합하는 방법(멀티캐스트 대리자)(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="d8bc6-104">How to combine delegates (Multicast Delegates) (C# Programming Guide)</span></span>
<span data-ttu-id="d8bc6-105">이 예제에서는 멀티캐스트 대리자를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d8bc6-105">This example demonstrates how to create multicast delegates.</span></span> <span data-ttu-id="d8bc6-106">[대리자](../../language-reference/builtin-types/reference-types.md) 개체의 유용한 속성은 `+` 연산자를 사용하여 하나의 대리자 인스턴스에 여러 개체를 할당할 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d8bc6-106">A useful property of [delegate](../../language-reference/builtin-types/reference-types.md) objects is that multiple objects can be assigned to one delegate instance by using the `+` operator.</span></span> <span data-ttu-id="d8bc6-107">멀티캐스트 대리자는 할당된 대리자 목록을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="d8bc6-107">The multicast delegate contains a list of the assigned delegates.</span></span> <span data-ttu-id="d8bc6-108">멀티캐스트 대리자가 호출되면 목록에 있는 대리자가 순서대로 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8bc6-108">When the multicast delegate is called, it invokes the delegates in the list, in order.</span></span> <span data-ttu-id="d8bc6-109">같은 형식의 대리자만 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8bc6-109">Only delegates of the same type can be combined.</span></span>  
  
 <span data-ttu-id="d8bc6-110">`-` 연산자는 멀티캐스트 대리자에서 구성 요소 대리자를 제거하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8bc6-110">The `-` operator can be used to remove a component delegate from a multicast delegate.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d8bc6-111">예제</span><span class="sxs-lookup"><span data-stu-id="d8bc6-111">Example</span></span>  
 [!code-csharp[csProgGuideDelegates#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#11)]  
  
## <a name="see-also"></a><span data-ttu-id="d8bc6-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d8bc6-112">See also</span></span>

- <xref:System.MulticastDelegate>
- [<span data-ttu-id="d8bc6-113">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="d8bc6-113">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="d8bc6-114">이벤트</span><span class="sxs-lookup"><span data-stu-id="d8bc6-114">Events</span></span>](../events/index.md)
