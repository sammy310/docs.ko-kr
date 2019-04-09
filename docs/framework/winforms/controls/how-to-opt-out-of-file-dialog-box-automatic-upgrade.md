---
title: '방법: 파일 대화 상자의 자동 업그레이드 옵트아웃'
ms.date: 03/30/2017
helpviewer_keywords:
- OpenFileDialog [Windows Forms], opt out of automatic upgrade
- file dialog box [Windows Forms], opt out of automatic upgrade
- Windows Vista file dialog box [Windows Forms], opt out of automatic upgrade
- SaveFileDialog [Windows Forms], opt out of automatic upgrade
- AutoUpgradeEnabled property
ms.assetid: 522e482e-cc01-48b1-8d59-9617dc2c4ac1
ms.openlocfilehash: 6fd34e1127747739423f6402f128194a3a39f5e0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59089150"
---
# <a name="how-to-opt-out-of-file-dialog-box-automatic-upgrade"></a><span data-ttu-id="a3fe4-102">방법: 파일 대화 상자의 자동 업그레이드 옵트아웃</span><span class="sxs-lookup"><span data-stu-id="a3fe4-102">How To: Opt Out of File Dialog Box Automatic Upgrade</span></span>
<span data-ttu-id="a3fe4-103">경우는 <xref:System.Windows.Forms.OpenFileDialog> 및 <xref:System.Windows.Forms.SaveFileDialog> 클래스는 응용 프로그램에서 사용 되 고, 해당 모양과 동작은 응용 프로그램에서 실행 중인 Windows 버전에 종속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3fe4-103">When the <xref:System.Windows.Forms.OpenFileDialog> and <xref:System.Windows.Forms.SaveFileDialog> classes are used in an application, their appearance and behavior depend on the version of Windows the application is running on.</span></span> <span data-ttu-id="a3fe4-104">작성 된 응용 프로그램을 [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)] 또는 이전에 표시 되는 [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)], <xref:System.Windows.Forms.OpenFileDialog> 및 <xref:System.Windows.Forms.SaveFileDialog> 자동으로 표시 됩니다는 [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)] 모양 및 동작 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3fe4-104">When an application that was created on the [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)] or earlier is displayed on [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)], <xref:System.Windows.Forms.OpenFileDialog> and <xref:System.Windows.Forms.SaveFileDialog> are automatically displayed with the [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)] appearance and behavior.</span></span> <span data-ttu-id="a3fe4-105">부터 [!INCLUDE[net_v30_short](../../../../includes/net-v30-short-md.md)], 표시할 자동 업그레이드를 옵트아웃할 수 있습니다 합니다 <xref:System.Windows.Forms.OpenFileDialog> 및 <xref:System.Windows.Forms.SaveFileDialog> 사용 하 여를 [!INCLUDE[winxp](../../../../includes/winxp-md.md)]-모양 및 동작 스타일입니다.</span><span class="sxs-lookup"><span data-stu-id="a3fe4-105">Starting in the [!INCLUDE[net_v30_short](../../../../includes/net-v30-short-md.md)], you can opt out of the automatic upgrade to display the <xref:System.Windows.Forms.OpenFileDialog> and <xref:System.Windows.Forms.SaveFileDialog> with a [!INCLUDE[winxp](../../../../includes/winxp-md.md)]-style appearance and behavior.</span></span>  
  
### <a name="to-opt-out-of-file-dialog-box-automatic-upgrade"></a><span data-ttu-id="a3fe4-106">파일 대화 상자 자동 업그레이드를 옵트아웃하려면</span><span class="sxs-lookup"><span data-stu-id="a3fe4-106">To opt out of file dialog box automatic upgrade</span></span>  
  
1.  <span data-ttu-id="a3fe4-107">설정 합니다 <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> 속성을 <xref:System.Windows.Forms.OpenFileDialog> 또는 <xref:System.Windows.Forms.SaveFileDialog> 에 `false` 대화 상자를 표시 하기 전에 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3fe4-107">Set the <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> property of <xref:System.Windows.Forms.OpenFileDialog> or <xref:System.Windows.Forms.SaveFileDialog> to `false` before you display the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3fe4-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="a3fe4-108">See also</span></span>

- <xref:System.Windows.Forms.FileDialog>
