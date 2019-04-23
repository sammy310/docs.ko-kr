---
title: '방법: 설치된 WPF 버전 확인'
ms.date: 03/30/2017
helpviewer_keywords:
- version [WPF], finding
ms.assetid: 99971cef-e218-4f9f-a4c1-350332741860
ms.openlocfilehash: ffbd9a4c7f66dff9c8773dff4259551e20aa963d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59768022"
---
# <a name="how-to-determine-the-installed-version-of-wpf"></a>방법: 설치된 WPF 버전 확인
현재 설치 된 버전의 버전 번호 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 에 **레지스트리**합니다.  
  
 버전 번호를 찾으려면:  
  
1. **시작** 메뉴에서 **실행**을 클릭합니다.  
  
2. **엽니다**, 형식 **regedit.exe**합니다.  
  
3. 다음 키를 엽니다.  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v3.0\Setup\Windows Presentation Foundation`  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 버전 번호에 저장 되는 **버전** 값입니다.
