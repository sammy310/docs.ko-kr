---
title: '방법: 병렬 작업을 사용하여 이진 트리 트래버스'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to traverse a tree
ms.assetid: 4265d169-6c69-4f36-b10d-b7ae7f72f4df
ms.openlocfilehash: 5ac81a61691ec20daafc9e18978ba5814a150383
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2020
ms.locfileid: "84288071"
---
# <a name="how-to-traverse-a-binary-tree-with-parallel-tasks"></a><span data-ttu-id="bd3ad-102">방법: 병렬 작업을 사용하여 이진 트리 트래버스</span><span class="sxs-lookup"><span data-stu-id="bd3ad-102">How to: Traverse a Binary Tree with Parallel Tasks</span></span>
<span data-ttu-id="bd3ad-103">다음 예제는 병렬 작업을 사용하여 트리 데이터 구조를 트래버스할 수 있는 두 가지 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="bd3ad-103">The following example shows two ways in which parallel tasks can be used to traverse a tree data structure.</span></span> <span data-ttu-id="bd3ad-104">트리 자체의 생성은 실행으로 남습니다.</span><span class="sxs-lookup"><span data-stu-id="bd3ad-104">The creation of the tree itself is left as an exercise.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bd3ad-105">예제</span><span class="sxs-lookup"><span data-stu-id="bd3ad-105">Example</span></span>  
 [!code-csharp[TPL#16](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl/cs/tpl.cs#16)]
 [!code-vb[TPL#16](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl/vb/treewalk.vb#16)]  
  
 <span data-ttu-id="bd3ad-106">표시된 두 가지 방법은 기능적으로 동등합니다.</span><span class="sxs-lookup"><span data-stu-id="bd3ad-106">The two methods shown are functionally equivalent.</span></span> <span data-ttu-id="bd3ad-107"><xref:System.Threading.Tasks.TaskFactory.StartNew%2A> 메서드를 사용하여 작업을 생성하고 실행함으로써 작업을 대기하고 예외를 처리하는 데 사용할 수 있는 작업에서 핸들을 다시 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="bd3ad-107">By using the <xref:System.Threading.Tasks.TaskFactory.StartNew%2A> method to create and run the tasks, you get a handle back from the tasks which can be used to wait on the tasks and handle exceptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd3ad-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bd3ad-108">See also</span></span>

- [<span data-ttu-id="bd3ad-109">TPL(작업 병렬 라이브러리)</span><span class="sxs-lookup"><span data-stu-id="bd3ad-109">Task Parallel Library (TPL)</span></span>](task-parallel-library-tpl.md)
