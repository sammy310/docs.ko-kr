---
title: 시스템 정보
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- domain names [Windows Forms], retrieving
- SystemInformation class [Windows Forms]
- user names [Windows Forms], retrieving
- system information [Windows Forms]
ms.assetid: 30cf43a3-8cb2-4ff3-862b-6c34576616a8
ms.openlocfilehash: a91e2fd8db0ef338ce30f89f11869f1b6698af3b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732585"
---
# <a name="system-information-and-windows-forms"></a>시스템 정보 및 Windows Forms
코드에서 결정을 내리기 위해 응용 프로그램이 실행 되는 컴퓨터에 대 한 정보를 수집 해야 하는 경우도 있습니다. 예를 들어 특정 네트워크 도메인에 연결 된 경우에만 적용 되는 함수를 사용할 수 있습니다. 이 경우 도메인을 확인 하 고 도메인이 없는 경우 함수를 사용 하지 않도록 설정 하는 방법이 필요 합니다.  
  
 Windows Forms 응용 프로그램은 <xref:System.Windows.Forms.SystemInformation> 클래스를 사용 하 여 런타임에 컴퓨터에 대 한 여러 가지 항목을 결정할 수 있습니다. 다음 예제에서는 <xref:System.Windows.Forms.SystemInformation> 클래스를 사용 하 여 <xref:System.Windows.Forms.SystemInformation.UserName%2A>를 검색 하 고 <xref:System.Windows.Forms.SystemInformation.UserDomainName%2A>하는 방법을 보여 줍니다.  
  
```vb  
Dim User As String = Windows.Forms.SystemInformation.UserName  
Dim Domain As String = Windows.Forms.SystemInformation.UserDomainName  
  
MessageBox.Show("Good morning " & User & ". You are connected to " _  
& Domain)  
```  
  
```csharp  
string User = SystemInformation.UserName;  
string Domain = SystemInformation.UserDomainName;  
  
MessageBox.Show("Good morning " + User + ". You are connected to "
+ Domain);
```  
  
 <xref:System.Windows.Forms.SystemInformation> 클래스의 모든 멤버는 읽기 전용입니다. 사용자의 설정은 수정할 수 없습니다. 클래스의 멤버 수가 100 개를 초과 하 여 컴퓨터에 연결 된 모니터 수 (<xref:System.Windows.Forms.SystemInformation.MonitorCount%2A>)의 모든 항목에 대 한 정보를 Windows 탐색기 (<xref:System.Windows.Forms.SystemInformation.IconHorizontalSpacing%2A> 및 <xref:System.Windows.Forms.SystemInformation.IconVerticalSpacing%2A>)의 아이콘 간격으로 반환 합니다.  
  
 <xref:System.Windows.Forms.SystemInformation> 클래스의 유용한 멤버 중 일부에는 <xref:System.Windows.Forms.SystemInformation.ComputerName%2A>, <xref:System.Windows.Forms.SystemInformation.DbcsEnabled%2A>, <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>및 <xref:System.Windows.Forms.SystemInformation.TerminalServerSession%2A>가 포함 됩니다.  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Forms.SystemInformation>
- [Windows Forms의 전원 관리](power-management-in-windows-forms.md)
