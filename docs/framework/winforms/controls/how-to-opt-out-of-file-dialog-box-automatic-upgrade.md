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
ms.openlocfilehash: 0753873ac37f26d6503397290ef4603702737a86
ms.sourcegitcommit: a8d3504f0eae1a40bda2b06bd441ba01f1631ef0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/18/2019
ms.locfileid: "67170622"
---
# <a name="how-to-opt-out-of-file-dialog-box-automatic-upgrade"></a><span data-ttu-id="0d43e-102">방법: 파일 대화 상자의 자동 업그레이드 옵트아웃</span><span class="sxs-lookup"><span data-stu-id="0d43e-102">How To: Opt Out of File Dialog Box Automatic Upgrade</span></span>
<span data-ttu-id="0d43e-103">경우는 <xref:System.Windows.Forms.OpenFileDialog> 및 <xref:System.Windows.Forms.SaveFileDialog> 클래스는 응용 프로그램에서 사용 되 고, 해당 모양과 동작은 응용 프로그램에서 실행 중인 Windows 버전에 종속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d43e-103">When the <xref:System.Windows.Forms.OpenFileDialog> and <xref:System.Windows.Forms.SaveFileDialog> classes are used in an application, their appearance and behavior depend on the version of Windows the application is running on.</span></span> <span data-ttu-id="0d43e-104">또는 이전 버전의.NET Framework 2.0에 만든 응용 프로그램에 표시 되 면 [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)], <xref:System.Windows.Forms.OpenFileDialog> 및 <xref:System.Windows.Forms.SaveFileDialog> 사용 하 여 자동으로 표시 되는 [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)] 모양 및 동작 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d43e-104">When an application that was created on the .NET Framework 2.0 or earlier is displayed on [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)], <xref:System.Windows.Forms.OpenFileDialog> and <xref:System.Windows.Forms.SaveFileDialog> are automatically displayed with the [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)] appearance and behavior.</span></span> <span data-ttu-id="0d43e-105">.NET Framework 3.0 부터는 옵트아웃할 수 있습니다 자동 업그레이드를 표시 합니다 <xref:System.Windows.Forms.OpenFileDialog> 및 <xref:System.Windows.Forms.SaveFileDialog> 사용 하 여를 [!INCLUDE[winxp](../../../../includes/winxp-md.md)]-모양 및 동작 스타일입니다.</span><span class="sxs-lookup"><span data-stu-id="0d43e-105">Starting in the .NET Framework 3.0, you can opt out of the automatic upgrade to display the <xref:System.Windows.Forms.OpenFileDialog> and <xref:System.Windows.Forms.SaveFileDialog> with a [!INCLUDE[winxp](../../../../includes/winxp-md.md)]-style appearance and behavior.</span></span>  
  
### <a name="to-opt-out-of-file-dialog-box-automatic-upgrade"></a><span data-ttu-id="0d43e-106">파일 대화 상자 자동 업그레이드를 옵트아웃하려면</span><span class="sxs-lookup"><span data-stu-id="0d43e-106">To opt out of file dialog box automatic upgrade</span></span>  
  
1. <span data-ttu-id="0d43e-107">설정 합니다 <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> 속성을 <xref:System.Windows.Forms.OpenFileDialog> 또는 <xref:System.Windows.Forms.SaveFileDialog> 에 `false` 대화 상자를 표시 하기 전에 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d43e-107">Set the <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> property of <xref:System.Windows.Forms.OpenFileDialog> or <xref:System.Windows.Forms.SaveFileDialog> to `false` before you display the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d43e-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="0d43e-108">See also</span></span>

- <xref:System.Windows.Forms.FileDialog>
