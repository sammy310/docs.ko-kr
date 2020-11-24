---
title: '방법: 미리 계산된 작업 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, creating pre-computed
ms.assetid: a73eafa2-1f49-4106-a19e-997186029b58
ms.openlocfilehash: 3f2a47d2f9ba8870ff3598c5bc73b54588039702
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2020
ms.locfileid: "94825769"
---
# <a name="how-to-create-pre-computed-tasks"></a><span data-ttu-id="792f8-102">방법: 미리 계산된 작업 만들기</span><span class="sxs-lookup"><span data-stu-id="792f8-102">How to: Create Pre-Computed Tasks</span></span>
<span data-ttu-id="792f8-103">이 문서에서는 <xref:System.Threading.Tasks.Task.FromResult%2A?displayProperty=nameWithType> 메서드를 사용하여 캐시에 저장된 비동기 다운로드 작업의 결과를 검색하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="792f8-103">This document describes how to use the <xref:System.Threading.Tasks.Task.FromResult%2A?displayProperty=nameWithType> method to retrieve the results of asynchronous download operations that are held in a cache.</span></span> <span data-ttu-id="792f8-104"><xref:System.Threading.Tasks.Task.FromResult%2A> 메서드는 제공된 값을 <xref:System.Threading.Tasks.Task%601> 속성으로 포함하는 완료된 <xref:System.Threading.Tasks.Task%601.Result%2A> 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="792f8-104">The <xref:System.Threading.Tasks.Task.FromResult%2A> method returns a finished <xref:System.Threading.Tasks.Task%601> object that holds the provided value as its <xref:System.Threading.Tasks.Task%601.Result%2A> property.</span></span> <span data-ttu-id="792f8-105">이 메서드는 <xref:System.Threading.Tasks.Task%601> 개체가 반환되는 비동기 작업을 수행하고 해당 <xref:System.Threading.Tasks.Task%601> 개체의 결과가 계산되어 있을 때 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="792f8-105">This method is useful when you perform an asynchronous operation that returns a <xref:System.Threading.Tasks.Task%601> object, and the result of that <xref:System.Threading.Tasks.Task%601> object is already computed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="792f8-106">예제</span><span class="sxs-lookup"><span data-stu-id="792f8-106">Example</span></span>  
 <span data-ttu-id="792f8-107">다음 예제에서는 웹에서 문자열을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="792f8-107">The following example downloads strings from the web.</span></span> <span data-ttu-id="792f8-108">이 예제에서는 `DownloadStringAsync` 메서드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="792f8-108">It defines the `DownloadStringAsync` method.</span></span> <span data-ttu-id="792f8-109">이 메서드는 웹에서 문자열을 비동기적으로 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="792f8-109">This method downloads strings from the web asynchronously.</span></span> <span data-ttu-id="792f8-110">또한 이 예제에서는 <xref:System.Collections.Concurrent.ConcurrentDictionary%602>개체를 사용하여 이전 작업의 결과를 캐시합니다.</span><span class="sxs-lookup"><span data-stu-id="792f8-110">This example also uses a <xref:System.Collections.Concurrent.ConcurrentDictionary%602> object to cache the results of previous operations.</span></span> <span data-ttu-id="792f8-111">입력 주소가 이 캐시에 저장된 경우 `DownloadStringAsync`는 <xref:System.Threading.Tasks.Task.FromResult%2A> 메서드를 사용하여 해당 주소의 콘텐츠를 포함하는 <xref:System.Threading.Tasks.Task%601> 개체를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="792f8-111">If the input address is held in this cache, `DownloadStringAsync` uses the <xref:System.Threading.Tasks.Task.FromResult%2A> method to produce a <xref:System.Threading.Tasks.Task%601> object that holds the content at that address.</span></span> <span data-ttu-id="792f8-112">그렇지 않은 경우에는 `DownloadStringAsync`가 웹에서 파일을 다운로드하고 결과를 캐시에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="792f8-112">Otherwise, `DownloadStringAsync` downloads the file from the web and adds the result to the cache.</span></span>  
  
 [!code-csharp[TPL_CachedDownloads#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_cacheddownloads/cs/cacheddownloads.cs#1)]
 [!code-vb[TPL_CachedDownloads#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_cacheddownloads/vb/cacheddownloads.vb#1)]  
  
 <span data-ttu-id="792f8-113">이 예제에서는 여러 문자열을 두 번 다운로드하는 데 필요한 시간을 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="792f8-113">This example computes the time that is required to download multiple strings two times.</span></span> <span data-ttu-id="792f8-114">결과가 캐시에 저장되기 때문에 다운로드 작업의 두 번째 집합은 첫 번째 집합보다 시간이 덜 걸려야 합니다.</span><span class="sxs-lookup"><span data-stu-id="792f8-114">The second set of download operations should take less time than the first set because the results are held in the cache.</span></span> <span data-ttu-id="792f8-115"><xref:System.Threading.Tasks.Task.FromResult%2A> 메서드는 `DownloadStringAsync` 메서드가 이러한 미리 계산된 결과를 포함하는 <xref:System.Threading.Tasks.Task%601> 개체를 만들 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="792f8-115">The <xref:System.Threading.Tasks.Task.FromResult%2A> method enables the `DownloadStringAsync` method to create <xref:System.Threading.Tasks.Task%601> objects that hold these pre-computed results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="792f8-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="792f8-116">See also</span></span>

- [<span data-ttu-id="792f8-117">작업 기반 비동기 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="792f8-117">Task-based Asynchronous Programming</span></span>](task-based-asynchronous-programming.md)
