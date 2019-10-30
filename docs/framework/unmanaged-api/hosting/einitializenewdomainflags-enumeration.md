---
title: EInitializeNewDomainFlags 열거형
ms.date: 03/30/2017
api_name:
- EInitializeNewDomainFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EInitializeNewDomainFlags
helpviewer_keywords:
- EInitializeNewDomainFlags enumeration [.NET Framework hosting]
ms.assetid: 3a120ab2-f5ef-4c9b-8595-d3ed7247c342
ms.openlocfilehash: 3693285e13d0650f7662e2187471027cc4c40704
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129415"
---
# <a name="einitializenewdomainflags-enumeration"></a><span data-ttu-id="776d0-102">EInitializeNewDomainFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="776d0-102">EInitializeNewDomainFlags Enumeration</span></span>
<span data-ttu-id="776d0-103">호스트에서 응용 프로그램 도메인 초기화에 대 한 정보를 런타임에 제공할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="776d0-103">Enables the host to provide the runtime with information about the initialization of an application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="776d0-104">구문</span><span class="sxs-lookup"><span data-stu-id="776d0-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eInitializeNewDomainFlags_None              = 0x0000,  
    eInitializeNewDomainFlags_NoSecurityChanges = 0x0002  
} EInitializeNewDomainFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="776d0-105">멤버</span><span class="sxs-lookup"><span data-stu-id="776d0-105">Members</span></span>  
  
|<span data-ttu-id="776d0-106">멤버</span><span class="sxs-lookup"><span data-stu-id="776d0-106">Member</span></span>|<span data-ttu-id="776d0-107">설명</span><span class="sxs-lookup"><span data-stu-id="776d0-107">Description</span></span>|  
|------------|-----------------|  
|`eInitializeNewDomainFlags_None`|<span data-ttu-id="776d0-108">플래그가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="776d0-108">No flags.</span></span>|  
|`eInitializeNewDomainFlags_NoSecurityChanges`|<span data-ttu-id="776d0-109">호스트가 <xref:System.AppDomainManager.InitializeNewDomain%2A> 메서드에서 응용 프로그램 도메인의 보안 상태를 변경 하지 않는다는 것을 CLR (공용 언어 런타임)에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="776d0-109">Informs the common language runtime (CLR) that the host will not make changes to the security state of the application domain in the <xref:System.AppDomainManager.InitializeNewDomain%2A> method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="776d0-110">주의</span><span class="sxs-lookup"><span data-stu-id="776d0-110">Remarks</span></span>  
 <span data-ttu-id="776d0-111">[ICLRDomainManager:: SetAppDomainManagerType](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md) 메서드는 `EInitializeNewDomainFlags`형식의 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="776d0-111">The [ICLRDomainManager::SetAppDomainManagerType](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md) method takes a parameter of type `EInitializeNewDomainFlags`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="776d0-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="776d0-112">Requirements</span></span>  
 <span data-ttu-id="776d0-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="776d0-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="776d0-114">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="776d0-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="776d0-115">**라이브러리:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="776d0-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="776d0-116">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="776d0-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="776d0-117">참조</span><span class="sxs-lookup"><span data-stu-id="776d0-117">See also</span></span>

- [<span data-ttu-id="776d0-118">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="776d0-118">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
- [<span data-ttu-id="776d0-119">SetAppDomainManagerType 메서드</span><span class="sxs-lookup"><span data-stu-id="776d0-119">SetAppDomainManagerType Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md)
