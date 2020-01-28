---
title: 설치 된 WPF 버전 확인
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- version [WPF], finding
ms.assetid: 99971cef-e218-4f9f-a4c1-350332741860
ms.openlocfilehash: 8fc5c380779891b44b7c4f7f8aeb5ed119d8b768
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735687"
---
# <a name="how-to-determine-the-installed-version-of-wpf"></a>방법: 설치된 WPF 버전 확인
현재 설치 된 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 버전의 버전 번호는 **레지스트리에**있습니다.  
  
 버전 번호를 찾으려면 다음을 수행 합니다.  
  
1. **시작** 메뉴에서 **실행**을 클릭합니다.  
  
2. **열기**에서 **regedit.exe**를 입력 합니다.  
  
3. 다음 키를 엽니다.  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v3.0\Setup\Windows Presentation Foundation`  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 버전 번호는 **version** 값에 저장 됩니다.
