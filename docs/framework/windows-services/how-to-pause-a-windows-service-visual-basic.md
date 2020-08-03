---
title: '방법: Windows 서비스 일시 중지(Visual Basic)'
description: 'ServiceController 구성 요소를 사용하여 Visual Basic이 설치된 로컬 컴퓨터에서 Windows 서비스(예: IIS Admin Service)를 일시 중지하는 방법을 읽어보세요.'
ms.date: 03/30/2017
dev_langs:
- vb
f1_keywords:
- ServiceController.Pause
helpviewer_keywords:
- Windows Service applications, pausing
- pausing Windows Service applications
ms.assetid: eddb9409-942b-46b6-a2ce-fbd4c65f2790
author: ghogen
ms.openlocfilehash: 628cc2e896f7f8a289e52674b721c4aef605854c
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/22/2020
ms.locfileid: "86925568"
---
# <a name="how-to-pause-a-windows-service-visual-basic"></a><span data-ttu-id="9ac12-103">방법: Windows 서비스 일시 중지(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9ac12-103">How to: Pause a Windows Service (Visual Basic)</span></span>
<span data-ttu-id="9ac12-104">이 예제에서는 <xref:System.ServiceProcess.ServiceController> 구성 요소를 사용하여 로컬 컴퓨터에서 IIS 관리 서비스를 일시 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="9ac12-104">This example uses the <xref:System.ServiceProcess.ServiceController> component to pause the IIS Admin service on the local computer.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9ac12-105">예제</span><span class="sxs-lookup"><span data-stu-id="9ac12-105">Example</span></span>  
 [!code-vb[VbRadconService#11](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#11)]  
[!code-vb[VbRadconService#12](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#12)]  
  
 <span data-ttu-id="9ac12-106">이 코드 예제는 IntelliSense 코드 조각으로 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ac12-106">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="9ac12-107">코드 조각 선택에서 **Windows 운영 체제 > Windows 서비스**에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ac12-107">In the code snippet picker, it is located in **Windows Operating System > Windows Services**.</span></span> <span data-ttu-id="9ac12-108">자세한 내용은 [코드 조각](/visualstudio/ide/code-snippets)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9ac12-108">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9ac12-109">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="9ac12-109">Compiling the Code</span></span>  
 <span data-ttu-id="9ac12-110">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9ac12-110">This example requires:</span></span>  
  
- <span data-ttu-id="9ac12-111">System.serviceprocess.dll에 대한 프로젝트 참조.</span><span class="sxs-lookup"><span data-stu-id="9ac12-111">A project reference to System.serviceprocess.dll.</span></span>  
  
- <span data-ttu-id="9ac12-112"><xref:System.ServiceProcess> 네임스페이스의 멤버에 대한 액세스 권한.</span><span class="sxs-lookup"><span data-stu-id="9ac12-112">Access to the members of the <xref:System.ServiceProcess> namespace.</span></span> <span data-ttu-id="9ac12-113">코드에서 멤버 이름을 정규화하지 않는 경우 `Imports` 문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9ac12-113">Add an `Imports` statement if you are not fully qualifying member names in your code.</span></span> <span data-ttu-id="9ac12-114">자세한 내용은 [Imports 문(.NET 네임스페이스 및 형식)](../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9ac12-114">For more information, see [Imports Statement (.NET Namespace and Type)](../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="9ac12-115">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="9ac12-115">Robust Programming</span></span>  
 <span data-ttu-id="9ac12-116"><xref:System.ServiceProcess.ServiceController> 클래스의 <xref:System.ServiceProcess.ServiceController.MachineName%2A> 속성은 기본적으로 로컬 컴퓨터입니다.</span><span class="sxs-lookup"><span data-stu-id="9ac12-116">The <xref:System.ServiceProcess.ServiceController.MachineName%2A> property of the <xref:System.ServiceProcess.ServiceController> class is the local computer by default.</span></span> <span data-ttu-id="9ac12-117">다른 컴퓨터에서 Windows 서비스를 참조하려면 <xref:System.ServiceProcess.ServiceController.MachineName%2A> 속성을 해당 컴퓨터의 이름으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="9ac12-117">To reference Windows services on another computer, change the <xref:System.ServiceProcess.ServiceController.MachineName%2A> property to the name of that computer.</span></span>  
  
 <span data-ttu-id="9ac12-118">다음 조건에서 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="9ac12-118">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="9ac12-119">서비스를 일시 중지할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9ac12-119">The service cannot be paused.</span></span> <span data-ttu-id="9ac12-120">(<xref:System.InvalidOperationException>)</span><span class="sxs-lookup"><span data-stu-id="9ac12-120">(<xref:System.InvalidOperationException>)</span></span>  
  
- <span data-ttu-id="9ac12-121">시스템 API에 액세스할 때 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="9ac12-121">An error occurred when accessing a system API.</span></span> <span data-ttu-id="9ac12-122">(<xref:System.ComponentModel.Win32Exception>)</span><span class="sxs-lookup"><span data-stu-id="9ac12-122">(<xref:System.ComponentModel.Win32Exception>)</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="9ac12-123">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="9ac12-123">.NET Framework Security</span></span>  
 <span data-ttu-id="9ac12-124"><xref:System.ServiceProcess.ServiceControllerPermission>에서 <xref:System.ServiceProcess.ServiceControllerPermissionAccess>를 사용하여 권한을 설정하면 컴퓨터에서 서비스 제어가 제한될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ac12-124">Control of services on the computer may be restricted by using the <xref:System.ServiceProcess.ServiceControllerPermissionAccess> to set permissions in the <xref:System.ServiceProcess.ServiceControllerPermission>.</span></span>  
  
 <span data-ttu-id="9ac12-125"><xref:System.Security.Permissions.PermissionState>를 사용하여 <xref:System.Security.Permissions.SecurityPermission>에서 권한을 설정하면 서비스 정보에 대한 액세스가 제한될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ac12-125">Access to service information may be restricted by using the <xref:System.Security.Permissions.PermissionState> to set permissions in the <xref:System.Security.Permissions.SecurityPermission>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ac12-126">참조</span><span class="sxs-lookup"><span data-stu-id="9ac12-126">See also</span></span>

- <xref:System.ServiceProcess.ServiceController>
- <xref:System.ServiceProcess.ServiceControllerStatus>
- <xref:System.ServiceProcess.ServiceController.WaitForStatus%2A>
- [<span data-ttu-id="9ac12-127">방법: Windows 서비스 계속(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9ac12-127">How to: Continue a Windows Service (Visual Basic)</span></span>](how-to-continue-a-windows-service-visual-basic.md)
