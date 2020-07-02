---
title: '방법: 애플리케이션 도메인 구성'
description: .NET에서 애플리케이션 도메인을 구성합니다. AppDomainSetup 클래스를 사용하여 새 애플리케이션 도메인에 대한 구성 정보를 CLR에 제공할 수 있습니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- application domains, configuring
- ApplicationBase property
ms.assetid: 07ea8438-7a34-49f0-a7e8-3d6ff7e4a482
ms.openlocfilehash: 27afcf161bec74143fafb5dceb20597de73e23d4
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2020
ms.locfileid: "85104861"
---
# <a name="how-to-configure-an-application-domain"></a>방법: 애플리케이션 도메인 구성
<xref:System.AppDomainSetup> 클래스를 사용하여 새 애플리케이션 도메인에 대한 구성 정보를 공용 언어 런타임에 제공할 수 있습니다. 사용자 고유의 애플리케이션 도메인을 만들 때 가장 중요한 속성은 <xref:System.AppDomainSetup.ApplicationBase%2A>입니다. 다른 **AppDomainSetup** 속성은 런타임 호스트에서 특정 애플리케이션 도메인을 구성하는 데 주로 사용됩니다.  
  
 **ApplicationBase** 속성은 애플리케이션의 루트 디렉터리를 정의합니다. 런타임에서 형식 요청을 충족해야 하는 경우 **ApplicationBase** 속성에 지정된 디렉터리에서 해당 형식을 포함하는 어셈블리를 찾습니다.  
  
> [!NOTE]
> 새 애플리케이션 도메인은 생성자의 **ApplicationBase** 속성만 상속합니다.  
  
 다음 예제에서는 **AppDomainSetup** 클래스 인스턴스를 만들고, 이 클래스를 사용하여 새 애플리케이션 도메인을 만들고, 콘솔에 정보를 기록한 다음 애플리케이션 도메인을 언로드합니다.  
  
## <a name="example"></a>예제  
 [!code-cpp[ADApplicationBase#2](../../../samples/snippets/cpp/VS_Snippets_CLR/ADApplicationBase/CPP/source2.cpp#2)]
 [!code-csharp[ADApplicationBase#2](../../../samples/snippets/csharp/VS_Snippets_CLR/ADApplicationBase/CS/source2.cs#2)]
 [!code-vb[ADApplicationBase#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/ADApplicationBase/VB/source2.vb#2)]  
  
## <a name="see-also"></a>참조

- [애플리케이션 도메인으로 프로그래밍](application-domains.md#programming-with-application-domains)
- [애플리케이션 도메인 사용](use.md)
