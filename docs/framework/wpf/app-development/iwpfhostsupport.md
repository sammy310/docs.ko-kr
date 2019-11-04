---
title: IWpfHostSupport
ms.date: 03/30/2017
helpviewer_keywords:
- IWpfHostSupport interface [WPF]
ms.assetid: cc5a0281-de81-4cc1-87e4-0e46b1a811e9
ms.openlocfilehash: 91a29233d12a842a64b7d3dd497312f6dc6742ca
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/01/2019
ms.locfileid: "73423646"
---
# <a name="iwpfhostsupport"></a>IWpfHostSupport
Presentationhost.exe를 통해 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 콘텐츠를 호스트 하는 응용 프로그램은이 인터페이스를 구현 하 여 호스트와 Presentationhost.exe 간의 통합 지점을 제공 합니다.  
  
## <a name="remarks"></a>주의  
 웹 브라우저와 같은 [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] 응용 프로그램은 Xbap (XAML 브라우저 응용 프로그램) 및 느슨한 XAML을 비롯 한 WPF 콘텐츠를 호스팅할 수 있습니다. WPF 콘텐츠를 호스트 하기 위해 [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] 응용 프로그램은 [WebBrowser 컨트롤](https://go.microsoft.com/fwlink/?LinkId=97911)의 인스턴스를 만듭니다. 호스트 되는 WPF는 호스트에 호스팅된 WPF 콘텐츠를 제공 하는 Presentationhost.exe의 인스턴스를 만들어 [WebBrowser 컨트롤](https://go.microsoft.com/fwlink/?LinkId=97911)에 표시 합니다.  
  
 `IWpfHostSupport`에서 통합을 사용 하도록 설정 하면 Presentationhost.exe에서 다음을 수행할 수 있습니다.  
  
- 호스트 응용 프로그램이 관심 있는 원시 입력 장치 (휴먼 인터페이스 장치)를 검색 하 고 등록 합니다.  
  
- 등록 된 원시 입력 장치에서 입력 메시지를 수신 하 고 호스트 응용 프로그램에 적절 한 메시지를 전달 합니다.  
  
- 호스트 응용 프로그램에서 사용자 지정 진행률 및 오류 사용자 인터페이스를 쿼리 합니다.  
  
> [!NOTE]
> 이 API는 로컬 클라이언트 컴퓨터에서만 사용할 수 있도록 지원됩니다.  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|[GetRawInputDevices](getrawinputdevices.md)|PresentationHost.exe가 호스트 애플리케이션과 관련된 원시 입력 디바이스(휴먼 인터페이스 디바이스)를 검색할 수 있게 합니다.|  
|[FilterInputMessage](filterinputmessage.md)|E_NOTIMPL이 반환되지 않는 한 메시지를 받을 때마다 PresentationHost.exe에서 호출됩니다.|  
|[GetCustomUI](getcustomui.md)|기본적으로 Presentationhost.exe는 WPF 콘텐츠가 배포 될 때 표시 되는 고유한 배포 진행률 및 배포 오류 사용자 인터페이스를 제공 합니다.|
