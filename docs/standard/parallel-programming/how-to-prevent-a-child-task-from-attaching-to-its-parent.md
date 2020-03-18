---
title: '방법: 자식 작업이 부모 작업에 연결되지 않도록 방지'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, preventing attachments
ms.assetid: c0fb85d4-9e80-4905-9f65-29acc54201c4
ms.openlocfilehash: 265b6d06f17a1dfbee3f009feff1ee1645e62a46
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2020
ms.locfileid: "73139255"
---
# <a name="how-to-prevent-a-child-task-from-attaching-to-its-parent"></a><span data-ttu-id="c89d2-102">방법: 자식 작업이 부모 작업에 연결되지 않도록 방지</span><span class="sxs-lookup"><span data-stu-id="c89d2-102">How to: Prevent a Child Task from Attaching to its Parent</span></span>
<span data-ttu-id="c89d2-103">이 문서에서는 자식 작업이 부모 작업에 연결하는 것을 방지하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c89d2-103">This document demonstrates how to prevent a child task from attaching to the parent task.</span></span> <span data-ttu-id="c89d2-104">자식 작업이 부모에 연결하는 것을 방지하는 방법은 타사가 작성하고 마찬가지로 작업을 사용하는 구성 요소를 호출하는 경우 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="c89d2-104">Preventing a child task from attaching to its parent is useful when you call a component that is written by a third party and that also uses tasks.</span></span> <span data-ttu-id="c89d2-105">예를 들어 <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent?displayProperty=nameWithType> 옵션을 사용하여 <xref:System.Threading.Tasks.Task> 또는 <xref:System.Threading.Tasks.Task%601> 개체를 만드는 타사 구성 요소는 오래 실행되는 경우 코드에서 문제를 유발하거나 처리되지 않은 예외를 throw할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c89d2-105">For example, a third-party component that uses the <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent?displayProperty=nameWithType> option to create a <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601> object can cause problems in your code if it is long-running or throws an unhandled exception.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c89d2-106">예제</span><span class="sxs-lookup"><span data-stu-id="c89d2-106">Example</span></span>  
 <span data-ttu-id="c89d2-107">다음 예제에서는 기본 옵션의 효과와 자식 작업이 부모에 연결하는 것을 방지하는 효과를 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="c89d2-107">The following example compares the effects of using the default options to the effects of preventing a child task from attaching to the parent.</span></span> <span data-ttu-id="c89d2-108">이 예제에서는 마찬가지로 <xref:System.Threading.Tasks.Task> 개체를 사용하는 타사 라이브러리를 호출하는 <xref:System.Threading.Tasks.Task> 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c89d2-108">The example creates a <xref:System.Threading.Tasks.Task> object that calls into a third-party library that also uses a <xref:System.Threading.Tasks.Task> object.</span></span> <span data-ttu-id="c89d2-109">타사 라이브러리는 <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent> 옵션을 사용하여 <xref:System.Threading.Tasks.Task> 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c89d2-109">The third-party library uses the <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent> option to create the <xref:System.Threading.Tasks.Task> object.</span></span> <span data-ttu-id="c89d2-110">애플리케이션은 <xref:System.Threading.Tasks.TaskCreationOptions.DenyChildAttach?displayProperty=nameWithType> 옵션을 사용하여 부모 작업을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c89d2-110">The application uses the <xref:System.Threading.Tasks.TaskCreationOptions.DenyChildAttach?displayProperty=nameWithType> option to create the parent task.</span></span> <span data-ttu-id="c89d2-111">이 옵션은 자식 작업에서 <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent> 지정을 제거하도록 런타임에 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="c89d2-111">This option instructs the runtime to remove the <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent> specification in child tasks.</span></span>  
  
 [!code-csharp[TPL_DenyChildAttach#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_denychildattach/cs/denychildattach.cs#1)]
 [!code-vb[TPL_DenyChildAttach#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_denychildattach/vb/denychildattach.vb#1)]  
  
 <span data-ttu-id="c89d2-112">부모 작업은 자식 작업이 모두 완료될 때까지 완료되지 않기 때문에 오래 실행되는 자식 작업은 전체적인 애플리케이션의 성능을 저하시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c89d2-112">Because a parent task does not finish until all child tasks finish, a long-running child task can cause the overall application to perform poorly.</span></span> <span data-ttu-id="c89d2-113">이 예제에서 애플리케이션이 기본 옵션을 사용하여 부모 작업을 만들 때 자식 작업은 부모 작업이 완료되기 전에 완료되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c89d2-113">In this example, when the application uses the default options to create the parent task, the child task must finish before the parent task finishes.</span></span> <span data-ttu-id="c89d2-114">애플리케이션에서 <xref:System.Threading.Tasks.TaskCreationOptions.DenyChildAttach?displayProperty=nameWithType> 옵션을 사용하는 경우 자식은 부모에 연결되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c89d2-114">When the application uses the <xref:System.Threading.Tasks.TaskCreationOptions.DenyChildAttach?displayProperty=nameWithType> option, the child is not attached to the parent.</span></span> <span data-ttu-id="c89d2-115">따라서 애플리케이션은 부모 작업이 완료된 후와 자식 작업이 완료되기를 기다려야 하기 전에 추가 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c89d2-115">Therefore, the application can perform additional work after the parent task finishes and before it must wait for the child task to finish.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c89d2-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c89d2-116">See also</span></span>

- [<span data-ttu-id="c89d2-117">작업 기반 비동기 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="c89d2-117">Task-based Asynchronous Programming</span></span>](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)
