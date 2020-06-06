---
title: <message>의 경우 <claimTypeRequirements>
ms.date: 03/30/2017
ms.assetid: f95c5ecd-abb6-4b77-a6d7-a38727f4a142
ms.openlocfilehash: db6717022bf3af0c4922818668595dd3937e9c71
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "61704409"
---
# <a name="claimtyperequirements-for-message"></a>\<message>의 경우 \<claimTypeRequirements>
필요한 클레임 형식의 컬렉션을 지정합니다.  
  
 컬렉션은 필수 및 선택적 클레임을 지정하는 데 서비스에서 사용됩니다. 이러한 클레임은 클라이언트에서 서비스에 액세스하는 데 사용하는 발급된 토큰에 있어야 합니다. WSDL 게시가 활성화되어 있지만 WCF에서는 발급된 토큰이 지정된 클레임 형식을 포함하지 않아도 되는 경우 서비스는 필수 클레임 형식을 메타데이터로 노출합니다. 서비스에서 필수 클레임 형식을 표시하려면 인증 정책을 사용해야 합니다.  
  
 페더레이션 클라이언트에서 이 컬렉션은 필수 및 선택적 클레임 목록을 포함하며, 이 목록은 발급된 토큰에 대한 클라이언트의 요청에서 보안 토큰 서비스로 전송됩니다.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
