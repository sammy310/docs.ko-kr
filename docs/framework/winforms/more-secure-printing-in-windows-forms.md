---
title: Windows Forms의 인쇄 추가 보안
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, printing
- PrintingPermission class [Windows Forms], Windows Forms security
- printing [Windows Forms], security
- security [Windows Forms], printing
ms.assetid: 48fd36ac-872f-4de0-902a-e52969cd4367
ms.openlocfilehash: 5ee170980ed02d90606c774e2a7055f047292e33
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59197362"
---
# <a name="more-secure-printing-in-windows-forms"></a><span data-ttu-id="0b656-102">Windows Forms의 인쇄 추가 보안</span><span class="sxs-lookup"><span data-stu-id="0b656-102">More Secure Printing in Windows Forms</span></span>
<span data-ttu-id="0b656-103">Windows Forms 응용 프로그램에 인쇄 기능이 포함 되는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="0b656-103">Windows Forms applications frequently include printing abilities.</span></span> <span data-ttu-id="0b656-104">[!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] 사용 하는 <xref:System.Drawing.Printing.PrintingPermission> 인쇄 기능에 대 한 액세스 제어 및 관련 클래스 <xref:System.Drawing.Printing.PrintingPermissionLevel> 액세스 수준을 나타내는 열거형 값입니다.</span><span class="sxs-lookup"><span data-stu-id="0b656-104">The [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] uses the <xref:System.Drawing.Printing.PrintingPermission> class to control access to printing capabilities and the associated <xref:System.Drawing.Printing.PrintingPermissionLevel> enumeration value to indicate the level of access.</span></span> <span data-ttu-id="0b656-105">기본적으로 인쇄 로컬 인트라넷 및 인터넷 영역;에 기본적으로 사용 하도록 설정 그러나 두 영역에 대 한 액세스 수준이 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b656-105">By default, printing is enabled by default in the Local Intranet and Internet zones; however, the level of access is restricted in both zones.</span></span> <span data-ttu-id="0b656-106">사용자 상호 작용이 필요한 응용 프로그램 인쇄할 수 있는지 또는 수 없습니다. 응용 프로그램에 부여 된 사용 권한 값에 따라 달라 집니다 인쇄 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b656-106">Whether your application can print, requires user interaction, or cannot print depends upon the permission value granted to the application.</span></span> <span data-ttu-id="0b656-107">기본적으로 로컬 인트라넷 영역 받게 <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting> 권한과 인트라넷 영역 수신 <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting> 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b656-107">By default, the Local Intranet zone receives <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting> access and the Intranet zone receives <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting> access.</span></span>  
  
 <span data-ttu-id="0b656-108">다음 표에서 각 인쇄 권한 수준에서 사용할 수 있는 기능을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0b656-108">The following table shows the functionality available at each printing permission level.</span></span>  
  
|<span data-ttu-id="0b656-109">PrintingPermissionLevel</span><span class="sxs-lookup"><span data-stu-id="0b656-109">PrintingPermissionLevel</span></span>|<span data-ttu-id="0b656-110">설명</span><span class="sxs-lookup"><span data-stu-id="0b656-110">Description</span></span>|  
|-----------------------------|-----------------|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.AllPrinting>|<span data-ttu-id="0b656-111">설치 된 모든 프린터에 대 한 전체 액세스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0b656-111">Provides full access to all installed printers.</span></span>|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting>|<span data-ttu-id="0b656-112">기본 프린터를 프로그래밍 방식 인쇄 및 인쇄 제한적인 대화 상자를 통해 안전 하 게 인쇄할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b656-112">Enables programmatic printing to the default printer and safer printing through a restrictive printing dialog box.</span></span> <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting> <span data-ttu-id="0b656-113">하위 집합인 <xref:System.Drawing.Printing.PrintingPermissionLevel.AllPrinting>합니다.</span><span class="sxs-lookup"><span data-stu-id="0b656-113">is a subset of <xref:System.Drawing.Printing.PrintingPermissionLevel.AllPrinting>.</span></span>|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting>|<span data-ttu-id="0b656-114">보다 제한 된 대화 상자 에서만에서 인쇄를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0b656-114">Provides printing only from a more-restricted dialog box.</span></span> <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting> <span data-ttu-id="0b656-115">하위 집합인 <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting>합니다.</span><span class="sxs-lookup"><span data-stu-id="0b656-115">is a subset of <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting>.</span></span>|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.NoPrinting>|<span data-ttu-id="0b656-116">프린터에 대 한 액세스를 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="0b656-116">Prevents access to printers.</span></span> <xref:System.Drawing.Printing.PrintingPermissionLevel.NoPrinting> <span data-ttu-id="0b656-117">하위 집합인 <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting>합니다.</span><span class="sxs-lookup"><span data-stu-id="0b656-117">is a subset of <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting>.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0b656-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="0b656-118">See also</span></span>

- [<span data-ttu-id="0b656-119">Windows Forms의 파일 및 데이터 액세스 추가 보안</span><span class="sxs-lookup"><span data-stu-id="0b656-119">More Secure File and Data Access in Windows Forms</span></span>](more-secure-file-and-data-access-in-windows-forms.md)
- [<span data-ttu-id="0b656-120">Windows Forms의 추가 보안 고려 사항</span><span class="sxs-lookup"><span data-stu-id="0b656-120">Additional Security Considerations in Windows Forms</span></span>](additional-security-considerations-in-windows-forms.md)
- [<span data-ttu-id="0b656-121">Windows Forms의 보안 개요</span><span class="sxs-lookup"><span data-stu-id="0b656-121">Security in Windows Forms Overview</span></span>](security-in-windows-forms-overview.md)
- [<span data-ttu-id="0b656-122">Windows Forms 보안</span><span class="sxs-lookup"><span data-stu-id="0b656-122">Windows Forms Security</span></span>](windows-forms-security.md)
