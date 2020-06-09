---
title: WCF에서의 보안 고려 사항
ms.date: 03/30/2017
helpviewer_keywords:
- security [WCF]
- Windows Communication Foundation, security
- WCF, security
ms.assetid: 42055ee0-6d0c-443d-9d89-788dfc345d6d
ms.openlocfilehash: ed0f018e0151e68afeb9a4747bf8a260faa184b1
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84601038"
---
# <a name="security-considerations-in-wcf"></a>WCF에서의 보안 고려 사항
이 단원의 항목에서는 WCF (Windows Communication Foundation) 응용 프로그램을 디자인할 때 고려해 야 할 다양 한 보안 관련 항목을 나열 합니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [정보 공개](information-disclosure.md)  
 정보가 공개되거나 공격 받을 수 있는 다양한 방법과 이러한 문제를 줄이는 방법에 대해 설명합니다.  
  
 [권한 상승](elevation-of-privilege.md)  
 초기에 부여된 권한을 벗어나는 공격자 인증 권한 제공에 따른 영향 및 이에 따른 문제를 줄이는 방법에 대해 설명합니다.  
  
 [서비스 거부](denial-of-service.md)  
 시스템이 메시지를 적절하게 처리할 수 없는 경우 발생되는 결과 및 이에 따른 문제를 줄이는 방법에 대해 설명합니다.  
  
 [변조](tampering.md)  
 메시지 또는 메시지 배달 변경 및 이에 따른 문제를 줄이는 방법에 대해 설명합니다.  
  
 [재생 공격](replay-attacks.md)  
 공격자가 두 당사자 간에 메시지 스트림을 복사하고, 하나 이상의 당사자에게 스트림을 재생하는 경우 발생하는 결과 및 이에 따른 문제를 줄이는 방법에 대해 설명합니다.  
  
 [보안 세션에 대한 보안 고려 사항](security-considerations-for-secure-sessions.md)  
 보안 세션 구현 시 보안에 영향을 주는 다음 항목에 대해 설명합니다.  
  
 [지원 되지 않는 시나리오](unsupported-scenarios.md)  
 특정 측면의 보안을 지원하지 않고 방지하거나 고려해야 할 다양한 시나리오에 대해 설명합니다.  
  
## <a name="reference"></a>참고  
 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a>관련 단원  
 [보안 지침 및 최선의 방법](security-guidance-and-best-practices.md)  
  
## <a name="see-also"></a>참고 항목

- [보안](security.md)
