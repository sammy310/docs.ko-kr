---
ms.openlocfilehash: 9d09f598538b9d5ee3f995d6281b8eb4b2668050
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/11/2019
ms.locfileid: "67802499"
---
### <a name="objectdisposedexception-thrown-by-wpf-spellchecker"></a><span data-ttu-id="a110b-101">WPF 맞춤법 검사기에 의해 throw된 ObjectDisposedException</span><span class="sxs-lookup"><span data-stu-id="a110b-101">ObjectDisposedException thrown by WPF spellchecker</span></span>

|   |   |
|---|---|
|<span data-ttu-id="a110b-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="a110b-102">Details</span></span>|<span data-ttu-id="a110b-103">WPF 애플리케이션은 애플리케이션 종료 중에 맞춤법 검사기에서 throw된 <xref:System.ObjectDisposedException?displayProperty=name>으로 인해 때때로 크래시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a110b-103">WPF applications occasionally crash during application shutdown with an <xref:System.ObjectDisposedException?displayProperty=name> thrown by the spellchecker.</span></span> <span data-ttu-id="a110b-104">이는 .NET Framework 4.7 WPF에서 예외를 제대로 처리하여 애플리케이션이 더 이상 부정적인 영향을 받지 않도록 함으로써 해결되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a110b-104">This is fixed in .NET Framework 4.7 WPF by handling the exception gracefully, and thus ensuring that applications are no longer adversely affected.</span></span> <span data-ttu-id="a110b-105">디버거에서 실행 중인 애플리케이션에서는 경우에 따라 첫째 예외만 계속 확인될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a110b-105">It should be noted that occasional first-chance exceptions would continue to be observed in applications running under a debugger.</span></span>|
|<span data-ttu-id="a110b-106">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="a110b-106">Suggestion</span></span>|<span data-ttu-id="a110b-107">NET Framework 4.7로 업그레이드</span><span class="sxs-lookup"><span data-stu-id="a110b-107">Upgrade to .NET Framework 4.7</span></span>|
|<span data-ttu-id="a110b-108">범위</span><span class="sxs-lookup"><span data-stu-id="a110b-108">Scope</span></span>|<span data-ttu-id="a110b-109">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="a110b-109">Edge</span></span>|
|<span data-ttu-id="a110b-110">버전</span><span class="sxs-lookup"><span data-stu-id="a110b-110">Version</span></span>|<span data-ttu-id="a110b-111">4.6.1</span><span class="sxs-lookup"><span data-stu-id="a110b-111">4.6.1</span></span>|
|<span data-ttu-id="a110b-112">형식</span><span class="sxs-lookup"><span data-stu-id="a110b-112">Type</span></span>|<span data-ttu-id="a110b-113">런타임</span><span class="sxs-lookup"><span data-stu-id="a110b-113">Runtime</span></span>|

