---
description: '자세한 정보: 페더레이션된 시나리오에서 트러스트 프로토콜 혼합'
title: 페더레이션 시나리오에서 혼합 트러스트 프로토콜
ms.date: 03/30/2017
ms.assetid: d7b5fee9-2246-4b09-b8d7-9e63cb817279
ms.openlocfilehash: f882b3728ed791f611a9f71f32840e68d8e17a1d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99733725"
---
# <a name="mixing-trust-protocols-in-federated-scenarios"></a>페더레이션 시나리오에서 혼합 트러스트 프로토콜

페더레이션 클라이언트가 트러스트 버전이 다른 서비스 및 STS(보안 토큰 서비스)와 통신하는 시나리오가 있을 수 있습니다. 서비스 WSDL에 STS와 버전이 다른 WS-Trust 요소가 있는 `RequestSecurityTokenTemplate` 어설션이 포함될 수 있습니다. 이러한 경우 WCF (Windows Communication Foundation) 클라이언트는에서 받은 WS-Trust 요소를 `RequestSecurityTokenTemplate` STS 트러스트 버전과 일치 하도록 변환 합니다. WCF는 표준 바인딩에 대해서만 일치 하지 않는 트러스트 버전을 처리 합니다. WCF에서 인식 하는 모든 표준 알고리즘 매개 변수는 표준 바인딩의 일부입니다. 이 항목에서는 서비스와 STS 간의 다양 한 트러스트 설정에 대 한 WCF 동작에 대해 설명 합니다.  
  
## <a name="rp-feb-2005-and-sts-feb-2005"></a>RP 2005년 2월 및 STS 2005년 2월  

 RP(신뢰 당사자)에 대한 WSDL에서는 `RequestSecurityTokenTemplate` 섹션 내에 다음 요소를 포함합니다.  
  
- `CanonicalizationAlgorithm`  
  
- `EncryptionAlgorithm`  
  
- `EncryptWith`  
  
- `SignWith`  
  
- `KeySize`  
  
- `KeyType`  
  
 클라이언트 구성 파일에는 매개 변수 목록이 포함됩니다.  
  
 WCF는 클라이언트 및 서비스 매개 변수를 구분할 수 없습니다. 모든 매개 변수를 추가 하 고 `RequestSecurityTokenTemplate` (RST)에서 보냅니다.  
  
## <a name="rp-trust-13-and-sts-trust-13"></a>RP Trust 1.3 및 STS Trust 1.3  

 RP에 대한 WSDL에서는 `RequestSecurityTokenTemplate` 섹션 내에 다음 요소를 포함합니다.  
  
- `CanonicalizationAlgorithm`  
  
- `EncryptionAlgorithm`  
  
- `EncryptWith`  
  
- `SignWith`  
  
- `KeySize`  
  
- `KeyType`  
  
- `KeyWrapAlgorithm`  
  
 클라이언트 구성 파일에는 RP에서 지정한 매개 변수를 래핑하는 `secondaryParameters` 요소가 포함됩니다.  
  
 WCF는 `EncryptionAlgorithm` `CanonicalizationAlgorithm` 요소 내에 있는 `KeyWrapAlgorithm` 경우 RST의 최상위 요소에서, 및 요소를 제거 합니다 `SecondaryParameters` . WCF `SecondaryParameters` 는 수정 되지 않은 나가는 RST에 요소를 추가 합니다.  
  
## <a name="rp-trust-feb-2005-and-sts-trust-13"></a>RP Trust 2005년 2월 및 STS Trust 1.3  

 RP에 대한 WSDL에서는 `RequestSecurityTokenTemplate` 섹션 내에 다음 요소를 포함합니다.  
  
- `CanonicalizationAlgorithm`  
  
- `EncryptionAlgorithm`  
  
- `EncryptWith`  
  
- `SignWith`  
  
- `KeySize`  
  
- `KeyType`  
  
 클라이언트 구성 파일에는 매개 변수 목록이 포함됩니다.  
  
 클라이언트 구성 파일에서 WCF는 서비스와 클라이언트 매개 변수를 구분할 수 없습니다. 따라서 WCF는 모든 매개 변수를 신뢰 버전 1.3 네임 스페이스로 변환 합니다.  
  
 WCF는 `KeyType` , `KeySize` 및 요소를 `TokenType` 다음과 같이 처리 합니다.  
  
- WSDL을 다운로드하고, 바인딩을 만들고, RP 매개 변수에서 `KeyType`, `KeySize` 및 `TokenType`을 할당합니다. 그런 다음 클라이언트 구성 파일이 생성됩니다.  
  
- 이제 클라이언트에서 구성 파일의 모든 매개 변수를 수정할 수 있습니다.  
  
- 런타임 중에 WCF는 `AdditionalTokenParameters` `KeyType` 구성 파일을 생성 하는 동안에는를 제외 하 고, 및를 제외 하 고 클라이언트 구성 파일의 섹션에 지정 된 모든 매개 변수를 복사 `KeySize` `TokenType` 합니다.  
  
## <a name="rp-trust-13-and-sts-trust-feb-2005"></a>RP Trust 1.3 및 STS Trust 2005년 2월  

 RP에 대한 WSDL에서는 `RequestSecurityTokenTemplate` 섹션 내에 다음 요소를 포함합니다.  
  
- `CanonicalizationAlgorithm`  
  
- `EncryptionAlgorithm`  
  
- `EncryptWith`  
  
- `SignWith`  
  
- `KeySize`  
  
- `KeyType`  
  
- `KeyWrapAlgorithm`  
  
 클라이언트 구성 파일에는 RP에서 지정한 매개 변수를 래핑하는 `secondaryParamters` 요소가 포함됩니다.  
  
 WCF는 섹션에 지정 된 모든 매개 변수를 `SecondaryParameters` 최상위 RST 요소에 복사 하지만 2005 WS-Trust 네임 스페이스로 변환 하지는 않습니다.
