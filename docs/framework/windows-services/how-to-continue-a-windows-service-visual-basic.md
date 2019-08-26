---
title: '방법: Windows 서비스 계속(Visual Basic)'
ms.date: 03/30/2017
dev_langs:
- vb
f1_keywords:
- ServiceController.Continue
helpviewer_keywords:
- Windows Service applications, pausing
- pausing Windows Service applications
ms.assetid: e5d13760-4c83-4b0d-abef-39852677cd7a
author: ghogen
ms.openlocfilehash: c9a783c0e7df39381ad1d9a8fedd7419605fd241
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69935548"
---
# <a name="how-to-continue-a-windows-service-visual-basic"></a><span data-ttu-id="e47a1-102">방법: Windows 서비스 계속(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e47a1-102">How to: Continue a Windows Service (Visual Basic)</span></span>
<span data-ttu-id="e47a1-103">이 예제에서는 <xref:System.ServiceProcess.ServiceController> 구성 요소를 사용하여 로컬 컴퓨터에서 IIS 관리 서비스를 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="e47a1-103">This example uses the <xref:System.ServiceProcess.ServiceController> component to continue the IIS Admin service on the local computer.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e47a1-104">예</span><span class="sxs-lookup"><span data-stu-id="e47a1-104">Example</span></span>  
 [!code-vb[VbRadconService#11](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#11)]  
[!code-vb[VbRadconService#13](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#13)]  
  
 <span data-ttu-id="e47a1-105">이 코드 예제는 IntelliSense 코드 조각으로 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e47a1-105">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="e47a1-106">코드 조각 선택에서 **Windows 운영 체제 > Windows 서비스**에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e47a1-106">In the code snippet picker, it is located in **Windows Operating System > Windows Services**.</span></span> <span data-ttu-id="e47a1-107">자세한 내용은 [코드 조각](/visualstudio/ide/code-snippets)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e47a1-107">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e47a1-108">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="e47a1-108">Compiling the Code</span></span>  
 <span data-ttu-id="e47a1-109">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="e47a1-109">This example requires:</span></span>  
  
- <span data-ttu-id="e47a1-110">System.serviceprocess.dll에 대한 프로젝트 참조.</span><span class="sxs-lookup"><span data-stu-id="e47a1-110">A project reference to System.serviceprocess.dll.</span></span>  
  
- <span data-ttu-id="e47a1-111"><xref:System.ServiceProcess> 네임스페이스의 멤버에 대한 액세스 권한.</span><span class="sxs-lookup"><span data-stu-id="e47a1-111">Access to the members of the <xref:System.ServiceProcess> namespace.</span></span> <span data-ttu-id="e47a1-112">코드에서 멤버 이름을 정규화하지 않는 경우 `Imports` 문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e47a1-112">Add an `Imports` statement if you are not fully qualifying member names in your code.</span></span> <span data-ttu-id="e47a1-113">자세한 내용은 [Imports 문(.NET 네임스페이스 및 형식)](../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e47a1-113">For more information, see [Imports Statement (.NET Namespace and Type)](../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="e47a1-114">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="e47a1-114">Robust Programming</span></span>  
 <span data-ttu-id="e47a1-115"><xref:System.ServiceProcess.ServiceController> 클래스의 <xref:System.ServiceProcess.ServiceController.MachineName%2A> 속성은 기본적으로 로컬 컴퓨터입니다.</span><span class="sxs-lookup"><span data-stu-id="e47a1-115">The <xref:System.ServiceProcess.ServiceController.MachineName%2A> property of the <xref:System.ServiceProcess.ServiceController> class is the local computer by default.</span></span> <span data-ttu-id="e47a1-116">다른 컴퓨터에서 Windows 서비스를 참조하려면 <xref:System.ServiceProcess.ServiceController.MachineName%2A> 속성을 해당 컴퓨터의 이름으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="e47a1-116">To reference Windows services on another computer, change the <xref:System.ServiceProcess.ServiceController.MachineName%2A> property to the name of that computer.</span></span>  
  
 <span data-ttu-id="e47a1-117">서비스 컨트롤러 상태가 <xref:System.ServiceProcess.ServiceControllerStatus.Paused>인 경우 서비스의 <xref:System.ServiceProcess.ServiceController.Continue%2A> 메서드를 호출할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e47a1-117">You cannot call the <xref:System.ServiceProcess.ServiceController.Continue%2A> method on a service until the service controller status is <xref:System.ServiceProcess.ServiceControllerStatus.Paused>.</span></span>  
  
 <span data-ttu-id="e47a1-118">다음 조건에서 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="e47a1-118">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="e47a1-119">서비스를 다시 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e47a1-119">The service cannot be resumed.</span></span> <span data-ttu-id="e47a1-120">(<xref:System.InvalidOperationException>)</span><span class="sxs-lookup"><span data-stu-id="e47a1-120">(<xref:System.InvalidOperationException>)</span></span>  
  
- <span data-ttu-id="e47a1-121">시스템 API에 액세스할 때 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="e47a1-121">An error occurred when accessing a system API.</span></span> <span data-ttu-id="e47a1-122">(<xref:System.ComponentModel.Win32Exception>)</span><span class="sxs-lookup"><span data-stu-id="e47a1-122">(<xref:System.ComponentModel.Win32Exception>)</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="e47a1-123">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="e47a1-123">.NET Framework Security</span></span>  
 <span data-ttu-id="e47a1-124"><xref:System.ServiceProcess.ServiceControllerPermission> 클래스에서 <xref:System.ServiceProcess.ServiceControllerPermissionAccess> 열거형을 사용하여 권한을 설정하면 컴퓨터에서 서비스 제어가 제한될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e47a1-124">Control of services on the computer may be restricted by using the <xref:System.ServiceProcess.ServiceControllerPermissionAccess> enumeration to set permissions in the <xref:System.ServiceProcess.ServiceControllerPermission> class.</span></span>  
  
 <span data-ttu-id="e47a1-125"><xref:System.Security.Permissions.PermissionState> 열거형을 사용하여 <xref:System.Security.Permissions.SecurityPermission> 클래스에서 권한을 설정하면 서비스 정보에 대한 액세스가 제한될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e47a1-125">Access to service information may be restricted by using the <xref:System.Security.Permissions.PermissionState> enumeration to set permissions in the <xref:System.Security.Permissions.SecurityPermission> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e47a1-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e47a1-126">See also</span></span>

- <xref:System.ServiceProcess.ServiceController>
- <xref:System.ServiceProcess.ServiceControllerStatus>
- [<span data-ttu-id="e47a1-127">방법: Windows 서비스 일시 중지(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e47a1-127">How to: Pause a Windows Service (Visual Basic)</span></span>](../../../docs/framework/windows-services/how-to-pause-a-windows-service-visual-basic.md)
