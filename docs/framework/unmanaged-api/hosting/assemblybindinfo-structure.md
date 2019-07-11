---
title: AssemblyBindInfo 구조체
ms.date: 03/30/2017
api_name:
- AssemblyBindInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- AssemblyBindInfo
helpviewer_keywords:
- AssemblyBindInfo structure [.NET Framework hosting]
ms.assetid: 6fc01e98-c2e7-49de-ab9f-95937cc89017
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3f4cb71e5ac0afe19e865ffca6fe578ad08f3162
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67773873"
---
# <a name="assemblybindinfo-structure"></a><span data-ttu-id="537f2-102">AssemblyBindInfo 구조체</span><span class="sxs-lookup"><span data-stu-id="537f2-102">AssemblyBindInfo Structure</span></span>
<span data-ttu-id="537f2-103">참조 된 어셈블리에 대 한 자세한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="537f2-103">Provides detailed information about the referenced assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="537f2-104">구문</span><span class="sxs-lookup"><span data-stu-id="537f2-104">Syntax</span></span>  
  
```cpp  
typedef struct _AssemblyBindInfo {  
    DWORD       dwAppDomainId;  
    LPCWSTR     lpReferencedIdentity;  
    LPCWSTR     lpPostPolicyIdentity;  
    DWORD       ePolicyLevel;  
} AssemblyBindInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="537f2-105">멤버</span><span class="sxs-lookup"><span data-stu-id="537f2-105">Members</span></span>  
  
|<span data-ttu-id="537f2-106">멤버</span><span class="sxs-lookup"><span data-stu-id="537f2-106">Member</span></span>|<span data-ttu-id="537f2-107">Description</span><span class="sxs-lookup"><span data-stu-id="537f2-107">Description</span></span>|  
|------------|-----------------|  
|`dwAppDomainId`|<span data-ttu-id="537f2-108">에 대 한 고유 식별자를 `IStream` 에 대 한 호출에서 반환 된 [ihostassemblystore:: Provideassembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md)에 참조 된 어셈블리를 로드 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="537f2-108">A unique identifier for the `IStream` returned by a call to [IHostAssemblyStore::ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md), from which the referenced assembly is to be loaded.</span></span>|  
|`lpReferencedIdentity`|<span data-ttu-id="537f2-109">참조 된 어셈블리에 대 한 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="537f2-109">A unique identifier for the referenced assembly.</span></span>|  
|`lpPostPolicyIdentity`|<span data-ttu-id="537f2-110">바인딩 정책 값을 적용 한 후 참조 된 어셈블리에 대 한 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="537f2-110">The identifier for the referenced assembly after the application of any binding policy values.</span></span>|  
|`ePolicyLevel`|<span data-ttu-id="537f2-111">중 하나는 [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) 어떤 버전 관리 정책이 있는 경우 적용할 참조 된 어셈블리를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="537f2-111">One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values that indicate which versioning policies, if any, should be applied to the referenced assembly.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="537f2-112">설명</span><span class="sxs-lookup"><span data-stu-id="537f2-112">Remarks</span></span>  
 <span data-ttu-id="537f2-113">고유 식별자를 제공 하는 호스트 `dwAppDomainId` 는 CLR (공용 언어 런타임)에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="537f2-113">The host supplies the unique identifier `dwAppDomainId` to the common language runtime (CLR).</span></span> <span data-ttu-id="537f2-114">호출한 후 `IHostAssemblyStore::ProvideAssembly` 런타임 식별자를 사용 하 여 결정을 반환 하는지 여부를 내용의 `IStream` 매핑되어 있는 합니다.</span><span class="sxs-lookup"><span data-stu-id="537f2-114">After a call to `IHostAssemblyStore::ProvideAssembly` returns, the runtime uses the identifier to determine whether the contents of the `IStream` have been mapped.</span></span> <span data-ttu-id="537f2-115">그렇다면 런타임 스트림에 다시 매핑하는 것이 아니라 기존 복사본을 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="537f2-115">If so, the runtime loads the existing copy rather than remapping the stream.</span></span> <span data-ttu-id="537f2-116">런타임에서에서 반환 된 스트림을 대 한 조회 키로이 식별자도 사용에 대 한 호출 [ihostassemblystore:: Providemodule](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="537f2-116">The runtime also uses this identifier as a lookup key for streams returned from calls to [IHostAssemblyStore::ProvideModule](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md).</span></span> <span data-ttu-id="537f2-117">따라서 식별자 어셈블리 요청 및 요청 모듈에 대 한 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="537f2-117">Therefore, the identifier must be unique for module requests and for assembly requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="537f2-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="537f2-118">Requirements</span></span>  
 <span data-ttu-id="537f2-119">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="537f2-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="537f2-120">**헤더:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="537f2-120">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="537f2-121">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="537f2-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="537f2-122">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="537f2-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="537f2-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="537f2-123">See also</span></span>

- [<span data-ttu-id="537f2-124">호스팅 구조체</span><span class="sxs-lookup"><span data-stu-id="537f2-124">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [<span data-ttu-id="537f2-125">ICLRAssemblyIdentityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="537f2-125">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="537f2-126">ICLRAssemblyReferenceList 인터페이스</span><span class="sxs-lookup"><span data-stu-id="537f2-126">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="537f2-127">IHostAssemblyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="537f2-127">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="537f2-128">IHostAssemblyStore 인터페이스</span><span class="sxs-lookup"><span data-stu-id="537f2-128">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
- [<span data-ttu-id="537f2-129">ModuleBindInfo 구조체</span><span class="sxs-lookup"><span data-stu-id="537f2-129">ModuleBindInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md)
