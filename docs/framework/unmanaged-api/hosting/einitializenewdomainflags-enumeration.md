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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 04b0d9989d66888c33de0359e4c93529fcfbf8d1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61628628"
---
# <a name="einitializenewdomainflags-enumeration"></a><span data-ttu-id="8a663-102">EInitializeNewDomainFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="8a663-102">EInitializeNewDomainFlags Enumeration</span></span>
<span data-ttu-id="8a663-103">호스트 응용 프로그램 도메인의 초기화에 대 한 정보를 사용 하 여 런타임에 제공를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a663-103">Enables the host to provide the runtime with information about the initialization of an application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a663-104">구문</span><span class="sxs-lookup"><span data-stu-id="8a663-104">Syntax</span></span>  
  
```  
typedef enum {  
    eInitializeNewDomainFlags_None              = 0x0000,  
    eInitializeNewDomainFlags_NoSecurityChanges = 0x0002  
} EInitializeNewDomainFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="8a663-105">멤버</span><span class="sxs-lookup"><span data-stu-id="8a663-105">Members</span></span>  
  
|<span data-ttu-id="8a663-106">멤버</span><span class="sxs-lookup"><span data-stu-id="8a663-106">Member</span></span>|<span data-ttu-id="8a663-107">설명</span><span class="sxs-lookup"><span data-stu-id="8a663-107">Description</span></span>|  
|------------|-----------------|  
|`eInitializeNewDomainFlags_None`|<span data-ttu-id="8a663-108">플래그가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8a663-108">No flags.</span></span>|  
|`eInitializeNewDomainFlags_NoSecurityChanges`|<span data-ttu-id="8a663-109">알립니다는 CLR (공용 언어 런타임)는 호스트를 변경 하면 안 응용 프로그램 도메인의 보안 상태를 <xref:System.AppDomainManager.InitializeNewDomain%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="8a663-109">Informs the common language runtime (CLR) that the host will not make changes to the security state of the application domain in the <xref:System.AppDomainManager.InitializeNewDomain%2A> method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8a663-110">설명</span><span class="sxs-lookup"><span data-stu-id="8a663-110">Remarks</span></span>  
 <span data-ttu-id="8a663-111">합니다 [iclrdomainmanager:: Setappdomainmanagertype](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md) 형식의 매개 변수를 사용 하는 메서드 `EInitializeNewDomainFlags`합니다.</span><span class="sxs-lookup"><span data-stu-id="8a663-111">The [ICLRDomainManager::SetAppDomainManagerType](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md) method takes a parameter of type `EInitializeNewDomainFlags`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a663-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8a663-112">Requirements</span></span>  
 <span data-ttu-id="8a663-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="8a663-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a663-114">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8a663-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8a663-115">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8a663-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8a663-116">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a663-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a663-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="8a663-117">See also</span></span>

- [<span data-ttu-id="8a663-118">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="8a663-118">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
- [<span data-ttu-id="8a663-119">SetAppDomainManagerType 메서드</span><span class="sxs-lookup"><span data-stu-id="8a663-119">SetAppDomainManagerType Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md)
