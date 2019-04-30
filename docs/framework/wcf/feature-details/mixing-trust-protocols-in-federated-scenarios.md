---
title: 페더레이션 시나리오에서 혼합 트러스트 프로토콜
ms.date: 03/30/2017
ms.assetid: d7b5fee9-2246-4b09-b8d7-9e63cb817279
ms.openlocfilehash: ce5c3a1875d84d98068dcc78d8346a88bc0b28f3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62046693"
---
# <a name="mixing-trust-protocols-in-federated-scenarios"></a><span data-ttu-id="585f1-102">페더레이션 시나리오에서 혼합 트러스트 프로토콜</span><span class="sxs-lookup"><span data-stu-id="585f1-102">Mixing Trust Protocols in Federated Scenarios</span></span>
<span data-ttu-id="585f1-103">페더레이션 클라이언트가 트러스트 버전이 다른 서비스 및 STS(보안 토큰 서비스)와 통신하는 시나리오가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="585f1-103">There may be scenarios in which federated clients communicate with a service and a Security Token Service (STS) that do not have the same trust version.</span></span> <span data-ttu-id="585f1-104">서비스 WSDL에 STS와 버전이 다른 WS-Trust 요소가 있는 `RequestSecurityTokenTemplate` 어설션이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="585f1-104">The service WSDL can contain a `RequestSecurityTokenTemplate` assertion with WS-Trust elements that are of different versions than the STS.</span></span> <span data-ttu-id="585f1-105">이러한 경우 Windows Communication Foundation (WCF) 클라이언트에서 수신한 Ws-trust 요소를 변환 합니다.는 `RequestSecurityTokenTemplate` STS 트러스트 버전과 일치 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="585f1-105">In such cases, a Windows Communication Foundation (WCF) client converts the WS-Trust elements received from the `RequestSecurityTokenTemplate` to match the STS trust version.</span></span> <span data-ttu-id="585f1-106">WCF에는 일치 하지 않는 트러스트 버전을 표준 바인딩 용 으로만 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="585f1-106">WCF handles mismatched trust versions only for standard bindings.</span></span> <span data-ttu-id="585f1-107">WCF에서 인식 되는 모든 표준 알고리즘 매개 변수를 사용 하면 표준 바인딩의 일부인 합니다.</span><span class="sxs-lookup"><span data-stu-id="585f1-107">All standard algorithm parameters that are recognized by WCF are part of the standard binding.</span></span> <span data-ttu-id="585f1-108">이 항목에서는 서비스와 STS 간의 다양 한 트러스트 설정 사용 하 여 WCF 동작을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="585f1-108">This topic describes the WCF behavior with various trust settings between the service and the STS.</span></span>  
  
## <a name="rp-feb-2005-and-sts-feb-2005"></a><span data-ttu-id="585f1-109">RP 2005년 2월 및 STS 2005년 2월</span><span class="sxs-lookup"><span data-stu-id="585f1-109">RP Feb 2005 and STS Feb 2005</span></span>  
 <span data-ttu-id="585f1-110">RP(신뢰 당사자)에 대한 WSDL에서는 `RequestSecurityTokenTemplate` 섹션 내에 다음 요소를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="585f1-110">The WSDL for Relying Party (RP) contains the following elements within the `RequestSecurityTokenTemplate` section:</span></span>  
  
- `CanonicalizationAlgorithm`  
  
- `EncryptionAlgorithm`  
  
- `EncryptWith`  
  
- `SignWith`  
  
- `KeySize`  
  
- `KeyType`  
  
 <span data-ttu-id="585f1-111">클라이언트 구성 파일에는 매개 변수 목록이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="585f1-111">The client configuration file contains a list of parameters.</span></span>  
  
 <span data-ttu-id="585f1-112">WCF는 클라이언트 및 서비스 매개 변수를 구분할 수 없습니다. 모든 매개 변수를 추가 하 고 보냅니다는 `RequestSecurityTokenTemplate` (RST).</span><span class="sxs-lookup"><span data-stu-id="585f1-112">WCF cannot differentiate between the client and service parameters; it adds all the parameters and sends them in the `RequestSecurityTokenTemplate` (RST).</span></span>  
  
## <a name="rp-trust-13-and-sts-trust-13"></a><span data-ttu-id="585f1-113">RP Trust 1.3 및 STS Trust 1.3</span><span class="sxs-lookup"><span data-stu-id="585f1-113">RP Trust 1.3 and STS Trust 1.3</span></span>  
 <span data-ttu-id="585f1-114">RP에 대한 WSDL에서는 `RequestSecurityTokenTemplate` 섹션 내에 다음 요소를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="585f1-114">The WSDL for RP contains the following elements within the `RequestSecurityTokenTemplate` section:</span></span>  
  
- `CanonicalizationAlgorithm`  
  
- `EncryptionAlgorithm`  
  
- `EncryptWith`  
  
- `SignWith`  
  
- `KeySize`  
  
- `KeyType`  
  
- `KeyWrapAlgorithm`  
  
 <span data-ttu-id="585f1-115">클라이언트 구성 파일에는 RP에서 지정한 매개 변수를 래핑하는 `secondaryParameters` 요소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="585f1-115">The client configuration file contains a `secondaryParameters` element that wraps the parameters specified by the RP.</span></span>  
  
 <span data-ttu-id="585f1-116">WCF 제거 합니다 `EncryptionAlgorithm`, `CanonicalizationAlgorithm` 및 `KeyWrapAlgorithm` 요소 내에 있는 경우 rst의 최상위 요소에서는 `SecondaryParameters` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="585f1-116">WCF removes the `EncryptionAlgorithm`, `CanonicalizationAlgorithm` and `KeyWrapAlgorithm` elements from the top-level element under the RST if these are present inside the `SecondaryParameters` element.</span></span> <span data-ttu-id="585f1-117">WCF 추가 `SecondaryParameters` 수정 되지 않은 나가는 RST 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="585f1-117">WCF appends the `SecondaryParameters` element to the outgoing RST unmodified.</span></span>  
  
## <a name="rp-trust-feb-2005-and-sts-trust-13"></a><span data-ttu-id="585f1-118">RP Trust 2005년 2월 및 STS Trust 1.3</span><span class="sxs-lookup"><span data-stu-id="585f1-118">RP Trust Feb 2005 and STS Trust 1.3</span></span>  
 <span data-ttu-id="585f1-119">RP에 대한 WSDL에서는 `RequestSecurityTokenTemplate` 섹션 내에 다음 요소를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="585f1-119">The WSDL for RP contains the following elements in the `RequestSecurityTokenTemplate` section:</span></span>  
  
- `CanonicalizationAlgorithm`  
  
- `EncryptionAlgorithm`  
  
- `EncryptWith`  
  
- `SignWith`  
  
- `KeySize`  
  
- `KeyType`  
  
 <span data-ttu-id="585f1-120">클라이언트 구성 파일에는 매개 변수 목록이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="585f1-120">The client configuration file contains a list of parameters.</span></span>  
  
 <span data-ttu-id="585f1-121">클라이언트 구성 파일에서 WCF 서비스 및 클라이언트 매개 변수를 구분할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="585f1-121">From the client configuration file, WCF cannot differentiate between the service and client parameters.</span></span> <span data-ttu-id="585f1-122">따라서 WCF 트러스트 버전 1.3 네임 스페이스에 모든 매개 변수를 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="585f1-122">Therefore WCF converts all the parameters to a Trust version 1.3 namespace.</span></span>  
  
 <span data-ttu-id="585f1-123">WCF 핸들은 `KeyType`, `KeySize`, 및 `TokenType` 다음과 같은 요소:</span><span class="sxs-lookup"><span data-stu-id="585f1-123">WCF handles the `KeyType`, `KeySize`, and `TokenType` elements as follows:</span></span>  
  
- <span data-ttu-id="585f1-124">WSDL을 다운로드하고, 바인딩을 만들고, RP 매개 변수에서 `KeyType`, `KeySize` 및 `TokenType`을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="585f1-124">Download the WSDL, create the binding, and assign `KeyType`, `KeySize`, and `TokenType` from the RP parameters.</span></span> <span data-ttu-id="585f1-125">그런 다음 클라이언트 구성 파일이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="585f1-125">The client configuration file is then generated.</span></span>  
  
- <span data-ttu-id="585f1-126">이제 클라이언트에서 구성 파일의 모든 매개 변수를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="585f1-126">The client can now change any parameter in the configuration file.</span></span>  
  
- <span data-ttu-id="585f1-127">WCF 런타임 중에 지정 된 모든 매개 변수를 복사 합니다 `AdditionalTokenParameters` 제외 하 고 클라이언트 구성 파일의 섹션 `KeyType`, `KeySize` 고 `TokenType`이므로 이러한 매개 변수는 구성 파일 하는 동안에 필요 세대입니다.</span><span class="sxs-lookup"><span data-stu-id="585f1-127">During runtime, WCF copies all parameters specified into the `AdditionalTokenParameters` section of the client configuration file except `KeyType`, `KeySize` and `TokenType`, because these parameters are accounted for during the configuration file generation.</span></span>  
  
## <a name="rp-trust-13-and-sts-trust-feb-2005"></a><span data-ttu-id="585f1-128">RP Trust 1.3 및 STS Trust 2005년 2월</span><span class="sxs-lookup"><span data-stu-id="585f1-128">RP Trust 1.3 and STS Trust Feb 2005</span></span>  
 <span data-ttu-id="585f1-129">RP에 대한 WSDL에서는 `RequestSecurityTokenTemplate` 섹션 내에 다음 요소를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="585f1-129">The WSDL for RP contains the following elements in the `RequestSecurityTokenTemplate` section:</span></span>  
  
- `CanonicalizationAlgorithm`  
  
- `EncryptionAlgorithm`  
  
- `EncryptWith`  
  
- `SignWith`  
  
- `KeySize`  
  
- `KeyType`  
  
- `KeyWrapAlgorithm`  
  
 <span data-ttu-id="585f1-130">클라이언트 구성 파일에는 RP에서 지정한 매개 변수를 래핑하는 `secondaryParamters` 요소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="585f1-130">The client configuration file contains a `secondaryParamters` element that wraps the parameters specified by the RP.</span></span>  
  
 <span data-ttu-id="585f1-131">내에 지정 된 모든 매개 변수를 복사 하는 WCF는 `SecondaryParameters` 최상위 RST 요소로 섹션 하지만 2005 Ws-trust 네임 스페이스를 변환 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="585f1-131">WCF copies all the parameters specified within the `SecondaryParameters` section to the top-level RST element, but does not convert them to the 2005 WS-Trust namespace.</span></span>
