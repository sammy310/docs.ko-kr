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
# <a name="more-secure-printing-in-windows-forms"></a>Windows Forms의 인쇄 추가 보안
Windows Forms 응용 프로그램에는 인쇄 기능이 포함 되는 경우가 많습니다. .NET Framework는 <xref:System.Drawing.Printing.PrintingPermission> 클래스를 사용 하 여 인쇄 기능 및 연결 된 <xref:System.Drawing.Printing.PrintingPermissionLevel> 열거형 값에 대 한 액세스를 제어 하 여 액세스 수준을 표시 합니다. 기본적으로 인쇄는 로컬 인트라넷 및 인터넷 영역에서 사용 하도록 설정 됩니다. 그러나 액세스 수준은 두 영역에서 모두 제한 됩니다. 응용 프로그램이 인쇄 하거나, 사용자 조작이 필요 하거나, 응용 프로그램에 부여 된 사용 권한 값에 따라 인쇄 될 수 없는지 여부입니다. 기본적으로 로컬 인트라넷 영역에는 <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting> 액세스 권한이 부여 되 고 인트라넷 영역에는 <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting> 액세스 권한이 부여 됩니다.  
  
 다음 표에서는 각 인쇄 권한 수준에서 사용할 수 있는 기능을 보여 줍니다.  
  
|PrintingPermissionLevel|Description|  
|-----------------------------|-----------------|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.AllPrinting>|설치 된 모든 프린터에 대 한 모든 권한을 제공 합니다.|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting>|기본 프린터를 프로그래밍 방식으로 인쇄 하 고 제한 된 인쇄 대화 상자를 통해 보다 안전 하 게 인쇄할 수 있습니다. <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting>은 <xref:System.Drawing.Printing.PrintingPermissionLevel.AllPrinting>의 하위 집합입니다.|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting>|는 제한 된 대화 상자 에서만 인쇄 기능을 제공 합니다. <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting>은 <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting>의 하위 집합입니다.|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.NoPrinting>|프린터에 액세스할 수 없도록 합니다. <xref:System.Drawing.Printing.PrintingPermissionLevel.NoPrinting>은 <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting>의 하위 집합입니다.|  
  
## <a name="see-also"></a>참고 항목

- [Windows Forms의 파일 및 데이터 액세스 추가 보안](more-secure-file-and-data-access-in-windows-forms.md)
- [Windows Forms의 추가 보안 고려 사항](additional-security-considerations-in-windows-forms.md)
- [Windows Forms의 보안 개요](security-in-windows-forms-overview.md)
- [Windows Forms 보안](windows-forms-security.md)
