---
title: '방법: 데이터 흐름 블록의 병렬 처리 수준 지정'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dataflow block, specifying parallelism in TPL
- Task Parallel Library, dataflows
- TPL dataflow library, specifying parallelism
ms.assetid: e4088541-ee05-40db-95f5-147cfe62fde7
ms.openlocfilehash: 50399d6cd32fe310089395ac8c660b08151ba808
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2020
ms.locfileid: "73141659"
---
# <a name="how-to-specify-the-degree-of-parallelism-in-a-dataflow-block"></a><span data-ttu-id="3906e-102">방법: 데이터 흐름 블록의 병렬 처리 수준 지정</span><span class="sxs-lookup"><span data-stu-id="3906e-102">How to: Specify the Degree of Parallelism in a Dataflow Block</span></span>
<span data-ttu-id="3906e-103">이 문서에서는 <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions.MaxDegreeOfParallelism%2A?displayProperty=nameWithType> 속성을 설정하여 실행 데이터 흐름 블록이 한 번에 둘 이상의 메시지를 처리할 수 있도록 하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3906e-103">This document describes how to set the <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions.MaxDegreeOfParallelism%2A?displayProperty=nameWithType> property to enable an execution dataflow block to process more than one message at a time.</span></span> <span data-ttu-id="3906e-104">이 방법은 오래 실행되는 계산을 수행하는 데이터 흐름 블록이 있고 메시지를 병렬로 처리하면 혜택을 얻을 수 있는 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="3906e-104">Doing this is useful when you have a dataflow block that performs a long-running computation and can benefit from processing messages in parallel.</span></span> <span data-ttu-id="3906e-105">이 예제에서는 <xref:System.Threading.Tasks.Dataflow.ActionBlock%601?displayProperty=nameWithType> 클래스를 사용하여 여러 데이터 흐름 작업을 동시에 수행합니다. 하지만 TPL 데이터 흐름 라이브러리에서 제공하는 미리 정의된 실행 블록 형식인 <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>, <xref:System.Threading.Tasks.Dataflow.TransformBlock%602?displayProperty=nameWithType> 및 <xref:System.Threading.Tasks.Dataflow.TransformManyBlock%602?displayProperty=nameWithType>에서 최대 병렬 처리 수준을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3906e-105">This example uses the <xref:System.Threading.Tasks.Dataflow.ActionBlock%601?displayProperty=nameWithType> class to perform multiple dataflow operations concurrently; however, you can specify the maximum degree of parallelism in any of the predefined execution block types that the TPL Dataflow Library provides, <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>, <xref:System.Threading.Tasks.Dataflow.TransformBlock%602?displayProperty=nameWithType>, and <xref:System.Threading.Tasks.Dataflow.TransformManyBlock%602?displayProperty=nameWithType>.</span></span>

[!INCLUDE [tpl-install-instructions](../../../includes/tpl-install-instructions.md)]

## <a name="example"></a><span data-ttu-id="3906e-106">예제</span><span class="sxs-lookup"><span data-stu-id="3906e-106">Example</span></span>  
 <span data-ttu-id="3906e-107">다음 예제에서는 두 가지 데이터 흐름 계산을 수행하고 각 계산에 필요한 경과 시간을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="3906e-107">The following example performs two dataflow computations and prints the elapsed time that is required for each computation.</span></span> <span data-ttu-id="3906e-108">첫 번째 계산에서는 최대 병렬 처리 수준을 기본값 1로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3906e-108">The first computation specifies a maximum degree of parallelism of 1, which is the default.</span></span> <span data-ttu-id="3906e-109">최대 병렬 처리 수준이 1이면 데이터 흐름 블록이 메시지를 연속적으로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="3906e-109">A maximum degree of parallelism of 1 causes the dataflow block to process messages serially.</span></span> <span data-ttu-id="3906e-110">두 번째 계산은 사용 가능한 프로세서 수와 동일한 최대 병렬 처리 수준을 지정하는 점을 제외하고 첫 번째 계산과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="3906e-110">The second computation resembles the first, except that it specifies a maximum degree of parallelism that is equal to the number of available processors.</span></span> <span data-ttu-id="3906e-111">이러한 지정에 따라 데이터 흐름 블록이 여러 작업을 병렬로 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3906e-111">This enables the dataflow block to perform multiple operations in parallel.</span></span>  
  
 [!code-csharp[TPLDataflow_DegreeOfParallelism#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_degreeofparallelism/cs/dataflowdegreeofparallelism.cs#1)]
 [!code-vb[TPLDataflow_DegreeOfParallelism#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_degreeofparallelism/vb/dataflowdegreeofparallelism.vb#1)]  
  
## <a name="robust-programming"></a><span data-ttu-id="3906e-112">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="3906e-112">Robust Programming</span></span>  
 <span data-ttu-id="3906e-113">기본적으로 미리 정의된 각각의 데이터 흐름 블록은 메시지를 받은 순서대로 메시지를 전파합니다.</span><span class="sxs-lookup"><span data-stu-id="3906e-113">By default, each predefined dataflow block propagates out messages in the order in which the messages are received.</span></span>  <span data-ttu-id="3906e-114">1보다 큰 최대 병렬 처리 수준을 지정하는 경우 여러 메시지가 동시에 처리되지만 메시지는 수신된 순서대로 전파됩니다.</span><span class="sxs-lookup"><span data-stu-id="3906e-114">Although multiple messages are processed simultaneously when you specify a maximum degree of parallelism that is greater than 1, they are still propagated out in the order in which they are received.</span></span>  
  
 <span data-ttu-id="3906e-115"><xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions.MaxDegreeOfParallelism%2A> 속성이 최대 병렬 처리 수준을 나타내기 때문에 데이터 흐름 블록은 지정한 것보다 낮은 병렬 처리 수준으로 실행될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3906e-115">Because the <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions.MaxDegreeOfParallelism%2A> property represents the maximum degree of parallelism, the dataflow block might execute with a lesser degree of parallelism than you specify.</span></span> <span data-ttu-id="3906e-116">데이터 흐름 블록은 기능적 요구 사항을 충족하기 위해서나 사용 가능한 시스템 리소스의 부족 때문에 낮은 병렬 처리 수준을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3906e-116">The dataflow block can use a lesser degree of parallelism to meet its functional requirements or to account for a lack of available system resources.</span></span> <span data-ttu-id="3906e-117">데이터 흐름 블록은 지정한 것보다 높은 병렬 처리 수준을 선택하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3906e-117">A dataflow block never chooses a greater degree of parallelism than you specify.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3906e-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3906e-118">See also</span></span>

- [<span data-ttu-id="3906e-119">데이터 흐름</span><span class="sxs-lookup"><span data-stu-id="3906e-119">Dataflow</span></span>](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
