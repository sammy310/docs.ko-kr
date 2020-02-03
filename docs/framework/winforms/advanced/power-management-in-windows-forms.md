---
title: 전원 관리
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- battery states
- power states
ms.assetid: ad04a801-5682-4d88-92c5-26eb9cdb209a
ms.openlocfilehash: 9ac39df43a08f62e50116c61c4bdeda4cd1c8281
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746860"
---
# <a name="power-management-in-windows-forms"></a><span data-ttu-id="fc8e5-102">Windows Forms의 전원 관리</span><span class="sxs-lookup"><span data-stu-id="fc8e5-102">Power Management in Windows Forms</span></span>
<span data-ttu-id="fc8e5-103">Windows Forms 응용 프로그램은 Windows 운영 체제의 전원 관리 기능을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc8e5-103">Your Windows Forms applications can take advantage of the power management features in the Windows operating system.</span></span> <span data-ttu-id="fc8e5-104">응용 프로그램은 컴퓨터의 전원 상태를 모니터링 하 고 상태 변경이 발생 하면 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc8e5-104">Your applications can monitor the power status of a computer and take action when a status change occurs.</span></span> <span data-ttu-id="fc8e5-105">예를 들어 응용 프로그램이 휴대용 컴퓨터에서 실행 되는 경우 컴퓨터의 배터리 충전량이 특정 수준에 속하면 응용 프로그램의 특정 기능을 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc8e5-105">For example, if your application is running on a portable computer, you might want to disable certain features in your application when the computer's battery charge falls under a certain level.</span></span>  
  
 <span data-ttu-id="fc8e5-106">.NET Framework은 사용자가 운영 체제를 일시 중단 하거나 다시 시작 하는 경우 또는 AC 전원 상태 또는 배터리 상태가 변경 되는 경우와 같이 전원 상태가 변경 될 때마다 발생 하는 <xref:Microsoft.Win32.SystemEvents.PowerModeChanged> 이벤트를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc8e5-106">The .NET Framework provides a <xref:Microsoft.Win32.SystemEvents.PowerModeChanged> event that occurs whenever there is a change in power status, such as when a user suspends or resumes the operating system, or when the AC power status or battery status changes.</span></span> <span data-ttu-id="fc8e5-107">다음 코드 예제와 같이 <xref:System.Windows.Forms.SystemInformation> 클래스의 <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> 속성을 사용 하 여 현재 상태를 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc8e5-107">The <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> property of the <xref:System.Windows.Forms.SystemInformation> class can be used to query for the current status, as shown in the following code example.</span></span>  
  
 [!code-csharp[PowerMode#1](~/samples/snippets/csharp/VS_Snippets_Winforms/powermode/cs/form1.cs#1)]
 [!code-vb[PowerMode#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/powermode/vb/form1.vb#1)]  
  
 <span data-ttu-id="fc8e5-108"><xref:System.Windows.Forms.BatteryChargeStatus> 열거형 외에도 <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> 속성에는 배터리 용량 (<xref:System.Windows.Forms.PowerStatus.BatteryFullLifetime%2A>) 및 배터리 요금 백분율 (<xref:System.Windows.Forms.PowerStatus.BatteryLifePercent%2A>, <xref:System.Windows.Forms.PowerStatus.BatteryLifeRemaining%2A>)을 결정 하는 열거형이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc8e5-108">Besides the <xref:System.Windows.Forms.BatteryChargeStatus> enumerations, the <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> property also contains enumerations for determining battery capacity (<xref:System.Windows.Forms.PowerStatus.BatteryFullLifetime%2A>) and battery charge percentage (<xref:System.Windows.Forms.PowerStatus.BatteryLifePercent%2A>, <xref:System.Windows.Forms.PowerStatus.BatteryLifeRemaining%2A>).</span></span>  
  
 <span data-ttu-id="fc8e5-109"><xref:System.Windows.Forms.Application>의 <xref:System.Windows.Forms.Application.SetSuspendState%2A> 메서드를 사용 하 여 컴퓨터를 최대 절전 모드 또는 일시 중단 모드로 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc8e5-109">You can use the <xref:System.Windows.Forms.Application.SetSuspendState%2A> method of the <xref:System.Windows.Forms.Application> to put a computer into hibernation or suspend mode.</span></span> <span data-ttu-id="fc8e5-110">`force` 인수를 `false`로 설정 하면 운영 체제에서 일시 중단 권한을 요청 하는 모든 응용 프로그램에 이벤트를 브로드캐스트합니다.</span><span class="sxs-lookup"><span data-stu-id="fc8e5-110">If the `force` argument is set to `false`, the operating system will broadcast an event to all applications requesting permission to suspend.</span></span> <span data-ttu-id="fc8e5-111">`disableWakeEvent` 인수를 `true`로 설정 하면 운영 체제에서 모든 절전 모드 해제 이벤트를 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc8e5-111">If the `disableWakeEvent` argument is set to `true`, the operating system disables all wake events.</span></span>  
  
 <span data-ttu-id="fc8e5-112">다음 코드 예제에서는 컴퓨터를 최대 절전 모드로 전환 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fc8e5-112">The following code example demonstrates how to put a computer into hibernation.</span></span>  
  
 [!code-csharp[PowerMode#2](~/samples/snippets/csharp/VS_Snippets_Winforms/powermode/cs/form1.cs#2)]
 [!code-vb[PowerMode#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/powermode/vb/form1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="fc8e5-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fc8e5-113">See also</span></span>

- <xref:Microsoft.Win32.SystemEvents.PowerModeChanged>
- <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>
- <xref:System.Windows.Forms.Application.SetSuspendState%2A>
- <xref:Microsoft.Win32.SystemEvents.SessionSwitch>
