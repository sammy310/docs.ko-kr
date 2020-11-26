---
title: 페더레이션 시나리오에서 혼합 트러스트 프로토콜
ms.date: 03/30/2017
ms.assetid: d7b5fee9-2246-4b09-b8d7-9e63cb817279
ms.openlocfilehash: 5ce178c0b2c83469a26993ce6db2d6c87815543b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96248177"
---
# <a name="mixing-trust-protocols-in-federated-scenarios"></a><span data-ttu-id="31708-102">페더레이션 시나리오에서 혼합 트러스트 프로토콜</span><span class="sxs-lookup"><span data-stu-id="31708-102">Mixing Trust Protocols in Federated Scenarios</span></span>

<span data-ttu-id="31708-103">페더레이션 클라이언트가 트러스트 버전이 다른 서비스 및 STS(보안 토큰 서비스)와 통신하는 시나리오가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31708-103">There may be scenarios in which federated clients communicate with a service and a Security Token Service (STS) that do not have the same trust version.</span></span> <span data-ttu-id="31708-104">서비스 WSDL에 STS와 버전이 다른 WS-Trust 요소가 있는 `RequestSecurityTokenTemplate` 어설션이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31708-104">The service WSDL can contain a `RequestSecurityTokenTemplate` assertion with WS-Trust elements that are of different versions than the STS.</span></span> <span data-ttu-id="31708-105">이러한 경우 WCF (Windows Communication Foundation) 클라이언트는에서 받은 WS-Trust 요소를 `RequestSecurityTokenTemplate` STS 트러스트 버전과 일치 하도록 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="31708-105">In such cases, a Windows Communication Foundation (WCF) client converts the WS-Trust elements received from the `RequestSecurityTokenTemplate` to match the STS trust version.</span></span> <span data-ttu-id="31708-106">WCF는 표준 바인딩에 대해서만 일치 하지 않는 트러스트 버전을 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="31708-106">WCF handles mismatched trust versions only for standard bindings.</span></span> <span data-ttu-id="31708-107">WCF에서 인식 하는 모든 표준 알고리즘 매개 변수는 표준 바인딩의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="31708-107">All standard algorithm parameters that are recognized by WCF are part of the standard binding.</span></span> <span data-ttu-id="31708-108">이 항목에서는 서비스와 STS 간의 다양 한 트러스트 설정에 대 한 WCF 동작에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="31708-108">This topic describes the WCF behavior with various trust settings between the service and the STS.</span></span>  
  
## <a name="rp-feb-2005-and-sts-feb-2005"></a><span data-ttu-id="31708-109">RP 2005년 2월 및 STS 2005년 2월</span><span class="sxs-lookup"><span data-stu-id="31708-109">RP Feb 2005 and STS Feb 2005</span></span>  

 <span data-ttu-id="31708-110">RP(신뢰 당사자)에 대한 WSDL에서는 `RequestSecurityTokenTemplate` 섹션 내에 다음 요소를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="31708-110">The WSDL for Relying Party (RP) contains the following elements within the `RequestSecurityTokenTemplate` section:</span></span>  
  
- `CanonicalizationAlgorithm`  
  
- `EncryptionAlgorithm`  
  
- `EncryptWith`  
  
- `SignWith`  
  
- `KeySize`  
  
- `KeyType`  
  
 <span data-ttu-id="31708-111">클라이언트 구성 파일에는 매개 변수 목록이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="31708-111">The client configuration file contains a list of parameters.</span></span>  
  
 <span data-ttu-id="31708-112">WCF는 클라이언트 및 서비스 매개 변수를 구분할 수 없습니다. 모든 매개 변수를 추가 하 고 `RequestSecurityTokenTemplate` (RST)에서 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="31708-112">WCF cannot differentiate between the client and service parameters; it adds all the parameters and sends them in the `RequestSecurityTokenTemplate` (RST).</span></span>  
  
## <a name="rp-trust-13-and-sts-trust-13"></a><span data-ttu-id="31708-113">RP Trust 1.3 및 STS Trust 1.3</span><span class="sxs-lookup"><span data-stu-id="31708-113">RP Trust 1.3 and STS Trust 1.3</span></span>  

 <span data-ttu-id="31708-114">RP에 대한 WSDL에서는 `RequestSecurityTokenTemplate` 섹션 내에 다음 요소를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="31708-114">The WSDL for RP contains the following elements within the `RequestSecurityTokenTemplate` section:</span></span>  
  
- `CanonicalizationAlgorithm`  
  
- `EncryptionAlgorithm`  
  
- `EncryptWith`  
  
- `SignWith`  
  
- `KeySize`  
  
- `KeyType`  
  
- `KeyWrapAlgorithm`  
  
 <span data-ttu-id="31708-115">클라이언트 구성 파일에는 RP에서 지정한 매개 변수를 래핑하는 `secondaryParameters` 요소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="31708-115">The client configuration file contains a `secondaryParameters` element that wraps the parameters specified by the RP.</span></span>  
  
 <span data-ttu-id="31708-116">WCF는 `EncryptionAlgorithm` `CanonicalizationAlgorithm` 요소 내에 있는 `KeyWrapAlgorithm` 경우 RST의 최상위 요소에서, 및 요소를 제거 합니다 `SecondaryParameters` .</span><span class="sxs-lookup"><span data-stu-id="31708-116">WCF removes the `EncryptionAlgorithm`, `CanonicalizationAlgorithm` and `KeyWrapAlgorithm` elements from the top-level element under the RST if these are present inside the `SecondaryParameters` element.</span></span> <span data-ttu-id="31708-117">WCF `SecondaryParameters` 는 수정 되지 않은 나가는 RST에 요소를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="31708-117">WCF appends the `SecondaryParameters` element to the outgoing RST unmodified.</span></span>  
  
## <a name="rp-trust-feb-2005-and-sts-trust-13"></a><span data-ttu-id="31708-118">RP Trust 2005년 2월 및 STS Trust 1.3</span><span class="sxs-lookup"><span data-stu-id="31708-118">RP Trust Feb 2005 and STS Trust 1.3</span></span>  

 <span data-ttu-id="31708-119">RP에 대한 WSDL에서는 `RequestSecurityTokenTemplate` 섹션 내에 다음 요소를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="31708-119">The WSDL for RP contains the following elements in the `RequestSecurityTokenTemplate` section:</span></span>  
  
- `CanonicalizationAlgorithm`  
  
- `EncryptionAlgorithm`  
  
- `EncryptWith`  
  
- `SignWith`  
  
- `KeySize`  
  
- `KeyType`  
  
 <span data-ttu-id="31708-120">클라이언트 구성 파일에는 매개 변수 목록이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="31708-120">The client configuration file contains a list of parameters.</span></span>  
  
 <span data-ttu-id="31708-121">클라이언트 구성 파일에서 WCF는 서비스와 클라이언트 매개 변수를 구분할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="31708-121">From the client configuration file, WCF cannot differentiate between the service and client parameters.</span></span> <span data-ttu-id="31708-122">따라서 WCF는 모든 매개 변수를 신뢰 버전 1.3 네임 스페이스로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="31708-122">Therefore WCF converts all the parameters to a Trust version 1.3 namespace.</span></span>  
  
 <span data-ttu-id="31708-123">WCF는 `KeyType` , `KeySize` 및 요소를 `TokenType` 다음과 같이 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="31708-123">WCF handles the `KeyType`, `KeySize`, and `TokenType` elements as follows:</span></span>  
  
- <span data-ttu-id="31708-124">WSDL을 다운로드하고, 바인딩을 만들고, RP 매개 변수에서 `KeyType`, `KeySize` 및 `TokenType`을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="31708-124">Download the WSDL, create the binding, and assign `KeyType`, `KeySize`, and `TokenType` from the RP parameters.</span></span> <span data-ttu-id="31708-125">그런 다음 클라이언트 구성 파일이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="31708-125">The client configuration file is then generated.</span></span>  
  
- <span data-ttu-id="31708-126">이제 클라이언트에서 구성 파일의 모든 매개 변수를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31708-126">The client can now change any parameter in the configuration file.</span></span>  
  
- <span data-ttu-id="31708-127">런타임 중에 WCF는 `AdditionalTokenParameters` `KeyType` 구성 파일을 생성 하는 동안에는를 제외 하 고, 및를 제외 하 고 클라이언트 구성 파일의 섹션에 지정 된 모든 매개 변수를 복사 `KeySize` `TokenType` 합니다.</span><span class="sxs-lookup"><span data-stu-id="31708-127">During runtime, WCF copies all parameters specified into the `AdditionalTokenParameters` section of the client configuration file except `KeyType`, `KeySize` and `TokenType`, because these parameters are accounted for during the configuration file generation.</span></span>  
  
## <a name="rp-trust-13-and-sts-trust-feb-2005"></a><span data-ttu-id="31708-128">RP Trust 1.3 및 STS Trust 2005년 2월</span><span class="sxs-lookup"><span data-stu-id="31708-128">RP Trust 1.3 and STS Trust Feb 2005</span></span>  

 <span data-ttu-id="31708-129">RP에 대한 WSDL에서는 `RequestSecurityTokenTemplate` 섹션 내에 다음 요소를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="31708-129">The WSDL for RP contains the following elements in the `RequestSecurityTokenTemplate` section:</span></span>  
  
- `CanonicalizationAlgorithm`  
  
- `EncryptionAlgorithm`  
  
- `EncryptWith`  
  
- `SignWith`  
  
- `KeySize`  
  
- `KeyType`  
  
- `KeyWrapAlgorithm`  
  
 <span data-ttu-id="31708-130">클라이언트 구성 파일에는 RP에서 지정한 매개 변수를 래핑하는 `secondaryParamters` 요소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="31708-130">The client configuration file contains a `secondaryParamters` element that wraps the parameters specified by the RP.</span></span>  
  
 <span data-ttu-id="31708-131">WCF는 섹션에 지정 된 모든 매개 변수를 `SecondaryParameters` 최상위 RST 요소에 복사 하지만 2005 WS-Trust 네임 스페이스로 변환 하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="31708-131">WCF copies all the parameters specified within the `SecondaryParameters` section to the top-level RST element, but does not convert them to the 2005 WS-Trust namespace.</span></span>
