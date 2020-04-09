---
title: '방법: Parallel.Invoke를 사용하여 병렬 작업 실행'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- task parallelism in .NET
- parallel programming, task parallelism
ms.assetid: 6b3ecd79-dec9-4ce1-abf4-62e5392a59c6
ms.openlocfilehash: f61bbf10bbeef736f66710f50e621c3619355a1d
ms.sourcegitcommit: 1c1a1f9ec0bd1efb3040d86a79f7ee94e207cca5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/03/2020
ms.locfileid: "80635796"
---
# <a name="how-to-use-parallelinvoke-to-execute-parallel-operations"></a><span data-ttu-id="fab2f-102">방법: Parallel.Invoke를 사용하여 병렬 작업 실행</span><span class="sxs-lookup"><span data-stu-id="fab2f-102">How to: Use Parallel.Invoke to Execute Parallel Operations</span></span>

<span data-ttu-id="fab2f-103">이 예제에서는 작업 병렬 라이브러리의 <xref:System.Threading.Tasks.Parallel.Invoke%2A>을 사용하여 작업을 병렬 처리하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fab2f-103">This example shows how to parallelize operations by using <xref:System.Threading.Tasks.Parallel.Invoke%2A> in the Task Parallel Library.</span></span> <span data-ttu-id="fab2f-104">세 가지 작업이 공유 데이터 소스에 대해 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="fab2f-104">Three operations are performed on a shared data source.</span></span> <span data-ttu-id="fab2f-105">소스를 수정하는 작업이 없기 때문에 작업을 간단하게 병렬로 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fab2f-105">The operations can be executed in parallel in a straightforward manner, because none of them modifies the source.</span></span>

> [!NOTE]
> <span data-ttu-id="fab2f-106">이 문서에서는 람다 식을 사용하여 TPL에 대리자를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="fab2f-106">This documentation uses lambda expressions to define delegates in TPL.</span></span> <span data-ttu-id="fab2f-107">C# 또는 Visual Basic의 람다 식을 잘 모르는 경우 [PLINQ 및 TPL의 람다 식](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fab2f-107">If you aren't familiar with lambda expressions in C# or Visual Basic, see [Lambda Expressions in PLINQ and TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).</span></span>

## <a name="example"></a><span data-ttu-id="fab2f-108">예제</span><span class="sxs-lookup"><span data-stu-id="fab2f-108">Example</span></span>

[!code-csharp[TPL_Parallel#06](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/parallelinvoke.cs#06)]
[!code-vb[TPL_Parallel#06](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/parallelinvoke.vb#06)]

<span data-ttu-id="fab2f-109"><xref:System.Threading.Tasks.Parallel.Invoke%2A>에서 동시에 실행하려는 작업을 표시하기만 하면 런타임에서 모든 스레드 예약 세부 정보(호스트 컴퓨터의 코어 수에 맞게 자동으로 크기 조정 포함)를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="fab2f-109">With <xref:System.Threading.Tasks.Parallel.Invoke%2A>, you simply express which actions you want to run concurrently, and the runtime handles all thread scheduling details, including scaling automatically to the number of cores on the host computer.</span></span>

<span data-ttu-id="fab2f-110">이 예제에서는 데이터가 아니라 작업을 병렬 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="fab2f-110">This example parallelizes the operations, not the data.</span></span> <span data-ttu-id="fab2f-111">대체 방법으로 PLINQ를 사용하여 LINQ 쿼리를 병렬 처리하고 쿼리를 순차적으로 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fab2f-111">As an alternate approach, you can parallelize the LINQ queries by using PLINQ and run the queries sequentially.</span></span> <span data-ttu-id="fab2f-112">또는 PLINQ를 사용하여 데이터를 병렬 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fab2f-112">Alternatively, you could parallelize the data by using PLINQ.</span></span> <span data-ttu-id="fab2f-113">다른 옵션은 쿼리와 작업을 둘 다 병렬 처리하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="fab2f-113">Another option is to parallelize both the queries and the tasks.</span></span> <span data-ttu-id="fab2f-114">결과로 생성된 오버헤드로 인해 프로세서가 비교적 적은 호스트 컴퓨터에서는 성능이 저하될 수도 있지만, 프로세서가 많은 컴퓨터에서는 효율적으로 크기가 조정됩니다.</span><span class="sxs-lookup"><span data-stu-id="fab2f-114">Although the resulting overhead might degrade performance on host computers with relatively few processors, it scales better on computers with many processors.</span></span>

## <a name="compile-the-code"></a><span data-ttu-id="fab2f-115">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="fab2f-115">Compile the Code</span></span>

<span data-ttu-id="fab2f-116">전체 예제를 복사하여 Microsoft Visual Studio 프로젝트에 붙여넣고 **F5** 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="fab2f-116">Copy and paste the entire example into a Microsoft Visual Studio project and press **F5**.</span></span>

## <a name="see-also"></a><span data-ttu-id="fab2f-117">참조</span><span class="sxs-lookup"><span data-stu-id="fab2f-117">See also</span></span>

- [<span data-ttu-id="fab2f-118">병렬 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="fab2f-118">Parallel Programming</span></span>](../../../docs/standard/parallel-programming/index.md)
- [<span data-ttu-id="fab2f-119">방법: 작업 및 해당 자식 취소</span><span class="sxs-lookup"><span data-stu-id="fab2f-119">How to: Cancel a Task and Its Children</span></span>](../../../docs/standard/parallel-programming/how-to-cancel-a-task-and-its-children.md)
- [<span data-ttu-id="fab2f-120">PLINQ(병렬 LINQ)</span><span class="sxs-lookup"><span data-stu-id="fab2f-120">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/introduction-to-plinq.md)
