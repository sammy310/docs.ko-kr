---
title: 사용자 지정 바인딩을 사용하는 보안 기능
ms.date: 03/30/2017
ms.assetid: a2425679-484a-4e6c-9c98-7da7304f1516
ms.openlocfilehash: 1b12907481ccb3f3c5f4b8aaba6ede8ebfa6228a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96288309"
---
# <a name="security-capabilities-with-custom-bindings"></a><span data-ttu-id="72e19-102">사용자 지정 바인딩을 사용하는 보안 기능</span><span class="sxs-lookup"><span data-stu-id="72e19-102">Security Capabilities with Custom Bindings</span></span>

<span data-ttu-id="72e19-103">시스템에서 제공되는 바인딩 중 하나를 사용하여 일반적으로 사용되는 보안 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72e19-103">You can perform most common security tasks by using one of the system-provided bindings.</span></span> <span data-ttu-id="72e19-104">하지만 좀더 제어가 필요한 경우에는 이 항목의 설명에 따라 <xref:System.ServiceModel.Channels.SecurityBindingElement>를 사용하여 사용자 지정 바인딩을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72e19-104">If you need more control, however, you can create a custom binding with a <xref:System.ServiceModel.Channels.SecurityBindingElement>, as explained in these topics.</span></span> <span data-ttu-id="72e19-105">사용자 지정 바인딩에 대 한 자세한 내용은 [사용자 지정 바인딩](../extending/custom-bindings.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="72e19-105">For more information about custom bindings, see [Custom Bindings](../extending/custom-bindings.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="72e19-106">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="72e19-106">In This Section</span></span>  

 [<span data-ttu-id="72e19-107">SecurityBindingElement 인증 모드</span><span class="sxs-lookup"><span data-stu-id="72e19-107">SecurityBindingElement Authentication Modes</span></span>](securitybindingelement-authentication-modes.md)  
 <span data-ttu-id="72e19-108">사용자 지정 바인딩에서 가능한 인증 모드에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="72e19-108">Describes the authentication modes that are possible with a custom binding.</span></span>  
  
 [<span data-ttu-id="72e19-109">방법: SecurityBindingElement를 사용하여 사용자 지정 바인딩 만들기</span><span class="sxs-lookup"><span data-stu-id="72e19-109">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 <span data-ttu-id="72e19-110">보안 요소로 사용자 지정 바인딩을 만드는 기본 단계에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="72e19-110">Describes the basic steps for creating a custom binding with a security element.</span></span>  
  
 [<span data-ttu-id="72e19-111">방법: 지정된 인증 모드에 대한 SecurityBindingElement 만들기</span><span class="sxs-lookup"><span data-stu-id="72e19-111">How to: Create a SecurityBindingElement for a Specified Authentication Mode</span></span>](how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)  
 <span data-ttu-id="72e19-112">지정된 인증 모드의 보안 요소를 만드는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="72e19-112">Describes how to create a security element for a specified authentication mode.</span></span>  
  
 [<span data-ttu-id="72e19-113">방법: WSFederationHttpBinding에서 보안 세션을 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="72e19-113">How to: Disable Secure Sessions on a WSFederationHttpBinding</span></span>](how-to-disable-secure-sessions-on-a-wsfederationhttpbinding.md)  
 <span data-ttu-id="72e19-114">페더레이션 서비스를 만드는 경우 보안 세션을 비활성화하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="72e19-114">Describes how to disable secure sessions when creating a federation service.</span></span>  
  
 [<span data-ttu-id="72e19-115">방법: 메시지 재생 검색 사용</span><span class="sxs-lookup"><span data-stu-id="72e19-115">How to: Enable Message Replay Detection</span></span>](how-to-enable-message-replay-detection.md)  
 <span data-ttu-id="72e19-116">재생 공격이 발생한 경우를 확인하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="72e19-116">Describes how to determine when a replay attack occurs.</span></span>  
  
 [<span data-ttu-id="72e19-117">방법: 지원하는 자격 증명 만들기</span><span class="sxs-lookup"><span data-stu-id="72e19-117">How to: Create a Supporting Credential</span></span>](how-to-create-a-supporting-credential.md)  
 <span data-ttu-id="72e19-118">필요한 경우 서비스에 지원하는 자격 증명을 제공하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="72e19-118">Describes how to supply a supporting credential to a service, if the service requires it.</span></span>  
  
 [<span data-ttu-id="72e19-119">방법: 서명 확인 설정</span><span class="sxs-lookup"><span data-stu-id="72e19-119">How to: Set Up a Signature Confirmation</span></span>](how-to-set-up-a-signature-confirmation.md)  
 <span data-ttu-id="72e19-120">메시지에 디지털 서명을 할 때 서명을 확인하는 단계에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="72e19-120">Describes the steps to confirm signatures when digitally signing messages.</span></span>  
  
 [<span data-ttu-id="72e19-121">방법: 최대 클럭 오차 설정</span><span class="sxs-lookup"><span data-stu-id="72e19-121">How to: Set a Max Clock Skew</span></span>](how-to-set-a-max-clock-skew.md)  
 <span data-ttu-id="72e19-122">서비스와 클라이언트 사이에서 최대로 허용되는 시간 차이를 설정하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="72e19-122">Describes how to set the maximum allowed time difference between a service and a client.</span></span>  
  
 [<span data-ttu-id="72e19-123">방법: 디지털 서명 암호화를 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="72e19-123">How to: Disable Encryption of Digital Signatures</span></span>](how-to-disable-encryption-of-digital-signatures.md)  
 <span data-ttu-id="72e19-124">디지털 서명의 암호화를 비활성화할 경우 얻을 수 있는 성능 상의 이점에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="72e19-124">Describes how disabling encryption of digital signatures can have a performance benefit.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="72e19-125">참고</span><span class="sxs-lookup"><span data-stu-id="72e19-125">Reference</span></span>  

 <xref:System.ServiceModel.Channels.SecurityBindingElement>  
  
 [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md)  
  
## <a name="related-sections"></a><span data-ttu-id="72e19-126">관련 단원</span><span class="sxs-lookup"><span data-stu-id="72e19-126">Related Sections</span></span>  

 [<span data-ttu-id="72e19-127">보호 수준 이해</span><span class="sxs-lookup"><span data-stu-id="72e19-127">Understanding Protection Level</span></span>](../understanding-protection-level.md)  
  
 [<span data-ttu-id="72e19-128">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="72e19-128">Securing Services and Clients</span></span>](securing-services-and-clients.md)  
  
## <a name="see-also"></a><span data-ttu-id="72e19-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="72e19-129">See also</span></span>

- [<span data-ttu-id="72e19-130">바인딩 및 보안</span><span class="sxs-lookup"><span data-stu-id="72e19-130">Bindings and Security</span></span>](bindings-and-security.md)
- [<span data-ttu-id="72e19-131">보안 개요</span><span class="sxs-lookup"><span data-stu-id="72e19-131">Security Overview</span></span>](security-overview.md)
- [<span data-ttu-id="72e19-132">시스템 제공 바인딩</span><span class="sxs-lookup"><span data-stu-id="72e19-132">System-Provided Bindings</span></span>](../system-provided-bindings.md)
