---
description: '자세히 알아보기: ServiceCredentials'
title: ServiceCredentials
ms.date: 03/30/2017
ms.assetid: 9c780793-4785-46f7-add9-ac1ebeadb614
ms.openlocfilehash: bfd025a8f671a3c5aea537059cde0e751cfa9bb9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99715550"
---
# <a name="servicecredentials"></a><span data-ttu-id="81e09-103">ServiceCredentials</span><span class="sxs-lookup"><span data-stu-id="81e09-103">ServiceCredentials</span></span>

<span data-ttu-id="81e09-104">ServiceCredentials</span><span class="sxs-lookup"><span data-stu-id="81e09-104">ServiceCredentials</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81e09-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="81e09-105">Syntax</span></span>  
  
```csharp
class ServiceCredentials : Behavior  
{  
  string ClientCertificate;  
  string IssuedTokenAuthentication;  
  string Peer;  
  string SecureConversationAuthentication;  
  string ServiceCertificate;  
  string UserNameAuthentication;  
  string WindowsAuthentication;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="81e09-106">메서드</span><span class="sxs-lookup"><span data-stu-id="81e09-106">Methods</span></span>  

 <span data-ttu-id="81e09-107">ServiceCredentials 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="81e09-107">The ServiceCredentials class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="81e09-108">속성</span><span class="sxs-lookup"><span data-stu-id="81e09-108">Properties</span></span>  

 <span data-ttu-id="81e09-109">ServiceCredentials 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81e09-109">The ServiceCredentials class has the following properties:</span></span>  
  
### <a name="clientcertificate"></a><span data-ttu-id="81e09-110">ClientCertificate</span><span class="sxs-lookup"><span data-stu-id="81e09-110">ClientCertificate</span></span>  

 <span data-ttu-id="81e09-111">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="81e09-111">Data type: string</span></span>  
  
 <span data-ttu-id="81e09-112">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="81e09-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="81e09-113">이 서비스에 대한 클라이언트 인증서 인증 및 구축 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="81e09-113">The client certificate authentication and provisioning settings for this service.</span></span>  
  
### <a name="issuedtokenauthentication"></a><span data-ttu-id="81e09-114">IssuedTokenAuthentication</span><span class="sxs-lookup"><span data-stu-id="81e09-114">IssuedTokenAuthentication</span></span>  

 <span data-ttu-id="81e09-115">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="81e09-115">Data type: string</span></span>  
  
 <span data-ttu-id="81e09-116">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="81e09-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="81e09-117">이 서비스에 대해 현재 발급된 토큰 인증 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="81e09-117">The current issued token authentication settings for this service.</span></span>  
  
### <a name="peer"></a><span data-ttu-id="81e09-118">Peer</span><span class="sxs-lookup"><span data-stu-id="81e09-118">Peer</span></span>  

 <span data-ttu-id="81e09-119">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="81e09-119">Data type: string</span></span>  
  
 <span data-ttu-id="81e09-120">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="81e09-120">Access type: Read-only</span></span>  
  
 <span data-ttu-id="81e09-121">피어 전송 엔드포인트가 사용하는 현재 자격 증명 인증 및 구축 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="81e09-121">The current credential authentication and provisioning settings to be used by peer transport endpoints.</span></span>  
  
### <a name="secureconversationauthentication"></a><span data-ttu-id="81e09-122">SecureConversationAuthentication</span><span class="sxs-lookup"><span data-stu-id="81e09-122">SecureConversationAuthentication</span></span>  

 <span data-ttu-id="81e09-123">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="81e09-123">Data type: string</span></span>  
  
 <span data-ttu-id="81e09-124">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="81e09-124">Access type: Read-only</span></span>  
  
 <span data-ttu-id="81e09-125">현재 보안 대화 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="81e09-125">Specifies the current secure conversation settings.</span></span>  
  
### <a name="servicecertificate"></a><span data-ttu-id="81e09-126">ServiceCertificate</span><span class="sxs-lookup"><span data-stu-id="81e09-126">ServiceCertificate</span></span>  

 <span data-ttu-id="81e09-127">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="81e09-127">Data type: string</span></span>  
  
 <span data-ttu-id="81e09-128">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="81e09-128">Access type: Read-only</span></span>  
  
 <span data-ttu-id="81e09-129">이 서비스와 연관된 인증서입니다.</span><span class="sxs-lookup"><span data-stu-id="81e09-129">The certificate associated with this service.</span></span>  
  
### <a name="usernameauthentication"></a><span data-ttu-id="81e09-130">UserNameAuthentication</span><span class="sxs-lookup"><span data-stu-id="81e09-130">UserNameAuthentication</span></span>  

 <span data-ttu-id="81e09-131">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="81e09-131">Data type: string</span></span>  
  
 <span data-ttu-id="81e09-132">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="81e09-132">Access type: Read-only</span></span>  
  
 <span data-ttu-id="81e09-133">이 서비스에 대한 사용자 이름/암호 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="81e09-133">The username/password settings for this service.</span></span>  
  
### <a name="windowsauthentication"></a><span data-ttu-id="81e09-134">WindowsAuthentication</span><span class="sxs-lookup"><span data-stu-id="81e09-134">WindowsAuthentication</span></span>  

 <span data-ttu-id="81e09-135">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="81e09-135">Data type: string</span></span>  
  
 <span data-ttu-id="81e09-136">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="81e09-136">Access type: Read-only</span></span>  
  
 <span data-ttu-id="81e09-137">이 서비스에 대한 Windows 인증 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="81e09-137">The Windows authentication settings for this service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="81e09-138">요구 사항</span><span class="sxs-lookup"><span data-stu-id="81e09-138">Requirements</span></span>  
  
|<span data-ttu-id="81e09-139">MOF</span><span class="sxs-lookup"><span data-stu-id="81e09-139">MOF</span></span>|<span data-ttu-id="81e09-140">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81e09-140">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="81e09-141">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="81e09-141">Namespace</span></span>|<span data-ttu-id="81e09-142">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81e09-142">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="81e09-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="81e09-143">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceCredentials>
