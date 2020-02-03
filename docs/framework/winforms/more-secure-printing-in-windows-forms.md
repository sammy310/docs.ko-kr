---
title: 더 안전한 인쇄
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, printing
- PrintingPermission class [Windows Forms], Windows Forms security
- printing [Windows Forms], security
- security [Windows Forms], printing
ms.assetid: 48fd36ac-872f-4de0-902a-e52969cd4367
ms.openlocfilehash: 6285b76d01660bfa761ea606421f264bdc0c0af5
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734885"
---
# <a name="more-secure-printing-in-windows-forms"></a><span data-ttu-id="7cd5c-102">Windows Forms의 인쇄 추가 보안</span><span class="sxs-lookup"><span data-stu-id="7cd5c-102">More Secure Printing in Windows Forms</span></span>
<span data-ttu-id="7cd5c-103">Windows Forms 응용 프로그램에는 인쇄 기능이 포함 되는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="7cd5c-103">Windows Forms applications frequently include printing abilities.</span></span> <span data-ttu-id="7cd5c-104">.NET Framework는 <xref:System.Drawing.Printing.PrintingPermission> 클래스를 사용 하 여 인쇄 기능 및 연결 된 <xref:System.Drawing.Printing.PrintingPermissionLevel> 열거형 값에 대 한 액세스를 제어 하 여 액세스 수준을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cd5c-104">The .NET Framework uses the <xref:System.Drawing.Printing.PrintingPermission> class to control access to printing capabilities and the associated <xref:System.Drawing.Printing.PrintingPermissionLevel> enumeration value to indicate the level of access.</span></span> <span data-ttu-id="7cd5c-105">기본적으로 인쇄는 로컬 인트라넷 및 인터넷 영역에서 사용 하도록 설정 됩니다. 그러나 액세스 수준은 두 영역에서 모두 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7cd5c-105">By default, printing is enabled by default in the Local Intranet and Internet zones; however, the level of access is restricted in both zones.</span></span> <span data-ttu-id="7cd5c-106">응용 프로그램이 인쇄 하거나, 사용자 조작이 필요 하거나, 응용 프로그램에 부여 된 사용 권한 값에 따라 인쇄 될 수 없는지 여부입니다.</span><span class="sxs-lookup"><span data-stu-id="7cd5c-106">Whether your application can print, requires user interaction, or cannot print depends upon the permission value granted to the application.</span></span> <span data-ttu-id="7cd5c-107">기본적으로 로컬 인트라넷 영역에는 <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting> 액세스 권한이 부여 되 고 인트라넷 영역에는 <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting> 액세스 권한이 부여 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7cd5c-107">By default, the Local Intranet zone receives <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting> access and the Intranet zone receives <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting> access.</span></span>  
  
 <span data-ttu-id="7cd5c-108">다음 표에서는 각 인쇄 권한 수준에서 사용할 수 있는 기능을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7cd5c-108">The following table shows the functionality available at each printing permission level.</span></span>  
  
|<span data-ttu-id="7cd5c-109">PrintingPermissionLevel</span><span class="sxs-lookup"><span data-stu-id="7cd5c-109">PrintingPermissionLevel</span></span>|<span data-ttu-id="7cd5c-110">Description</span><span class="sxs-lookup"><span data-stu-id="7cd5c-110">Description</span></span>|  
|-----------------------------|-----------------|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.AllPrinting>|<span data-ttu-id="7cd5c-111">설치 된 모든 프린터에 대 한 모든 권한을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cd5c-111">Provides full access to all installed printers.</span></span>|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting>|<span data-ttu-id="7cd5c-112">기본 프린터를 프로그래밍 방식으로 인쇄 하 고 제한 된 인쇄 대화 상자를 통해 보다 안전 하 게 인쇄할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cd5c-112">Enables programmatic printing to the default printer and safer printing through a restrictive printing dialog box.</span></span> <span data-ttu-id="7cd5c-113"><xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting>은 <xref:System.Drawing.Printing.PrintingPermissionLevel.AllPrinting>의 하위 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="7cd5c-113"><xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting> is a subset of <xref:System.Drawing.Printing.PrintingPermissionLevel.AllPrinting>.</span></span>|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting>|<span data-ttu-id="7cd5c-114">는 제한 된 대화 상자 에서만 인쇄 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cd5c-114">Provides printing only from a more-restricted dialog box.</span></span> <span data-ttu-id="7cd5c-115"><xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting>은 <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting>의 하위 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="7cd5c-115"><xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting> is a subset of <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting>.</span></span>|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.NoPrinting>|<span data-ttu-id="7cd5c-116">프린터에 액세스할 수 없도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cd5c-116">Prevents access to printers.</span></span> <span data-ttu-id="7cd5c-117"><xref:System.Drawing.Printing.PrintingPermissionLevel.NoPrinting>은 <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting>의 하위 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="7cd5c-117"><xref:System.Drawing.Printing.PrintingPermissionLevel.NoPrinting> is a subset of <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting>.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7cd5c-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7cd5c-118">See also</span></span>

- [<span data-ttu-id="7cd5c-119">Windows Forms의 파일 및 데이터 액세스 추가 보안</span><span class="sxs-lookup"><span data-stu-id="7cd5c-119">More Secure File and Data Access in Windows Forms</span></span>](more-secure-file-and-data-access-in-windows-forms.md)
- [<span data-ttu-id="7cd5c-120">Windows Forms의 추가 보안 고려 사항</span><span class="sxs-lookup"><span data-stu-id="7cd5c-120">Additional Security Considerations in Windows Forms</span></span>](additional-security-considerations-in-windows-forms.md)
- [<span data-ttu-id="7cd5c-121">Windows Forms의 보안 개요</span><span class="sxs-lookup"><span data-stu-id="7cd5c-121">Security in Windows Forms Overview</span></span>](security-in-windows-forms-overview.md)
- [<span data-ttu-id="7cd5c-122">Windows Forms 보안</span><span class="sxs-lookup"><span data-stu-id="7cd5c-122">Windows Forms Security</span></span>](windows-forms-security.md)
