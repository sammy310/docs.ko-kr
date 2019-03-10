---
title: Windows Forms 컨트롤의 다중 스레딩
ms.date: 03/30/2017
helpviewer_keywords:
- BackgroundWorker component
- threading [Windows Forms], controls
ms.assetid: c311d652-0f26-45fa-bdcc-b1615d73ce4e
ms.openlocfilehash: cc7f358a62c8057abb77e1f5a28544bb6c858d98
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57703324"
---
# <a name="multithreading-in-windows-forms-controls"></a><span data-ttu-id="7ce1d-102">Windows Forms 컨트롤의 다중 스레딩</span><span class="sxs-lookup"><span data-stu-id="7ce1d-102">Multithreading in Windows Forms Controls</span></span>
<span data-ttu-id="7ce1d-103">많은 응용 프로그램에서 가능 사용자 인터페이스 (UI) 응답성 다른 스레드에서 시간이 많이 걸리는 작업을 수행 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ce1d-103">In many applications, you can make your user interface (UI) more responsive by performing time-consuming operations on another thread.</span></span> <span data-ttu-id="7ce1d-104">다양 한 도구를 사용할 수 있습니다 다중 스레딩을 비롯 하 여 Windows Forms 컨트롤을 <xref:System.Threading> 네임 스페이스를 <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> 메서드를 및 `BackgroundWorker` 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="7ce1d-104">A number of tools are available for multithreading your Windows Forms controls, including the <xref:System.Threading> namespace, the <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> method, and the `BackgroundWorker` component.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7ce1d-105">그러나 합니다 `BackgroundWorker` 대체 하 고 기능을 추가 하는 구성 요소를 <xref:System.Threading> 네임 스페이스 및 <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> 메서드이 보존 이전 버전과 호환성 및 향후 사용을 위해 선택한 경우.</span><span class="sxs-lookup"><span data-stu-id="7ce1d-105">The `BackgroundWorker` component replaces and adds functionality to the <xref:System.Threading> namespace and the <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> method; however, these are retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="7ce1d-106">자세한 내용은 [BackgroundWorker 구성 요소 개요](backgroundworker-component-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7ce1d-106">For more information, see [BackgroundWorker Component Overview](backgroundworker-component-overview.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7ce1d-107">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="7ce1d-107">In This Section</span></span>  
 [<span data-ttu-id="7ce1d-108">방법: 스레드로부터 안전한 Windows Forms 컨트롤 호출</span><span class="sxs-lookup"><span data-stu-id="7ce1d-108">How to: Make Thread-Safe Calls to Windows Forms Controls</span></span>](how-to-make-thread-safe-calls-to-windows-forms-controls.md)  
 <span data-ttu-id="7ce1d-109">Windows Forms 컨트롤에 스레드로부터 안전한 호출을 수행 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7ce1d-109">Shows how to make thread-safe calls to Windows Forms controls.</span></span>  
  
 [<span data-ttu-id="7ce1d-110">방법: 파일을 검색 하는 백그라운드 스레드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ce1d-110">How to: Use a Background Thread to Search for Files</span></span>](how-to-use-a-background-thread-to-search-for-files.md)  
 <span data-ttu-id="7ce1d-111">사용 하는 방법을 보여 줍니다 합니다 <xref:System.Threading> 네임 스페이스 및 <xref:System.Windows.Forms.Control.BeginInvoke%2A> 메서드를 비동기적으로 파일을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ce1d-111">Shows how to use the <xref:System.Threading> namespace and the <xref:System.Windows.Forms.Control.BeginInvoke%2A> method to search for files asynchronously.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="7ce1d-112">참조</span><span class="sxs-lookup"><span data-stu-id="7ce1d-112">Reference</span></span>  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="7ce1d-113">비동기 작업에 대 한 작업자 스레드를 캡슐화 하는 구성 요소를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ce1d-113">Documents a component that encapsulates a worker thread for asynchronous operations.</span></span>  
  
 <xref:System.Media.SoundPlayer.LoadAsync%2A>  
 <span data-ttu-id="7ce1d-114">소리를 비동기적으로 로드 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ce1d-114">Documents how to load a sound asynchronously.</span></span>  
  
 <xref:System.Windows.Forms.PictureBox.LoadAsync%2A>  
 <span data-ttu-id="7ce1d-115">이미지를 비동기적으로 로드 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ce1d-115">Documents how to load an image asynchronously.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="7ce1d-116">관련 단원</span><span class="sxs-lookup"><span data-stu-id="7ce1d-116">Related Sections</span></span>  
 [<span data-ttu-id="7ce1d-117">방법: 백그라운드에서 작업 실행</span><span class="sxs-lookup"><span data-stu-id="7ce1d-117">How to: Run an Operation in the Background</span></span>](how-to-run-an-operation-in-the-background.md)  
 <span data-ttu-id="7ce1d-118">사용 하 여 시간이 오래 걸리는 작업을 수행 하는 방법을 보여 줍니다는 <xref:System.ComponentModel.BackgroundWorker> 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="7ce1d-118">Shows how to perform a time-consuming operation with the <xref:System.ComponentModel.BackgroundWorker> component.</span></span>  
  
 [<span data-ttu-id="7ce1d-119">BackgroundWorker 구성 요소 개요</span><span class="sxs-lookup"><span data-stu-id="7ce1d-119">BackgroundWorker Component Overview</span></span>](backgroundworker-component-overview.md)  
 <span data-ttu-id="7ce1d-120">사용 하는 방법을 설명 하는 항목을 제공 합니다 <xref:System.ComponentModel.BackgroundWorker> 비동기 작업에 대 한 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="7ce1d-120">Provides topics that describe how to use the <xref:System.ComponentModel.BackgroundWorker> component for asynchronous operations.</span></span>
