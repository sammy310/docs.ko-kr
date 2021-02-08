---
description: '자세히 알아보기: NetTcpBinding 응용 프로그램을 피어 채널 응용 프로그램으로 변환'
title: NetTcpBinding 애플리케이션을 피어 채널 애플리케이션으로 변환
ms.date: 03/30/2017
ms.assetid: d4137292-a923-4b8f-8594-42276f2d3ce2
ms.openlocfilehash: 828ffce38fb05acff851c9fe5a6fbb38fffad6aa
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99780416"
---
# <a name="converting-a-nettcpbinding-application-to-a-peer-channel-application"></a>NetTcpBinding 애플리케이션을 피어 채널 애플리케이션으로 변환

연결의 매개 변수를 설명 하는 바인딩을 사용 하 여 WinFX를 사용 하는 클라이언트 간에 연결을 만들 수 있습니다. 피어 투 피어 연결을 사용 하도록 .NET Framework 응용 프로그램을 변환 하려면 클라이언트 연결을 만들 때이 기술을 지 원하는 바인딩이 필요 합니다. 피어 채널은 <xref:System.ServiceModel.NetPeerTcpBinding>과 유사한 방식으로 사용할 수 있는 <xref:System.ServiceModel.NetTcpBinding>이라는 바인딩을 제공합니다. 주요 차이점에는 확인자 서비스 지정과 보안 설정 정의가 포함됩니다.  
  
 애플리케이션에서 기본 확인자와 보안 설정을 사용하는 경우 피어 채널을 사용하도록 일반 클라이언트/서버 기반 애플리케이션을 변환하려면 애플리케이션 구성 파일에서 바인딩의 이름을 &quot;NetTcpBinding&quot;에서 &quot;NetPeerTcpBinding&quot;으로 변경해야 합니다. 애플리케이션 코드베이스는 변경할 필요가 없습니다.  
  
## <a name="see-also"></a>참고 항목

- [피어 채널 애플리케이션 빌드](building-a-peer-channel-application.md)
- [시스템 제공 바인딩](../system-provided-bindings.md)
