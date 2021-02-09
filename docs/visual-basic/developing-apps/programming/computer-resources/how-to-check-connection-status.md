---
description: '자세한 정보: 방법: Visual Basic에서 연결 상태 확인'
title: '방법: 연결 상태 확인'
ms.date: 07/20/2015
helpviewer_keywords:
- Web connections [Visual Basic]
- IsAvailable property [Visual Basic], about IsAvailable
- connections [Visual Basic], checking status
- connection status [Visual Basic]
ms.assetid: 4d9ee8ab-9a6f-4279-ace4-b75afc976a74
ms.openlocfilehash: c568e3be5d8fedb1ae12c748110b23218deaf069
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797746"
---
# <a name="how-to-check-connection-status-in-visual-basic"></a><span data-ttu-id="9821d-103">방법: Visual Basic에서 연결 상태 확인</span><span class="sxs-lookup"><span data-stu-id="9821d-103">How to: Check Connection Status in Visual Basic</span></span>

<span data-ttu-id="9821d-104"><xref:Microsoft.VisualBasic.Devices.Network.IsAvailable> 속성은 컴퓨터에 작동하는 네트워크 또는 인터넷 연결이 있는지 확인하는 데 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9821d-104">The <xref:Microsoft.VisualBasic.Devices.Network.IsAvailable> property can be used to determine whether the computer has a working network or Internet connection.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-check-whether-a-computer-has-a-working-connection"></a><span data-ttu-id="9821d-105">컴퓨터에 작동하는 연결이 있는지 확인하려면</span><span class="sxs-lookup"><span data-stu-id="9821d-105">To check whether a computer has a working connection</span></span>  
  
- <span data-ttu-id="9821d-106">`IsAvailable` 속성이 `True` 또는 `False`인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="9821d-106">Determine whether the `IsAvailable` property is `True` or `False`.</span></span> <span data-ttu-id="9821d-107">다음 코드에서는 속성의 상태를 확인하고 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="9821d-107">The following code checks the property's status and reports it:</span></span>  
  
     [!code-vb[VbResourceTasks#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#3)]  
  
     <span data-ttu-id="9821d-108">이 코드 예제는 IntelliSense 코드 조각으로 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9821d-108">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="9821d-109">코드 조각 선택에서는 **연결 및 네트워킹** 에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9821d-109">In the code snippet picker, it is located in **Connectivity and Networking**.</span></span> <span data-ttu-id="9821d-110">자세한 내용은 [코드 조각](/visualstudio/ide/code-snippets)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9821d-110">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9821d-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9821d-111">See also</span></span>

- <xref:Microsoft.VisualBasic.Devices.Network?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Devices.Network.IsAvailable>
