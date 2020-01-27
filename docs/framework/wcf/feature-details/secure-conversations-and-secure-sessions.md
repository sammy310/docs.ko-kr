---
title: 보안 대화 및 보안 세션
ms.date: 03/30/2017
ms.assetid: 48cb104a-532d-40ae-aa57-769dae103fda
ms.openlocfilehash: 887b2e6e6553a910de046950514869907519cf35
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746455"
---
# <a name="secure-conversations-and-secure-sessions"></a>보안 대화 및 보안 세션
WCF (Windows Communication Foundation) 기능은 서로 인증 하 고 암호화 및 디지털 서명 프로세스에 동의 하는 두 끝점 사이에 보안 세션을 설정 하는 기능입니다. 예를 들어, 서비스 엔드포인트는 인증을 위해 X.509 인증서에 기반한 보안 토큰을 보낼 클라이언트 엔드포인트가 필요할 수 있습니다. 클라이언트가 인증되면 서비스 엔드포인트는 세션 내의 모든 후속 메시지 보안을 설정하는 데 사용되는 클라이언트에게 SCT(보안 컨텍스트 토큰)를 다시 반환합니다. 이 보안 세션을 설정하면 SCT에 대칭 키가 포함되기 때문에 두 개의 엔드포인트 간에 교환되는 메시지 집합이 훨씬 효율적일 수 있습니다. X.509 인증서가 기준으로 하는 비대칭 키는 디지털 서명을 생성하거나 데이터 집합을 암호화할 때 대칭 키보다 훨씬 더 많은 계산 능력이 필요합니다.  
  
 부트스트랩 정책 ( [ws-securitypolicy](https://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/ws-securitypolicy-1.2-spec-os.html) 표준의 섹션 6.2.7에 정의 됨)에는 채널을 보호 하 고 RST/SCT 및 RSTR/sct exchange 이전에 클라이언트를 인증 하는 데 사용 되는 메시지 보안 어설션이 포함 됩니다. 특정 WCF 표준 바인딩에는 보안 대화가 사용 되는지 여부를 제어 하는 `Security.Message.EstablishSecurityContext` 속성이 있습니다. 사용자 지정 바인딩을 사용 하는 경우 부트스트랩은 구성 파일에서 [\<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) 를 통해 또는 코드에서 <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSecureConversationBindingElement%2A>를 호출 하 여 보안 바인딩 요소를 중첩 하 여 표시 됩니다.  
  
 세션에 대 한 자세한 내용은 참조 하십시오 [를 사용 하 여 세션](../../../../docs/framework/wcf/using-sessions.md)합니다.  
  
## <a name="see-also"></a>참조

- [세션, 인스턴스 및 동시성](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)
- [방법: 세션이 필요한 서비스 만들기](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-that-requires-sessions.md)
