---
title: '방법: PLINQ를 사용하여 파일 디렉터리 반복'
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- PLINQ queries, how to iterate directories
ms.assetid: 354e8ce3-35c4-431c-99ca-7661d1f3901b
ms.openlocfilehash: 5033cc24fce5fc17a950e4797de1ef4071e2b98a
ms.sourcegitcommit: 6d09ae36acba0b0e2ba47999f8f1a725795462a2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92925378"
---
# <a name="how-to-iterate-file-directories-with-plinq"></a><span data-ttu-id="eca56-102">방법: PLINQ를 사용하여 파일 디렉터리 반복</span><span class="sxs-lookup"><span data-stu-id="eca56-102">How to: Iterate File Directories with PLINQ</span></span>

<span data-ttu-id="eca56-103">이 문서에서는 파일 디렉터리에서 작업을 병렬 처리하는 두 가지 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="eca56-103">This article shows two ways to parallelize operations on file directories.</span></span> <span data-ttu-id="eca56-104">첫 번째 쿼리는 <xref:System.IO.Directory.GetFiles%2A> 메서드를 사용하여 디렉터리 및 모든 하위 디렉터리에서 파일 이름 배열을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="eca56-104">The first query uses the <xref:System.IO.Directory.GetFiles%2A> method to populate an array of file names in a directory and all subdirectories.</span></span> <span data-ttu-id="eca56-105">이 메서드는 전체 배열이 채워질 때까지 반환되지 않으므로 작업 시작 시 대기 시간이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eca56-105">This method can introduce latency at the beginning of the operation, because it doesn't return until the entire array is populated.</span></span> <span data-ttu-id="eca56-106">그러나 배열이 채워진 후 PLINQ는 메서드를 빠르게 병렬 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eca56-106">However, after the array is populated, PLINQ can process it in parallel quickly.</span></span>  
  
<span data-ttu-id="eca56-107">두 번째 쿼리는 결과를 즉시 반환하기 시작하는 정적 <xref:System.IO.Directory.EnumerateDirectories%2A> 및 <xref:System.IO.DirectoryInfo.EnumerateFiles%2A> 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="eca56-107">The second query uses the static <xref:System.IO.Directory.EnumerateDirectories%2A> and <xref:System.IO.DirectoryInfo.EnumerateFiles%2A> methods, which begin returning results immediately.</span></span> <span data-ttu-id="eca56-108">큰 디렉터리 트리를 반복 중일 경우 이 방법이 더 빠를 수 있지만, 처리 시간은 첫 번째 예제와 비교하여 많은 요소에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="eca56-108">This approach can be faster when you're iterating over large directory trees, but the processing time compared to the first example depends on many factors.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="eca56-109">이 예제는 사용법을 보여 주기 위해 제공되며 동일한 순차적 LINQ to Objects 쿼리보다 빠르게 실행되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eca56-109">These examples are intended to demonstrate usage and might not run faster than the equivalent sequential LINQ to Objects query.</span></span> <span data-ttu-id="eca56-110">속도 향상에 대한 자세한 내용은 [PLINQ의 속도 향상 이해](understanding-speedup-in-plinq.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="eca56-110">For more information about speedup, see [Understanding Speedup in PLINQ](understanding-speedup-in-plinq.md).</span></span>  
  
## <a name="getfiles-example"></a><span data-ttu-id="eca56-111">GetFiles 예제</span><span class="sxs-lookup"><span data-stu-id="eca56-111">GetFiles example</span></span>

 <span data-ttu-id="eca56-112">다음 예제에서는 트리의 모든 디렉터리에 액세스할 수 있고, 파일 크기가 크지 않으며, 액세스 시간이 길지 않을 경우 파일 디렉터리를 반복하는 방법을 간단한 시나리오로 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="eca56-112">This example shows how to iterate over file directories in simple scenarios when you have access to all directories in the tree, the file sizes aren't large, and the access times are not significant.</span></span> <span data-ttu-id="eca56-113">이 방법에는 파일 이름 배열이 생성되는 동안 시작 시에 대기 시간이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="eca56-113">This approach involves a period of latency at the beginning while the array of file names is being constructed.</span></span>  
  
 [!code-csharp[PLINQ#33](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqfileiteration.cs#33)]  
  
## <a name="enumeratefiles-example"></a><span data-ttu-id="eca56-114">EnumerateFiles 예제</span><span class="sxs-lookup"><span data-stu-id="eca56-114">EnumerateFiles example</span></span>

 <span data-ttu-id="eca56-115">다음 예제에서는 트리의 모든 디렉터리에 액세스할 수 있고, 파일 크기가 크지 않으며, 액세스 시간이 길지 않을 경우 파일 디렉터리를 반복하는 방법을 간단한 시나리오로 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="eca56-115">This example shows how to iterate over file directories in simple scenarios when you have access to all directories in the tree, the file sizes aren't large, and the access times are not significant.</span></span> <span data-ttu-id="eca56-116">이 방법은 이전 예제보다 빠르게 결과를 생성하기 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="eca56-116">This approach begins producing results faster than the previous example.</span></span>  
  
 [!code-csharp[PLINQ#34](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqfileiteration.cs#34)]  
  
 <span data-ttu-id="eca56-117"><xref:System.IO.Directory.GetFiles%2A>를 사용할 경우 트리의 모든 디렉터리에 충분한 권한이 있는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="eca56-117">When using <xref:System.IO.Directory.GetFiles%2A>, be sure that you have sufficient permissions on all directories in the tree.</span></span> <span data-ttu-id="eca56-118">그렇지 않으면 예외가 throw되고 결과가 반환되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="eca56-118">Otherwise, an exception will be thrown and no results will be returned.</span></span> <span data-ttu-id="eca56-119">PLINQ 쿼리에서 <xref:System.IO.Directory.EnumerateDirectories%2A>를 사용할 경우 반복을 계속할 수 있는 정상적인 방법으로 I/O 예외를 처리하는 것이 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="eca56-119">When using the <xref:System.IO.Directory.EnumerateDirectories%2A> in a PLINQ query, it is problematic to handle I/O exceptions in a graceful way that enables you to continue iterating.</span></span> <span data-ttu-id="eca56-120">코드에서 I/O 또는 인증되지 않은 액세스 예외를 처리해야 하는 경우에는 [방법: 병렬 클래스를 사용하여 파일 디렉터리 반복](how-to-iterate-file-directories-with-the-parallel-class.md)에 설명된 방법을 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eca56-120">If your code must handle I/O or unauthorized access exceptions, then you should consider the approach described in [How to: Iterate File Directories with the Parallel Class](how-to-iterate-file-directories-with-the-parallel-class.md).</span></span>  
  
 <span data-ttu-id="eca56-121">예를 들어 I/O 지연이 네트워크를 통한 파일 I/O와 관련된 문제인 경우 [TPL 및 일반적인 .NET 비동기 프로그래밍](tpl-and-traditional-async-programming.md) 및 이 [블로그 게시물](https://devblogs.microsoft.com/pfxteam/parallel-extensions-and-io/)에 설명된 비동기 I/O 기법 중 하나를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="eca56-121">If I/O latency is an issue, for example with file I/O over a network, consider using one of the asynchronous I/O techniques described in [TPL and Traditional .NET Asynchronous Programming](tpl-and-traditional-async-programming.md) and in this [blog post](https://devblogs.microsoft.com/pfxteam/parallel-extensions-and-io/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eca56-122">참조</span><span class="sxs-lookup"><span data-stu-id="eca56-122">See also</span></span>

- [<span data-ttu-id="eca56-123">PLINQ(병렬 LINQ)</span><span class="sxs-lookup"><span data-stu-id="eca56-123">Parallel LINQ (PLINQ)</span></span>](introduction-to-plinq.md)
