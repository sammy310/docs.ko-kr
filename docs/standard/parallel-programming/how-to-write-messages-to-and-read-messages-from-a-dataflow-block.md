---
title: '방법: 데이터 흐름 블록에 메시지 쓰기 및 데이터 흐름 블록에서 메시지 읽기'
ms.date: 09/10/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Task Parallel Library, dataflows
- TPL dataflow library, reading and writing messages
ms.assetid: 1a9bf078-aa82-46eb-b95a-f87237f028c5
ms.openlocfilehash: 8eb92d917bb2b03c2a505a2ba238598e0c1a450c
ms.sourcegitcommit: 6d4ee46871deb9ea1e45bb5f3784474e240bbc26
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/11/2020
ms.locfileid: "90022859"
---
# <a name="how-to-write-and-read-messages-from-a-dataflow-block"></a><span data-ttu-id="50a01-102">방법: 데이터 흐름 블록에 메시지 쓰기 및 데이터 흐름 블록에서 메시지 읽기</span><span class="sxs-lookup"><span data-stu-id="50a01-102">How to: Write and read messages from a Dataflow block</span></span>

<span data-ttu-id="50a01-103">이 문서에서는 TPL(작업 병렬 라이브러리) 데이터 흐름 라이브러리를 사용하여 데이터 흐름 블록에 메시지를 쓰고 데이터 흐름 블록에서 메시지를 읽는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="50a01-103">This article describes how to use the Task Parallel Library (TPL) Dataflow Library to write messages to and read messages from a dataflow block.</span></span> <span data-ttu-id="50a01-104">TPL 데이터 흐름 라이브러리는 데이터 흐름 블록에서 메시지를 쓰고 읽기 위한 동기 메서드와 비동기 메서드를 모두 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="50a01-104">The TPL Dataflow Library provides both synchronous and asynchronous methods for writing messages to and reading messages from a dataflow block.</span></span> <span data-ttu-id="50a01-105">이 문서에서는 <xref:System.Threading.Tasks.Dataflow.BufferBlock%601?displayProperty=nameWithType> 클래스를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="50a01-105">This article shows how to uses the <xref:System.Threading.Tasks.Dataflow.BufferBlock%601?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="50a01-106"><xref:System.Threading.Tasks.Dataflow.BufferBlock%601> 클래스는 메시지를 버퍼링하며, 메시지 소스와 메시지 대상 둘 다로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="50a01-106">The <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> class buffers messages and behaves as both a message source and a message target.</span></span>

[!INCLUDE [tpl-install-instructions](../../../includes/tpl-install-instructions.md)]

## <a name="writing-and-reading-synchronously"></a><span data-ttu-id="50a01-107">동기적으로 쓰기 및 읽기</span><span class="sxs-lookup"><span data-stu-id="50a01-107">Writing and reading synchronously</span></span>

<span data-ttu-id="50a01-108">다음 예제에서는 <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Post%2A> 메서드를 사용하여 <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> 데이터 흐름 블록에 쓰고 <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Receive%2A> 메서드를 사용하여 동일한 개체에서 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="50a01-108">The following example uses the <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Post%2A> method to write to a <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> dataflow block and the <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Receive%2A> method to read from the same object.</span></span>

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs" id="2":::
:::code language="vb" source="../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb" id="2":::

<span data-ttu-id="50a01-109">또한 <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> 메서드를 사용하여 다음 예제와 같이 데이터 흐름 블록에서 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50a01-109">You can also use the <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> method to read from a dataflow block, as shown in the following example.</span></span> <span data-ttu-id="50a01-110"><xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> 메서드는 현재 스레드를 차단하지 않고 때때로 데이터를 폴링할 때 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="50a01-110">The <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> method does not block the current thread and is useful when you occasionally poll for data.</span></span>

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs" id="3":::
:::code language="vb" source="../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb" id="3":::

<span data-ttu-id="50a01-111"><xref:System.Threading.Tasks.Dataflow.DataflowBlock.Post%2A> 메서드가 동기적으로 작동하기 때문에 앞의 예제에 있는 <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> 개체는 두 번째 루프에서 데이터를 읽기 전에 모든 데이터를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="50a01-111">Because the <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Post%2A> method acts synchronously, the <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> object in the previous examples receives all data before the second loop reads data.</span></span> <span data-ttu-id="50a01-112">다음 예제에서는 <xref:System.Threading.Tasks.Task.WhenAll(System.Threading.Tasks.Task[])?displayProperty=nameWithType>를 사용하여 메시지 블록에서 동시에 읽고 쓰는 방법으로 첫 번째 예제를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="50a01-112">The following example extends the first example by using <xref:System.Threading.Tasks.Task.WhenAll(System.Threading.Tasks.Task[])?displayProperty=nameWithType> to read from and write to the message block concurrently.</span></span> <span data-ttu-id="50a01-113"><xref:System.Threading.Tasks.Task.WhenAll%2A>가 작업을 동시에 수행하기 때문에 값은 특정 순서로 <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> 개체에 기록되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="50a01-113">Because <xref:System.Threading.Tasks.Task.WhenAll%2A> performs actions concurrently, the values are not written to the <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> object in any specific order.</span></span>

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs" id="4":::
:::code language="vb" source="../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb" id="4":::

## <a name="writing-and-reading-asynchronously"></a><span data-ttu-id="50a01-114">비동기적으로 쓰기 및 읽기</span><span class="sxs-lookup"><span data-stu-id="50a01-114">Writing and reading asynchronously</span></span>

<span data-ttu-id="50a01-115">다음 예제에서는 <xref:System.Threading.Tasks.Dataflow.DataflowBlock.SendAsync%2A> 메서드를 사용하여 비동기적으로 <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> 개체에 쓰고 <xref:System.Threading.Tasks.Dataflow.DataflowBlock.ReceiveAsync%2A> 메서드를 사용하여 비동기적으로 동일한 개체에서 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="50a01-115">The following example uses the <xref:System.Threading.Tasks.Dataflow.DataflowBlock.SendAsync%2A> method to asynchronously write to a <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> object and the <xref:System.Threading.Tasks.Dataflow.DataflowBlock.ReceiveAsync%2A> method to asynchronously read from the same object.</span></span> <span data-ttu-id="50a01-116">이 예제에서는 [async](../../csharp/language-reference/keywords/async.md) 및 [await](../../csharp/language-reference/operators/await.md)(Visual Basic에서는 [Async](../../visual-basic/language-reference/modifiers/async.md) 및 [Await](../../visual-basic/language-reference/operators/await-operator.md)) 연산자를 사용하여 비동기적으로 대상 블록에 데이터를 보내고 대상 블록에서 데이터를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="50a01-116">This example uses the [async](../../csharp/language-reference/keywords/async.md) and [await](../../csharp/language-reference/operators/await.md) operators ([Async](../../visual-basic/language-reference/modifiers/async.md) and [Await](../../visual-basic/language-reference/operators/await-operator.md) in Visual Basic) to asynchronously send data to and read data from the target block.</span></span> <span data-ttu-id="50a01-117"><xref:System.Threading.Tasks.Dataflow.DataflowBlock.SendAsync%2A> 메서드는 데이터 흐름 블록이 메시지를 연기할 수 있도록 해야 하는 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="50a01-117">The <xref:System.Threading.Tasks.Dataflow.DataflowBlock.SendAsync%2A> method is useful when you must enable a dataflow block to postpone messages.</span></span> <span data-ttu-id="50a01-118"><xref:System.Threading.Tasks.Dataflow.DataflowBlock.ReceiveAsync%2A> 메서드는 데이터를 사용할 수 있게 될 때 데이터에 대한 작업을 수행하려는 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="50a01-118">The <xref:System.Threading.Tasks.Dataflow.DataflowBlock.ReceiveAsync%2A> method is useful when you want to act on data when that data becomes available.</span></span> <span data-ttu-id="50a01-119">메시지가 메시지 블록 간에 전파되는 방법에 대한 자세한 내용은 [데이터 흐름](dataflow-task-parallel-library.md)의 [메시지 전달] 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="50a01-119">For more information about how messages propagate among message blocks, see the section Message Passing in [Dataflow](dataflow-task-parallel-library.md).</span></span>

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs" id="5":::
:::code language="vb" source="../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb" id="5":::

## <a name="a-complete-example"></a><span data-ttu-id="50a01-120">전체 예제</span><span class="sxs-lookup"><span data-stu-id="50a01-120">A complete example</span></span>

<span data-ttu-id="50a01-121">다음 예제에서는 이 문서의 모든 코드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="50a01-121">The following example shows all of the code for this article.</span></span>

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs" id="1":::
:::code language="vb" source="../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb" id="1":::

## <a name="next-steps"></a><span data-ttu-id="50a01-122">다음 단계</span><span class="sxs-lookup"><span data-stu-id="50a01-122">Next steps</span></span>

<span data-ttu-id="50a01-123">이 예제에서는 메시지 블록에서 직접 읽고 쓰는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="50a01-123">This example shows how to read from and write to a message block directly.</span></span> <span data-ttu-id="50a01-124">데이터 흐름 블록을 연결하여 데이터 흐름 블록의 선형 시퀀스인 *파이프라인*이나 데이터 흐름 블록의 그래프인 *네트워크*를 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50a01-124">You can also connect dataflow blocks to form *pipelines*, which are linear sequences of dataflow blocks, or *networks*, which are graphs of dataflow blocks.</span></span> <span data-ttu-id="50a01-125">파이프라인 또는 네트워크에서 소스는 데이터를 사용할 수 있게 되면 대상에 데이터를 비동기적으로 전파합니다.</span><span class="sxs-lookup"><span data-stu-id="50a01-125">In a pipeline or network, sources asynchronously propagate data to targets as that data becomes available.</span></span> <span data-ttu-id="50a01-126">기본 데이터 흐름 파이프라인을 만드는 예제는 [연습: 데이터 흐름 파이프라인 만들기](walkthrough-creating-a-dataflow-pipeline.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="50a01-126">For an example that creates a basic dataflow pipeline, see [Walkthrough: Creating a Dataflow Pipeline](walkthrough-creating-a-dataflow-pipeline.md).</span></span> <span data-ttu-id="50a01-127">더 복잡한 데이터 흐름 네트워크를 만드는 예제는 [연습: Windows Forms 애플리케이션에서 데이터 흐름 사용](walkthrough-using-dataflow-in-a-windows-forms-application.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="50a01-127">For an example that creates a more complex dataflow network, see [Walkthrough: Using Dataflow in a Windows Forms Application](walkthrough-using-dataflow-in-a-windows-forms-application.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="50a01-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="50a01-128">See also</span></span>

- [<span data-ttu-id="50a01-129">데이터 흐름(작업 병렬 라이브러리)</span><span class="sxs-lookup"><span data-stu-id="50a01-129">Dataflow (Task Parallel Library)</span></span>](dataflow-task-parallel-library.md)
