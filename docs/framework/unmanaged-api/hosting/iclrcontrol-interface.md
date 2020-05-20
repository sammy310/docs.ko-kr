---
title: ICLRControl 인터페이스
ms.date: 03/30/2017
api_name:
- ICLRControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRControl
helpviewer_keywords:
- ICLRControl interface [.NET Framework hosting]
ms.assetid: a24fd905-1fa6-45a0-ad65-e9e2ee58861e
topic_type:
- apiref
ms.openlocfilehash: 54748fdeaf911591c21f4495335e54c777878f04
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615841"
---
# <a name="iclrcontrol-interface"></a><span data-ttu-id="4a31f-102">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4a31f-102">ICLRControl Interface</span></span>
<span data-ttu-id="4a31f-103">호스트가 CLR (공용 언어 런타임)에 대 한 참조를 가져오고의 측면을 구성 하는 데 사용할 수 있는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a31f-103">Provides methods that allow a host to get references to, and configure aspects of, the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4a31f-104">메서드</span><span class="sxs-lookup"><span data-stu-id="4a31f-104">Methods</span></span>  
  
|<span data-ttu-id="4a31f-105">메서드</span><span class="sxs-lookup"><span data-stu-id="4a31f-105">Method</span></span>|<span data-ttu-id="4a31f-106">설명</span><span class="sxs-lookup"><span data-stu-id="4a31f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4a31f-107">GetCLRManager 메서드</span><span class="sxs-lookup"><span data-stu-id="4a31f-107">GetCLRManager Method</span></span>](iclrcontrol-getclrmanager-method.md)|<span data-ttu-id="4a31f-108">호스트가 CLR을 구성 하는 데 사용할 수 있는 관리자 형식의 인스턴스에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4a31f-108">Gets an interface pointer to an instance of any of the manager types the host can use to configure the CLR.</span></span>|  
|[<span data-ttu-id="4a31f-109">SetAppDomainManagerType 메서드</span><span class="sxs-lookup"><span data-stu-id="4a31f-109">SetAppDomainManagerType Method</span></span>](iclrcontrol-setappdomainmanagertype-method.md)|<span data-ttu-id="4a31f-110">에서 파생 된 형식을 <xref:System.AppDomainManager> 응용 프로그램 도메인 관리자의 형식으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a31f-110">Sets a type derived from <xref:System.AppDomainManager> as the type for application domain managers.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4a31f-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4a31f-111">Requirements</span></span>  
 <span data-ttu-id="4a31f-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4a31f-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a31f-113">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="4a31f-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4a31f-114">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a31f-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4a31f-115">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a31f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a31f-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4a31f-116">See also</span></span>

- [<span data-ttu-id="4a31f-117">ICLRAssemblyIdentityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4a31f-117">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="4a31f-118">ICLRDebugManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4a31f-118">ICLRDebugManager Interface</span></span>](iclrdebugmanager-interface.md)
- [<span data-ttu-id="4a31f-119">ICLRGCManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4a31f-119">ICLRGCManager Interface</span></span>](iclrgcmanager-interface.md)
- [<span data-ttu-id="4a31f-120">ICLRHostBindingPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4a31f-120">ICLRHostBindingPolicyManager Interface</span></span>](iclrhostbindingpolicymanager-interface.md)
- [<span data-ttu-id="4a31f-121">ICLRHostProtectionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4a31f-121">ICLRHostProtectionManager Interface</span></span>](iclrhostprotectionmanager-interface.md)
- [<span data-ttu-id="4a31f-122">ICLROnEventManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4a31f-122">ICLROnEventManager Interface</span></span>](iclroneventmanager-interface.md)
- [<span data-ttu-id="4a31f-123">ICLRPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4a31f-123">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
- [<span data-ttu-id="4a31f-124">IHostControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4a31f-124">IHostControl Interface</span></span>](ihostcontrol-interface.md)
- [<span data-ttu-id="4a31f-125">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4a31f-125">Hosting Interfaces</span></span>](hosting-interfaces.md)
