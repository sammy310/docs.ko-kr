---
title: '방법: ShowDialog 메서드를 통해 Windows Form을 표시하여 COM Interop 지원'
ms.date: 03/30/2017
helpviewer_keywords:
- COM [Windows Forms]
- Windows Forms, unmanaged
- COM interop [Windows Forms], calling methods
- ActiveX controls [Windows Forms], COM interop
- Windows Forms, interop
ms.assetid: 87aac8ad-3c04-43b3-9b0c-d0b00df9ee74
ms.openlocfilehash: f2fb48e07243694b14904b240bdcb0739175c2fc
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65593532"
---
# <a name="how-to-support-com-interop-by-displaying-a-windows-form-with-the-showdialog-method"></a><span data-ttu-id="764cc-102">방법: ShowDialog 메서드를 통해 Windows Form을 표시하여 COM Interop 지원</span><span class="sxs-lookup"><span data-stu-id="764cc-102">How to: Support COM Interop by Displaying a Windows Form with the ShowDialog Method</span></span>
<span data-ttu-id="764cc-103">.NET Framework 메시지 루프를 사용 하 여 만들어지는에 Windows 폼을 표시 하 여 구성 요소 개체 모델 (COM) 상호 운용성 문제를 해결할 수 있습니다는 <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType> 메서드.</span><span class="sxs-lookup"><span data-stu-id="764cc-103">You can resolve Component Object Model (COM) interoperability problems by displaying your Windows Form on a .NET Framework message loop, which is created by using the <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="764cc-104">폼이 COM 클라이언트 애플리케이션에서 제대로 작동하게 하려면 Windows Forms 메시지 루프에서 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="764cc-104">To make a form work correctly from a COM client application, you must run it on a Windows Forms message loop.</span></span> <span data-ttu-id="764cc-105">이렇게 하려면 다음 접근 방식 중 하나를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="764cc-105">To do this, use one of the following approaches:</span></span>  
  
- <span data-ttu-id="764cc-106"><xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> 메서드를 사용하여 Windows Form을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="764cc-106">Use the <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> method to display the Windows Form;</span></span>  
  
- <span data-ttu-id="764cc-107">각 Windows Form을 별도 스레드에 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="764cc-107">Display each Windows Form on a separate thread.</span></span> <span data-ttu-id="764cc-108">자세한 내용은 [방법: 각 Windows Form을 별개의 스레드에서 표시 하 여 COM Interop 지원](how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="764cc-108">For more information, see [How to: Support COM Interop by Displaying Each Windows Form on Its Own Thread](how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread.md).</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="764cc-109">프로시저</span><span class="sxs-lookup"><span data-stu-id="764cc-109">Procedure</span></span>  
 <span data-ttu-id="764cc-110">사용 하 여를 <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> 메서드 이므로.NET Framework 메시지 루프에서 폼을 표시 하는 가장 쉬운 방법은 수 모든 방법의 구현 하는 최소 코드가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="764cc-110">Using the <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> method can be the easiest way to display a form on a .NET Framework message loop because, of all the approaches, it requires the least code to implement.</span></span>  
  
 <span data-ttu-id="764cc-111"><xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> 메서드는 관리되지 않는 응용 프로그램의 메시지 루프를 일시 중단하고 폼을 대화 상자로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="764cc-111">The <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> method suspends the unmanaged application's message loop and displays the form as a dialog box.</span></span> <span data-ttu-id="764cc-112">호스트 응용 프로그램의 메시지 루프가 일시 중단 되었기 때문에 <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> 메서드는 폼의 메시지를 처리 하는 새.NET Framework 메시지 루프를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="764cc-112">Because the host application's message loop has been suspended, the <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> method creates a new .NET Framework message loop to process the form's messages.</span></span>  
  
 <span data-ttu-id="764cc-113"><xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> 메서드 사용의 단점은 폼이 모달 대화 상자로 열린다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="764cc-113">The disadvantage of using the <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> method is that the form will be opened as a modal dialog box.</span></span> <span data-ttu-id="764cc-114">즉, Windows Form이 열려 있는 동안에는 호출하는 애플리케이션에서 UI(사용자 인터페이스)가 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="764cc-114">This behavior blocks any user interface (UI) in the calling application while the Windows Form is open.</span></span> <span data-ttu-id="764cc-115">사용자가 폼을 끝내 면.NET Framework 메시지 루프가 닫히고 이전 응용 프로그램의 메시지 루프가 다시 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="764cc-115">When the user exits the form, the .NET Framework message loop closes and the earlier application's message loop starts running again.</span></span>  
  
 <span data-ttu-id="764cc-116">폼을 표시할 메서드를 가지고 있는 클래스 라이브러리를 Windows Forms에서 만든 다음 COM interop에 대한 클래스 라이브러리를 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="764cc-116">You can create a class library in Windows Forms which has a method to show the form, and then build the class library for COM interop.</span></span> <span data-ttu-id="764cc-117">Visual Basic 6.0 또는 MFC(Microsoft Foundation Classes)에서 이 DLL 파일을 사용할 수 있으며, 이러한 환경 중 하나에서 <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> 메서드를 호출하여 폼을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="764cc-117">You can use this DLL file from Visual Basic 6.0 or Microsoft Foundation Classes (MFC), and from either of these environments you can call the <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> method to display the form.</span></span>  
  
#### <a name="to-support-com-interop-by-displaying-a-windows-form-with-the-showdialog-method"></a><span data-ttu-id="764cc-118">ShowDialog 메서드로 Windows Form을 표시하여 COM Interop를 지원하려면</span><span class="sxs-lookup"><span data-stu-id="764cc-118">To support COM interop by displaying a windows form with the ShowDialog method</span></span>  
  
- <span data-ttu-id="764cc-119">에 대 한 모든 호출을 대체 합니다 <xref:System.Windows.Forms.Form.Show%2A?displayProperty=nameWithType> 메서드를 호출 하 여는 <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> .NET Framework 구성 요소에서 메서드.</span><span class="sxs-lookup"><span data-stu-id="764cc-119">Replace all calls to the <xref:System.Windows.Forms.Form.Show%2A?displayProperty=nameWithType> method with calls to the <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> method in your .NET Framework component.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="764cc-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="764cc-120">See also</span></span>

- [<span data-ttu-id="764cc-121">.NET Framework 구성 요소를 COM에 노출</span><span class="sxs-lookup"><span data-stu-id="764cc-121">Exposing .NET Framework Components to COM</span></span>](../../interop/exposing-dotnet-components-to-com.md)
- [<span data-ttu-id="764cc-122">방법: 각 Windows Form을 별개의 스레드에서 표시 하 여 COM Interop 지원</span><span class="sxs-lookup"><span data-stu-id="764cc-122">How to: Support COM Interop by Displaying Each Windows Form on Its Own Thread</span></span>](how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread.md)
- [<span data-ttu-id="764cc-123">Windows Forms 및 관리되지 않는 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="764cc-123">Windows Forms and Unmanaged Applications</span></span>](windows-forms-and-unmanaged-applications.md)
