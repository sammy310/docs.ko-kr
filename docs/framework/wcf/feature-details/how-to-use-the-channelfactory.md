---
title: '방법: ChannelFactory 사용'
description: WCF 클라이언트를 사용 하 여 서비스에 액세스 하기 위해 채널 팩터리를 만드는 방법에 대해 알아봅니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d48f01b5-582b-4c8b-b547-8adddae7e371
ms.openlocfilehash: 7c87026ca4cf7c739f4615da9bc7f0272a382392
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85246664"
---
# <a name="how-to-use-the-channelfactory"></a>방법: ChannelFactory 사용
제네릭 <xref:System.ServiceModel.ChannelFactory%601> 클래스는 둘 이상의 채널을 만드는 데 사용할 수 있는 채널 팩터리를 만들어야 하는 고급 시나리오에서 사용됩니다.  
  
### <a name="to-create-and-use-the-channelfactory-class"></a>ChannelFactory 클래스를 만들고 사용하려면  
  
1. WCF (Windows Communication Foundation) 서비스를 빌드하고 실행 합니다. 자세한 내용은 [서비스 디자인 및 구현](../designing-and-implementing-services.md), [서비스 구성](../configuring-services.md)및 [서비스 호스팅](../hosting-services.md)을 참조 하세요.  
  
2. [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) 를 사용 하 여 클라이언트에 대 한 계약 (인터페이스)을 생성 합니다.  
  
3. 클라이언트 코드에서 <xref:System.ServiceModel.ChannelFactory%601> 클래스를 사용하여 여러 개의 엔드포인트 수신기를 만듭니다.  
  
## <a name="example"></a>예제  
 [!code-csharp[c_HowToUseChannelFactory#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtousechannelfactory/cs/source.cs#1)]
 [!code-vb[c_HowToUseChannelFactory#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtousechannelfactory/vb/source.vb#1)]
