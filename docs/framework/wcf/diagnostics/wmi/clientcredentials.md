---
description: '다음에 대 한 자세한 정보: ClientCredentials'
title: ClientCredentials
ms.date: 03/30/2017
ms.assetid: 41dffd6b-8f14-4fed-aefb-2a1bb168efb3
ms.openlocfilehash: 7b0b5a05e5b61de717567de664079f2ed1e20f6b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99757665"
---
# <a name="clientcredentials"></a><span data-ttu-id="2bb37-103">ClientCredentials</span><span class="sxs-lookup"><span data-stu-id="2bb37-103">ClientCredentials</span></span>

<span data-ttu-id="2bb37-104">ClientCredentials</span><span class="sxs-lookup"><span data-stu-id="2bb37-104">ClientCredentials</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2bb37-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="2bb37-105">Syntax</span></span>  
  
```csharp
class ClientCredentials : Behavior  
{  
  string ClientCertificate;  
  string HttpDigest;  
  string IssuedToken;  
  string Peer;  
  string ServiceCertificate;  
  boolean SupportInteractive;  
  string UserName;  
  string Windows;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="2bb37-106">메서드</span><span class="sxs-lookup"><span data-stu-id="2bb37-106">Methods</span></span>  

 <span data-ttu-id="2bb37-107">ClientCredentials 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2bb37-107">The ClientCredentials class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="2bb37-108">속성</span><span class="sxs-lookup"><span data-stu-id="2bb37-108">Properties</span></span>  

 <span data-ttu-id="2bb37-109">ClientCredentials 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2bb37-109">The ClientCredentials class has the following properties:</span></span>  
  
### <a name="clientcertificate"></a><span data-ttu-id="2bb37-110">ClientCertificate</span><span class="sxs-lookup"><span data-stu-id="2bb37-110">ClientCertificate</span></span>  

 <span data-ttu-id="2bb37-111">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="2bb37-111">Data type: string</span></span>  
  
 <span data-ttu-id="2bb37-112">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="2bb37-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2bb37-113">서비스를 인증하는 데 클라이언트가 사용하는 X.509 인증서입니다.</span><span class="sxs-lookup"><span data-stu-id="2bb37-113">The X.509 certificate the client uses to authenticate to the service.</span></span>  
  
### <a name="httpdigest"></a><span data-ttu-id="2bb37-114">HttpDigest</span><span class="sxs-lookup"><span data-stu-id="2bb37-114">HttpDigest</span></span>  

 <span data-ttu-id="2bb37-115">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="2bb37-115">Data type: string</span></span>  
  
 <span data-ttu-id="2bb37-116">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="2bb37-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2bb37-117">현재 Http 다이제스트 자격 증명입니다.</span><span class="sxs-lookup"><span data-stu-id="2bb37-117">The current Http Digest credential.</span></span>  
  
### <a name="issuedtoken"></a><span data-ttu-id="2bb37-118">IssuedToken</span><span class="sxs-lookup"><span data-stu-id="2bb37-118">IssuedToken</span></span>  

 <span data-ttu-id="2bb37-119">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="2bb37-119">Data type: string</span></span>  
  
 <span data-ttu-id="2bb37-120">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="2bb37-120">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2bb37-121">로컬 보안 토큰 서비스에 연결하기 위해 사용되는 엔드포인트 주소 및 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="2bb37-121">The endpoint address and binding used to contact the local security token service.</span></span>  
  
### <a name="peer"></a><span data-ttu-id="2bb37-122">Peer</span><span class="sxs-lookup"><span data-stu-id="2bb37-122">Peer</span></span>  

 <span data-ttu-id="2bb37-123">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="2bb37-123">Data type: string</span></span>  
  
 <span data-ttu-id="2bb37-124">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="2bb37-124">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2bb37-125">메시의 다른 노드에게 자신을 인증하기 위해 피어 노드가 사용하는 자격 증명입니다.</span><span class="sxs-lookup"><span data-stu-id="2bb37-125">The credentials that the peer node uses to authenticate itself to other nodes in the mesh.</span></span>  
  
### <a name="servicecertificate"></a><span data-ttu-id="2bb37-126">ServiceCertificate</span><span class="sxs-lookup"><span data-stu-id="2bb37-126">ServiceCertificate</span></span>  

 <span data-ttu-id="2bb37-127">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="2bb37-127">Data type: string</span></span>  
  
 <span data-ttu-id="2bb37-128">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="2bb37-128">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2bb37-129">서비스의 X.509 인증서입니다.</span><span class="sxs-lookup"><span data-stu-id="2bb37-129">The service's X.509 certificate.</span></span>  
  
### <a name="supportinteractive"></a><span data-ttu-id="2bb37-130">SupportInteractive</span><span class="sxs-lookup"><span data-stu-id="2bb37-130">SupportInteractive</span></span>  

 <span data-ttu-id="2bb37-131">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="2bb37-131">Data type: boolean</span></span>  
  
 <span data-ttu-id="2bb37-132">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="2bb37-132">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2bb37-133">자격 증명이 대화형 협상을 지원하는지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="2bb37-133">A Boolean value that specifies whether the credential supports interactive negotiation.</span></span>  
  
### <a name="username"></a><span data-ttu-id="2bb37-134">UserName</span><span class="sxs-lookup"><span data-stu-id="2bb37-134">UserName</span></span>  

 <span data-ttu-id="2bb37-135">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="2bb37-135">Data type: string</span></span>  
  
 <span data-ttu-id="2bb37-136">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="2bb37-136">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2bb37-137">서비스에게 자신을 인증하기 위해 클라이언트가 사용하는 사용자 이름 및 암호입니다.</span><span class="sxs-lookup"><span data-stu-id="2bb37-137">The username and password the client uses to authenticate itself to the service.</span></span>  
  
### <a name="windows"></a><span data-ttu-id="2bb37-138">Windows</span><span class="sxs-lookup"><span data-stu-id="2bb37-138">Windows</span></span>  

 <span data-ttu-id="2bb37-139">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="2bb37-139">Data type: string</span></span>  
  
 <span data-ttu-id="2bb37-140">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="2bb37-140">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2bb37-141">서비스에게 자신을 인증하기 위해 클라이언트가 사용하는 Windows 자격 증명입니다.</span><span class="sxs-lookup"><span data-stu-id="2bb37-141">The windows credentials the client uses to authenticate itself to the service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2bb37-142">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2bb37-142">Requirements</span></span>  
  
|<span data-ttu-id="2bb37-143">MOF</span><span class="sxs-lookup"><span data-stu-id="2bb37-143">MOF</span></span>|<span data-ttu-id="2bb37-144">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2bb37-144">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="2bb37-145">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="2bb37-145">Namespace</span></span>|<span data-ttu-id="2bb37-146">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2bb37-146">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2bb37-147">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2bb37-147">See also</span></span>

- <xref:System.ServiceModel.Description.ClientCredentials>
