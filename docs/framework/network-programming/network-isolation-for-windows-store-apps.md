---
title: Windows 스토어 앱에 대한 네트워크 격리
ms.date: 03/30/2017
ms.assetid: b064497c-d956-46b8-838d-7a0223c7e200
ms.openlocfilehash: 390a0281f03b08322cc1bee469b601fd5a1547c4
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/04/2019
ms.locfileid: "74802171"
---
# <a name="network-isolation-for-windows-store-apps"></a>Windows 스토어 앱에 대한 네트워크 격리

<xref:System.Net>, <xref:System.Net.Http> 및 <xref:System.Net.Http.Headers> 네임스페이스의 클래스는 Windows 스토어 앱 또는 데스크톱 앱을 개발하는 데 사용할 수 있습니다. Windows 스토어 앱에서 사용할 때 이러한 네임스페이스의 클래스는 Windows 8에서 사용한 애플리케이션 보안 모델의 일부인 네트워크 격리의 영향을 받습니다. 시스템의 Windows 스토어 앱에서 네트워크에 액세스할 수 있도록 앱 매니페스트에서 적절한 네트워크 기능을 사용해야 합니다.  
  
## <a name="checklist-for-network-isolation"></a>네트워크 격리 검사 목록  

이 검사 목록을 사용하여 Windows 스토어 앱에 대해 네트워크 격리가 구성되어 있는지 확인합니다.  
  
1. 앱에 필요한 네트워크 액세스 요청의 방향을 결정합니다. 이 방향은 아웃바운드 클라이언트에서 시작된 요청 또는 원치 않는 인바운드 요청이거나, 이러한 두 네트워크 요청 유형을 조합한 것일 수 있습니다.  
  
2. 앱과 통신하는 네트워크 리소스의 유형을 결정합니다. 앱이 홈 또는 회사 네트워크에서 신뢰할 수 있는 리소스와 통신해야 할 수도 있습니다. 앱에서 인터넷에 있는 리소스와 통신해야 할 수도 있습니다. 앱에서 두 가지 유형의 네트워크 리소스 모두에 액세스해야 할 수도 있습니다.  
  
3. 앱 매니페스트에서 필요한 최소 네트워킹 격리 기능을 구성합니다.  
  
4. 문제 해결을 위해 제공된 네트워크 격리 도구를 사용하여 테스트하도록 앱을 배포하고 실행합니다.  
  
네트워크 격리 문제를 해결하는 데 사용한 네트워크 기능과 격리 도구를 구성하는 방법에 대한 자세한 내용은 Windows 8.x 스토어 개발자 문서의 [네트워크 격리 기능 구성 방법](https://docs.microsoft.com/previous-versions/windows/apps/hh770532(v=win.10))을 참조하세요.
  
## <a name="see-also"></a>참고 항목

- [웹 서비스에 연결](https://docs.microsoft.com/previous-versions/windows/apps/hh761504(v=win.10))
- [네트워크 격리 지침 및 검사 목록](https://docs.microsoft.com/previous-versions/windows/apps/hh770532(v=win.10))
- [빠른 시작: HttpClient를 사용하여 연결](https://docs.microsoft.com/previous-versions/windows/apps/hh781239(v=win.10))
- [HttpClient 처리기 사용 방법](https://docs.microsoft.com/previous-versions/windows/apps/hh781241(v=win.10))
- [HttpClient 연결 보호 방법](https://docs.microsoft.com/previous-versions/windows/apps/hh781240(v=win.10))
- [HttpClient 샘플](https://code.msdn.microsoft.com/windowsapps/HttpClient-sample-55700664)
