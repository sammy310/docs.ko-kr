---
title: Windows Forms의 전원 관리
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- battery states
- power states
ms.assetid: ad04a801-5682-4d88-92c5-26eb9cdb209a
ms.openlocfilehash: 6bb9b4f30a88ece93b17ff2510087b220d538738
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61757653"
---
# <a name="power-management-in-windows-forms"></a><span data-ttu-id="d6398-102">Windows Forms의 전원 관리</span><span class="sxs-lookup"><span data-stu-id="d6398-102">Power Management in Windows Forms</span></span>
<span data-ttu-id="d6398-103">Windows Forms 응용 프로그램 Windows 운영 체제에서 전원 관리 기능 활용을 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6398-103">Your Windows Forms applications can take advantage of the power management features in the Windows operating system.</span></span> <span data-ttu-id="d6398-104">응용 프로그램 컴퓨터의 전원 상태를 모니터링 하 고 상태 변경이 발생할 때 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6398-104">Your applications can monitor the power status of a computer and take action when a status change occurs.</span></span> <span data-ttu-id="d6398-105">예를 들어, 응용 프로그램 휴대용 컴퓨터를 실행 하는 경우 컴퓨터의 배터리 충전량 특정 수준에 속하는 경우 응용 프로그램의 특정 기능을 사용 하지 않도록 설정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d6398-105">For example, if your application is running on a portable computer, you might want to disable certain features in your application when the computer's battery charge falls under a certain level.</span></span>  
  
 <span data-ttu-id="d6398-106">[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 제공 된 <xref:Microsoft.Win32.SystemEvents.PowerModeChanged> AC 전원 상태 또는 배터리 상태를 변경 하는 경우 또는 사용자 일시 중단 하거나 운영 체제를 다시 시작 하는 등 전원 상태가 변경 될 때마다 발생 하는 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="d6398-106">The [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] provides a <xref:Microsoft.Win32.SystemEvents.PowerModeChanged> event that occurs whenever there is a change in power status, such as when a user suspends or resumes the operating system, or when the AC power status or battery status changes.</span></span> <span data-ttu-id="d6398-107"><xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> 속성의는 <xref:System.Windows.Forms.SystemInformation> 클래스 수 있습니다 다음 코드 예제에 표시 된 대로 현재 상태에 대 한 쿼리를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6398-107">The <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> property of the <xref:System.Windows.Forms.SystemInformation> class can be used to query for the current status, as shown in the following code example.</span></span>  
  
 [!code-csharp[PowerMode#1](~/samples/snippets/csharp/VS_Snippets_Winforms/powermode/cs/form1.cs#1)]
 [!code-vb[PowerMode#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/powermode/vb/form1.vb#1)]  
  
 <span data-ttu-id="d6398-108">외에 합니다 <xref:System.Windows.Forms.BatteryChargeStatus> 열거형을 <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> 속성 열거형 배터리 용량을 결정 하는 데에 포함 되어 있습니다 (<xref:System.Windows.Forms.PowerStatus.BatteryFullLifetime%2A>) 및 배터리 백분율 요금이 부과 됩니다 (<xref:System.Windows.Forms.PowerStatus.BatteryLifePercent%2A>, <xref:System.Windows.Forms.PowerStatus.BatteryLifeRemaining%2A>).</span><span class="sxs-lookup"><span data-stu-id="d6398-108">Besides the <xref:System.Windows.Forms.BatteryChargeStatus> enumerations, the <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> property also contains enumerations for determining battery capacity (<xref:System.Windows.Forms.PowerStatus.BatteryFullLifetime%2A>) and battery charge percentage (<xref:System.Windows.Forms.PowerStatus.BatteryLifePercent%2A>, <xref:System.Windows.Forms.PowerStatus.BatteryLifeRemaining%2A>).</span></span>  
  
 <span data-ttu-id="d6398-109">사용할 수는 <xref:System.Windows.Forms.Application.SetSuspendState%2A> 메서드는 <xref:System.Windows.Forms.Application> 컴퓨터 최대 절전 모드로 전환 하거나 일시 중단 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="d6398-109">You can use the <xref:System.Windows.Forms.Application.SetSuspendState%2A> method of the <xref:System.Windows.Forms.Application> to put a computer into hibernation or suspend mode.</span></span> <span data-ttu-id="d6398-110">경우는 `force` 인수가로 설정 된 `false`, 운영 체제 이벤트 일시 중단 하는 권한을 요청 하는 모든 응용 프로그램에 브로드캐스트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6398-110">If the `force` argument is set to `false`, the operating system will broadcast an event to all applications requesting permission to suspend.</span></span> <span data-ttu-id="d6398-111">경우는 `disableWakeEvent` 인수가로 설정 된 `true`, 운영 체제 절전 모드 해제 이벤트를 모두 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6398-111">If the `disableWakeEvent` argument is set to `true`, the operating system disables all wake events.</span></span>  
  
 <span data-ttu-id="d6398-112">다음 코드 예제에서는 컴퓨터 최대 절전 모드로 전환 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6398-112">The following code example demonstrates how to put a computer into hibernation.</span></span>  
  
 [!code-csharp[PowerMode#2](~/samples/snippets/csharp/VS_Snippets_Winforms/powermode/cs/form1.cs#2)]
 [!code-vb[PowerMode#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/powermode/vb/form1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="d6398-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="d6398-113">See also</span></span>

- <xref:Microsoft.Win32.SystemEvents.PowerModeChanged>
- <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>
- <xref:System.Windows.Forms.Application.SetSuspendState%2A>
- <xref:Microsoft.Win32.SystemEvents.SessionSwitch>
