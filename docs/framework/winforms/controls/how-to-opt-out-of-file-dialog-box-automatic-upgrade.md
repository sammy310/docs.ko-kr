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
ms.openlocfilehash: a4be35617e8be1c6c83ac6f2d06e03b6cbb2977f
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59301102"
---
# <a name="how-to-opt-out-of-file-dialog-box-automatic-upgrade"></a>방법: 파일 대화 상자의 자동 업그레이드 옵트아웃
경우는 <xref:System.Windows.Forms.OpenFileDialog> 및 <xref:System.Windows.Forms.SaveFileDialog> 클래스는 응용 프로그램에서 사용 되 고, 해당 모양과 동작은 응용 프로그램에서 실행 중인 Windows 버전에 종속 됩니다. 작성 된 응용 프로그램을 [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)] 또는 이전에 표시 되는 [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)], <xref:System.Windows.Forms.OpenFileDialog> 및 <xref:System.Windows.Forms.SaveFileDialog> 자동으로 표시 됩니다는 [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)] 모양 및 동작 합니다. 부터 [!INCLUDE[net_v30_short](../../../../includes/net-v30-short-md.md)], 표시할 자동 업그레이드를 옵트아웃할 수 있습니다 합니다 <xref:System.Windows.Forms.OpenFileDialog> 및 <xref:System.Windows.Forms.SaveFileDialog> 사용 하 여를 [!INCLUDE[winxp](../../../../includes/winxp-md.md)]-모양 및 동작 스타일입니다.  
  
### <a name="to-opt-out-of-file-dialog-box-automatic-upgrade"></a>파일 대화 상자 자동 업그레이드를 옵트아웃하려면  
  
1. 설정 합니다 <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> 속성을 <xref:System.Windows.Forms.OpenFileDialog> 또는 <xref:System.Windows.Forms.SaveFileDialog> 에 `false` 대화 상자를 표시 하기 전에 합니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Forms.FileDialog>
