---
title: '문제 해결: Windows 서비스 디버깅'
ms.date: 03/30/2017
helpviewer_keywords:
- debugging Windows Service applications
- debugging [Visual Studio], Windows services
- troubleshooting service applications
- services, troubleshooting
- troubleshooting debugging, Windows Services
- Windows Service applications, debugging
- services, debugging
- Windows Service applications, troubleshooting
ms.assetid: cf859d4c-f04c-4cb7-81e3-bc7de8bea190
author: ghogen
ms.openlocfilehash: 0552fc005a25e83065bb44e425770f9cef84f71b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59082583"
---
# <a name="troubleshooting-debugging-windows-services"></a><span data-ttu-id="135e5-102">문제 해결: Windows 서비스 디버깅</span><span class="sxs-lookup"><span data-stu-id="135e5-102">Troubleshooting: Debugging Windows Services</span></span>
<span data-ttu-id="135e5-103">Windows 서비스 애플리케이션을 디버그할 때 서비스와 **Windows 서비스 관리자**가 상호 작용합니다.</span><span class="sxs-lookup"><span data-stu-id="135e5-103">When you debug a Windows service application, your service and the **Windows Service Manager** interact.</span></span> <span data-ttu-id="135e5-104">**서비스 관리자**는 <xref:System.ServiceProcess.ServiceBase.OnStart%2A> 메서드를 호출하여 서비스를 시작한 다음, <xref:System.ServiceProcess.ServiceBase.OnStart%2A> 메서드가 반환될 때까지 30초 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="135e5-104">The **Service Manager** starts your service by calling the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method, and then waits 30 seconds for the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method to return.</span></span> <span data-ttu-id="135e5-105">이 시간 이내에 메서드가 반환되지 않으면 관리자는 서비스를 시작할 수 없다는 오류를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="135e5-105">If the method does not return in this time, the manager shows an error that the service cannot be started.</span></span>  
  
 <span data-ttu-id="135e5-106">디버그 하는 경우는 <xref:System.ServiceProcess.ServiceBase.OnStart%2A> 에 설명 된 대로 메서드 [방법: Windows 서비스 애플리케이션 디버깅](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md)에 설명된 대로  메서드를 디버그할 때는 이 30초 기간에 유의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="135e5-106">When you debug the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method as described in [How to: Debug Windows Service Applications](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md), you must be aware of this 30-second period.</span></span> <span data-ttu-id="135e5-107"><xref:System.ServiceProcess.ServiceBase.OnStart%2A> 메서드에 중단점을 배치하고 메서드를 30초 이내에 단계별로 실행하지 못하면 관리자가 서비스를 시작하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="135e5-107">If you place a breakpoint in the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method and do not step through it in 30 seconds, the manager will not start the service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="135e5-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="135e5-108">See also</span></span>

- [<span data-ttu-id="135e5-109">방법: Windows 서비스 애플리케이션 디버그</span><span class="sxs-lookup"><span data-stu-id="135e5-109">How to: Debug Windows Service Applications</span></span>](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md)
- [<span data-ttu-id="135e5-110">Windows 서비스 애플리케이션 소개</span><span class="sxs-lookup"><span data-stu-id="135e5-110">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)
