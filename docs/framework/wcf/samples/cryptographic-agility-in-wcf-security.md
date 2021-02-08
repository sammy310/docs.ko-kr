---
description: '자세한 정보: WCF 보안의 암호화 민첩성'
title: WCF 보안의 암호화 민첩성
ms.date: 03/30/2017
ms.assetid: c2c549e5-ac19-40c5-b686-8f67f52b6dbf
ms.openlocfilehash: ab46034b16a846f7399220480fc928655d931be0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99778349"
---
# <a name="cryptographic-agility-in-wcf-security"></a>WCF 보안의 암호화 민첩성

이 샘플에서는 Windows Communication Foundation (WCF) 클라이언트 및 서비스에서 암호화 agile 구현을 제공 하도록 표준/사용자 지정 알고리즘을 지정 하는 방법을 보여 줍니다. 이 샘플은 다음 프로젝트로 구성되어 있습니다.

**서비스**

이는 인터페이스를 구현 하 `ICalculator` 고 <xref:System.ServiceModel.WSHttpBinding> 보안 세션 및 신뢰할 수 있는 세션을 사용 하 여 끝점을 보호 하는 자체 호스팅 WCF 서비스입니다. 이 서비스는 사용자 지정 `SecurityAlgorithmSuite` 클래스를 정의하여 메시지 보안에 사용할 암호화 알고리즘을 지정합니다.

**클라이언트**

인증에 성공 하면 서비스에 액세스 하는 WCF 클라이언트입니다. 이 클라이언트는 `ICalculator` 인터페이스에 의해 노출되고 서비스에 의해 구현된 작업을 호출합니다. 또한 클라이언트는 동일한 사용자 지정 `SecurityAlgorithmSuite` 클래스를 정의하여 메시지 보안에 사용할 암호화 알고리즘을 지정합니다.

## <a name="to-use-this-sample"></a>이 샘플을 사용하려면

1. Visual Studio 2012에서 CryptoAgility 솔루션을 엽니다.

2. Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.

3. 파일 탐색기를 열고 \WCF\Basic\Security\CryptoAgility\Service\bin 디렉터리로 이동한 후 service.exe을 마우스 오른쪽 단추로 클릭 하 고 **관리자 권한으로 실행** 을 선택 하 여 관리자 권한으로 service.exe 파일을 실행 합니다.

4. \WCF\Basic\Security\CryptoAgility\Client\bin 디렉터리로 이동하고 client.exe 파일을 정상적으로 실행합니다.

> [!IMPORTANT]
> 컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> 이 디렉터리가 없는 경우 [.NET Framework 4에 대 한 Windows Communication Foundation (wcf) 및 Windows Workflow Foundation (WF) 샘플](https://www.microsoft.com/download/details.aspx?id=21459) 로 이동 하 여 모든 WINDOWS COMMUNICATION FOUNDATION (wcf) 및 샘플을 다운로드 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 합니다. 이 샘플은 다음 디렉터리에 있습니다.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Security\CryptoAgility`

## <a name="see-also"></a>참고 항목

- [Windows Communication Foundation 보안](../feature-details/security.md)
