---
description: '자세한 정보: 사용자 지정 바인딩을 사용 하는 보안 기능'
title: 사용자 지정 바인딩을 사용하는 보안 기능
ms.date: 03/30/2017
ms.assetid: a2425679-484a-4e6c-9c98-7da7304f1516
ms.openlocfilehash: 0d4298bcb0b22d607c4abb15d879e3b093394bad
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99779844"
---
# <a name="security-capabilities-with-custom-bindings"></a><span data-ttu-id="0a650-103">사용자 지정 바인딩을 사용하는 보안 기능</span><span class="sxs-lookup"><span data-stu-id="0a650-103">Security Capabilities with Custom Bindings</span></span>

<span data-ttu-id="0a650-104">시스템에서 제공되는 바인딩 중 하나를 사용하여 일반적으로 사용되는 보안 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a650-104">You can perform most common security tasks by using one of the system-provided bindings.</span></span> <span data-ttu-id="0a650-105">하지만 좀더 제어가 필요한 경우에는 이 항목의 설명에 따라 <xref:System.ServiceModel.Channels.SecurityBindingElement>를 사용하여 사용자 지정 바인딩을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a650-105">If you need more control, however, you can create a custom binding with a <xref:System.ServiceModel.Channels.SecurityBindingElement>, as explained in these topics.</span></span> <span data-ttu-id="0a650-106">사용자 지정 바인딩에 대 한 자세한 내용은 [사용자 지정 바인딩](../extending/custom-bindings.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0a650-106">For more information about custom bindings, see [Custom Bindings](../extending/custom-bindings.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0a650-107">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="0a650-107">In This Section</span></span>  

 [<span data-ttu-id="0a650-108">SecurityBindingElement 인증 모드</span><span class="sxs-lookup"><span data-stu-id="0a650-108">SecurityBindingElement Authentication Modes</span></span>](securitybindingelement-authentication-modes.md)  
 <span data-ttu-id="0a650-109">사용자 지정 바인딩에서 가능한 인증 모드에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0a650-109">Describes the authentication modes that are possible with a custom binding.</span></span>  
  
 [<span data-ttu-id="0a650-110">방법: SecurityBindingElement를 사용하여 사용자 지정 바인딩 만들기</span><span class="sxs-lookup"><span data-stu-id="0a650-110">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 <span data-ttu-id="0a650-111">보안 요소로 사용자 지정 바인딩을 만드는 기본 단계에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0a650-111">Describes the basic steps for creating a custom binding with a security element.</span></span>  
  
 [<span data-ttu-id="0a650-112">방법: 지정된 인증 모드에 대한 SecurityBindingElement 만들기</span><span class="sxs-lookup"><span data-stu-id="0a650-112">How to: Create a SecurityBindingElement for a Specified Authentication Mode</span></span>](how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)  
 <span data-ttu-id="0a650-113">지정된 인증 모드의 보안 요소를 만드는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0a650-113">Describes how to create a security element for a specified authentication mode.</span></span>  
  
 [<span data-ttu-id="0a650-114">방법: WSFederationHttpBinding에서 보안 세션을 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="0a650-114">How to: Disable Secure Sessions on a WSFederationHttpBinding</span></span>](how-to-disable-secure-sessions-on-a-wsfederationhttpbinding.md)  
 <span data-ttu-id="0a650-115">페더레이션 서비스를 만드는 경우 보안 세션을 비활성화하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0a650-115">Describes how to disable secure sessions when creating a federation service.</span></span>  
  
 [<span data-ttu-id="0a650-116">방법: 메시지 재생 검색 사용</span><span class="sxs-lookup"><span data-stu-id="0a650-116">How to: Enable Message Replay Detection</span></span>](how-to-enable-message-replay-detection.md)  
 <span data-ttu-id="0a650-117">재생 공격이 발생한 경우를 확인하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0a650-117">Describes how to determine when a replay attack occurs.</span></span>  
  
 [<span data-ttu-id="0a650-118">방법: 지원하는 자격 증명 만들기</span><span class="sxs-lookup"><span data-stu-id="0a650-118">How to: Create a Supporting Credential</span></span>](how-to-create-a-supporting-credential.md)  
 <span data-ttu-id="0a650-119">필요한 경우 서비스에 지원하는 자격 증명을 제공하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0a650-119">Describes how to supply a supporting credential to a service, if the service requires it.</span></span>  
  
 [<span data-ttu-id="0a650-120">방법: 서명 확인 설정</span><span class="sxs-lookup"><span data-stu-id="0a650-120">How to: Set Up a Signature Confirmation</span></span>](how-to-set-up-a-signature-confirmation.md)  
 <span data-ttu-id="0a650-121">메시지에 디지털 서명을 할 때 서명을 확인하는 단계에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0a650-121">Describes the steps to confirm signatures when digitally signing messages.</span></span>  
  
 [<span data-ttu-id="0a650-122">방법: 최대 클럭 오차 설정</span><span class="sxs-lookup"><span data-stu-id="0a650-122">How to: Set a Max Clock Skew</span></span>](how-to-set-a-max-clock-skew.md)  
 <span data-ttu-id="0a650-123">서비스와 클라이언트 사이에서 최대로 허용되는 시간 차이를 설정하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0a650-123">Describes how to set the maximum allowed time difference between a service and a client.</span></span>  
  
 [<span data-ttu-id="0a650-124">방법: 디지털 서명 암호화를 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="0a650-124">How to: Disable Encryption of Digital Signatures</span></span>](how-to-disable-encryption-of-digital-signatures.md)  
 <span data-ttu-id="0a650-125">디지털 서명의 암호화를 비활성화할 경우 얻을 수 있는 성능 상의 이점에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0a650-125">Describes how disabling encryption of digital signatures can have a performance benefit.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="0a650-126">참고</span><span class="sxs-lookup"><span data-stu-id="0a650-126">Reference</span></span>  

 <xref:System.ServiceModel.Channels.SecurityBindingElement>  
  
 [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md)  
  
## <a name="related-sections"></a><span data-ttu-id="0a650-127">관련 단원</span><span class="sxs-lookup"><span data-stu-id="0a650-127">Related Sections</span></span>  

 [<span data-ttu-id="0a650-128">보호 수준 이해</span><span class="sxs-lookup"><span data-stu-id="0a650-128">Understanding Protection Level</span></span>](../understanding-protection-level.md)  
  
 [<span data-ttu-id="0a650-129">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="0a650-129">Securing Services and Clients</span></span>](securing-services-and-clients.md)  
  
## <a name="see-also"></a><span data-ttu-id="0a650-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0a650-130">See also</span></span>

- [<span data-ttu-id="0a650-131">바인딩 및 보안</span><span class="sxs-lookup"><span data-stu-id="0a650-131">Bindings and Security</span></span>](bindings-and-security.md)
- [<span data-ttu-id="0a650-132">보안 개요</span><span class="sxs-lookup"><span data-stu-id="0a650-132">Security Overview</span></span>](security-overview.md)
- [<span data-ttu-id="0a650-133">시스템 제공 바인딩</span><span class="sxs-lookup"><span data-stu-id="0a650-133">System-Provided Bindings</span></span>](../system-provided-bindings.md)
