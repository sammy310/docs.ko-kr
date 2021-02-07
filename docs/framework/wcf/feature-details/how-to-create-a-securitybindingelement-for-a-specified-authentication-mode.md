---
description: '자세히 알아보기: 방법: 지정 된 인증 모드에 대 한 SecurityBindingElement 만들기'
title: '방법: 지정된 인증 모드에 대한 SecurityBindingElement 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a7c7747a-5b8c-463f-8493-7266dac75066
ms.openlocfilehash: cb0831787b6d54daf561fc2750f1efe81bebfb0f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99734479"
---
# <a name="how-to-create-a-securitybindingelement-for-a-specified-authentication-mode"></a>방법: 지정된 인증 모드에 대한 SecurityBindingElement 만들기

WCF (Windows Communication Foundation)는 클라이언트와 서비스가 서로 인증 하는 여러 모드를 제공 합니다. <xref:System.ServiceModel.Channels.SecurityBindingElement> 클래스에 static 메서드를 사용하거나 다음 예제처럼 구성을 통해 이러한 인증 모드의 보안 바인딩 요소를 만들 수 있습니다.  
  
 18 개의 인증 모드에 대 한 자세한 내용은 [SecurityBindingElement 인증 모드](securitybindingelement-authentication-modes.md)를 참조 하세요.  
  
## <a name="example"></a>예제  

 다음 코드 예제에서는 다양한 인증 모드의 바인딩을 만드는 방법을 보여 줍니다.  
  
> [!NOTE]
> <xref:System.ServiceModel.Channels.SecurityBindingElement> 개체의 인스턴스를 만들면 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.KeyType%2A> 및 <xref:System.ServiceModel.Channels.SecurityBindingElement.MessageSecurityVersion%2A> 등의 여러 속성을 변경할 수 없게 됩니다. 이러한 속성에서 `set`을 호출해도 해당 속성은 변경되지 않습니다.  
  
 [!code-csharp[c_CustomBindingsAuthMode#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombindingsauthmode/cs/source.cs#2)]
 [!code-vb[c_CustomBindingsAuthMode#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_custombindingsauthmode/vb/source.vb#2)]  
  
## <a name="see-also"></a>참고 항목

- [SecurityBindingElement 인증 모드](securitybindingelement-authentication-modes.md)
- [방법: SecurityBindingElement를 사용하여 사용자 지정 바인딩 만들기](how-to-create-a-custom-binding-using-the-securitybindingelement.md)
