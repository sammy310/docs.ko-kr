---
title: 컨트롤의 다중 스레딩
ms.date: 03/30/2017
helpviewer_keywords:
- BackgroundWorker component
- threading [Windows Forms], controls
ms.assetid: c311d652-0f26-45fa-bdcc-b1615d73ce4e
ms.openlocfilehash: 79832e12a10f02c909d2a28270594bcb4ea68656
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742136"
---
# <a name="multithreading-in-windows-forms-controls"></a><span data-ttu-id="ae705-102">Windows Forms 컨트롤의 다중 스레딩</span><span class="sxs-lookup"><span data-stu-id="ae705-102">Multithreading in Windows Forms Controls</span></span>
<span data-ttu-id="ae705-103">많은 응용 프로그램에서 다른 스레드에서 시간이 많이 걸리는 작업을 수행 하 여 UI (사용자 인터페이스)의 응답성을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae705-103">In many applications, you can make your user interface (UI) more responsive by performing time-consuming operations on another thread.</span></span> <span data-ttu-id="ae705-104"><xref:System.Threading> 네임 스페이스, <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> 메서드 및 `BackgroundWorker` 구성 요소를 포함 하 여 Windows Forms 컨트롤의 다중 스레딩에 다양 한 도구를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae705-104">A number of tools are available for multithreading your Windows Forms controls, including the <xref:System.Threading> namespace, the <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> method, and the `BackgroundWorker` component.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ae705-105">`BackgroundWorker` 구성 요소는 기능을 대체 하 고 <xref:System.Threading> 네임 스페이스 및 <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> 메서드를 추가 합니다. 그러나 이러한 기능은 이전 버전과의 호환성 및 향후 사용을 위해 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae705-105">The `BackgroundWorker` component replaces and adds functionality to the <xref:System.Threading> namespace and the <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> method; however, these are retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="ae705-106">자세한 내용은 [BackgroundWorker 구성 요소 개요](backgroundworker-component-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ae705-106">For more information, see [BackgroundWorker Component Overview](backgroundworker-component-overview.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ae705-107">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="ae705-107">In This Section</span></span>  
 [<span data-ttu-id="ae705-108">방법: 스레드로부터 안전한 방식으로 Windows Forms 컨트롤 호출</span><span class="sxs-lookup"><span data-stu-id="ae705-108">How to: Make Thread-Safe Calls to Windows Forms Controls</span></span>](how-to-make-thread-safe-calls-to-windows-forms-controls.md)  
 <span data-ttu-id="ae705-109">Windows Forms 컨트롤을 스레드로부터 안전 하 게 호출 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ae705-109">Shows how to make thread-safe calls to Windows Forms controls.</span></span>  
  
 [<span data-ttu-id="ae705-110">방법: 백그라운드 스레드를 사용하여 파일 검색</span><span class="sxs-lookup"><span data-stu-id="ae705-110">How to: Use a Background Thread to Search for Files</span></span>](how-to-use-a-background-thread-to-search-for-files.md)  
 <span data-ttu-id="ae705-111"><xref:System.Threading> 네임 스페이스 및 <xref:System.Windows.Forms.Control.BeginInvoke%2A> 메서드를 사용 하 여 파일을 비동기적으로 검색 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ae705-111">Shows how to use the <xref:System.Threading> namespace and the <xref:System.Windows.Forms.Control.BeginInvoke%2A> method to search for files asynchronously.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="ae705-112">참조</span><span class="sxs-lookup"><span data-stu-id="ae705-112">Reference</span></span>  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="ae705-113">비동기 작업에 대 한 작업자 스레드를 캡슐화 하는 구성 요소를 문서화 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae705-113">Documents a component that encapsulates a worker thread for asynchronous operations.</span></span>  
  
 <xref:System.Media.SoundPlayer.LoadAsync%2A>  
 <span data-ttu-id="ae705-114">소리를 비동기적으로 로드 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae705-114">Documents how to load a sound asynchronously.</span></span>  
  
 <xref:System.Windows.Forms.PictureBox.LoadAsync%2A>  
 <span data-ttu-id="ae705-115">이미지를 비동기적으로 로드 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae705-115">Documents how to load an image asynchronously.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="ae705-116">관련 섹션</span><span class="sxs-lookup"><span data-stu-id="ae705-116">Related Sections</span></span>  
 [<span data-ttu-id="ae705-117">방법: 백그라운드에서 작업 실행</span><span class="sxs-lookup"><span data-stu-id="ae705-117">How to: Run an Operation in the Background</span></span>](how-to-run-an-operation-in-the-background.md)  
 <span data-ttu-id="ae705-118"><xref:System.ComponentModel.BackgroundWorker> 구성 요소를 사용 하 여 시간이 오래 걸리는 작업을 수행 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ae705-118">Shows how to perform a time-consuming operation with the <xref:System.ComponentModel.BackgroundWorker> component.</span></span>  
  
 [<span data-ttu-id="ae705-119">BackgroundWorker 구성 요소 개요</span><span class="sxs-lookup"><span data-stu-id="ae705-119">BackgroundWorker Component Overview</span></span>](backgroundworker-component-overview.md)  
 <span data-ttu-id="ae705-120">비동기 작업에 <xref:System.ComponentModel.BackgroundWorker> 구성 요소를 사용 하는 방법을 설명 하는 항목을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae705-120">Provides topics that describe how to use the <xref:System.ComponentModel.BackgroundWorker> component for asynchronous operations.</span></span>
