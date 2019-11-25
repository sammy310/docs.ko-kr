---
title: '방법: 파일 대화 상자 자동 업그레이드 옵트아웃'
ms.date: 03/30/2017
helpviewer_keywords:
- OpenFileDialog [Windows Forms], opt out of automatic upgrade
- file dialog box [Windows Forms], opt out of automatic upgrade
- Windows Vista file dialog box [Windows Forms], opt out of automatic upgrade
- SaveFileDialog [Windows Forms], opt out of automatic upgrade
- AutoUpgradeEnabled property
ms.assetid: 522e482e-cc01-48b1-8d59-9617dc2c4ac1
ms.openlocfilehash: bbde260cc7f05226c9b06325b45708e1cde3cf8c
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976891"
---
# <a name="how-to-opt-out-of-file-dialog-box-automatic-upgrade"></a>방법: 파일 대화 상자 자동 업그레이드 옵트아웃
응용 프로그램에서 <xref:System.Windows.Forms.OpenFileDialog> 및 <xref:System.Windows.Forms.SaveFileDialog> 클래스를 사용 하는 경우 응용 프로그램이 실행 되는 Windows 버전에 따라 모양과 동작이 달라 집니다. .NET Framework 2.0 또는 이전 버전에서 만든 응용 프로그램이 Windows Vista에 표시 되 면 <xref:System.Windows.Forms.OpenFileDialog> 및 <xref:System.Windows.Forms.SaveFileDialog> Windows Vista 모양과 동작으로 자동으로 표시 됩니다. 3\.0 .NET Framework부터 자동 업그레이드를 옵트아웃 하 여 <xref:System.Windows.Forms.OpenFileDialog>를 표시 하 고 [!INCLUDE[winxp](../../../../includes/winxp-md.md)]스타일의 모양과 동작을 <xref:System.Windows.Forms.SaveFileDialog> 수 있습니다.  
  
### <a name="to-opt-out-of-file-dialog-box-automatic-upgrade"></a>파일 대화 상자 자동 업그레이드를 옵트아웃하려면  
  
1. 대화 상자를 표시 하기 전에 <xref:System.Windows.Forms.OpenFileDialog> 또는 <xref:System.Windows.Forms.SaveFileDialog>의 <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> 속성을 `false`로 설정 합니다.  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Forms.FileDialog>
