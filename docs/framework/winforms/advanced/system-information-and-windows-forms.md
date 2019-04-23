---
title: 시스템 정보 및 Windows Forms
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
ms.openlocfilehash: eeb469dbf4553634aa50d0a9ea17e9b2464defb4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59228902"
---
# <a name="system-information-and-windows-forms"></a><span data-ttu-id="e4d2d-102">시스템 정보 및 Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e4d2d-102">System Information and Windows Forms</span></span>
<span data-ttu-id="e4d2d-103">경우에 따라 코드에서 결정 하기 위해 응용 프로그램에서 실행 되는 컴퓨터에 대 한 정보를 수집 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4d2d-103">Sometimes it is necessary to gather information about the computer that your application is running on in order to make decisions in your code.</span></span> <span data-ttu-id="e4d2d-104">예를 들어만 특정 네트워크 도메인;에 연결 하는 경우에 적용할 수 있는 함수를 해야 할 수 있습니다. 이 경우 도메인을 확인 하 고 도메인에 없는 경우 함수를 사용 하지 않도록 설정 하는 방법을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4d2d-104">For example, you might have a function that is only applicable when connected to a particular network domain; in this case you would need a way to determine the domain and disable the function if the domain is not present.</span></span>  
  
 <span data-ttu-id="e4d2d-105">Windows Forms 응용 프로그램에서 사용할 수는 <xref:System.Windows.Forms.SystemInformation> 실행된 시간에 다양 한 컴퓨터에 대 한 작업을 결정 하는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="e4d2d-105">Windows Forms applications can use the <xref:System.Windows.Forms.SystemInformation> class to determine a number of things about a computer at run time.</span></span> <span data-ttu-id="e4d2d-106">다음 예제는 <xref:System.Windows.Forms.SystemInformation> 검색할 클래스를 <xref:System.Windows.Forms.SystemInformation.UserName%2A> 및 <xref:System.Windows.Forms.SystemInformation.UserDomainName%2A>:</span><span class="sxs-lookup"><span data-stu-id="e4d2d-106">The following example demonstrates using the <xref:System.Windows.Forms.SystemInformation> class to retrieve the <xref:System.Windows.Forms.SystemInformation.UserName%2A> and <xref:System.Windows.Forms.SystemInformation.UserDomainName%2A>:</span></span>  
  
```vb  
Dim User As String = Windows.Forms.SystemInformation.UserName  
Dim Domain As String = Windows.Forms.SystemInformation.UserDomainName  
  
MessageBox.Show("Good morning " & User & ". You are connected to " _  
& Domain)  
```  
  
```csharp  
string User = SystemInformation.UserName;  
string Domain = SystemInformation.UserDomainName;  
  
MessageBox.Show("Good morning " + User + ". You are connected to " _  
+ Domain)  
```  
  
 <span data-ttu-id="e4d2d-107">모든 멤버는 <xref:System.Windows.Forms.SystemInformation> 클래스는 읽기 전용 이며 사용자의 설정을 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e4d2d-107">All members of the <xref:System.Windows.Forms.SystemInformation> class are read-only; you cannot modify a user's settings.</span></span> <span data-ttu-id="e4d2d-108">컴퓨터에 연결 하는 모니터의 수는 모든 정보를 반환 하는 클래스의 100 개 이상의 멤버가 (<xref:System.Windows.Forms.SystemInformation.MonitorCount%2A>)의 Windows 탐색기 아이콘 간격으로 (<xref:System.Windows.Forms.SystemInformation.IconHorizontalSpacing%2A> 및 <xref:System.Windows.Forms.SystemInformation.IconVerticalSpacing%2A>).</span><span class="sxs-lookup"><span data-stu-id="e4d2d-108">There are over 100 members of the class, returning information on everything from the number of monitors attached to the computer (<xref:System.Windows.Forms.SystemInformation.MonitorCount%2A>) to the spacing of icons in Windows Explorer (<xref:System.Windows.Forms.SystemInformation.IconHorizontalSpacing%2A> and <xref:System.Windows.Forms.SystemInformation.IconVerticalSpacing%2A>).</span></span>  
  
 <span data-ttu-id="e4d2d-109">유용한 구성원 중 일부는 <xref:System.Windows.Forms.SystemInformation> 클래스에 포함 <xref:System.Windows.Forms.SystemInformation.ComputerName%2A>를 <xref:System.Windows.Forms.SystemInformation.DbcsEnabled%2A>, <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>, 및 <xref:System.Windows.Forms.SystemInformation.TerminalServerSession%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="e4d2d-109">Some of the more useful members of the <xref:System.Windows.Forms.SystemInformation> class include <xref:System.Windows.Forms.SystemInformation.ComputerName%2A>, <xref:System.Windows.Forms.SystemInformation.DbcsEnabled%2A>, <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>, and <xref:System.Windows.Forms.SystemInformation.TerminalServerSession%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4d2d-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="e4d2d-110">See also</span></span>

- <xref:System.Windows.Forms.SystemInformation>
- [<span data-ttu-id="e4d2d-111">Windows Forms의 전원 관리</span><span class="sxs-lookup"><span data-stu-id="e4d2d-111">Power Management in Windows Forms</span></span>](power-management-in-windows-forms.md)
