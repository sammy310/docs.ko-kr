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
ms.openlocfilehash: 615637813b08629aaea74b23fa2737f52d61bafb
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616920"
---
# <a name="assemblybindinfo-structure"></a><span data-ttu-id="8eaa8-102">AssemblyBindInfo 구조체</span><span class="sxs-lookup"><span data-stu-id="8eaa8-102">AssemblyBindInfo Structure</span></span>
<span data-ttu-id="8eaa8-103">참조 된 어셈블리에 대 한 자세한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8eaa8-103">Provides detailed information about the referenced assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8eaa8-104">구문</span><span class="sxs-lookup"><span data-stu-id="8eaa8-104">Syntax</span></span>  
  
```cpp  
typedef struct _AssemblyBindInfo {  
    DWORD       dwAppDomainId;  
    LPCWSTR     lpReferencedIdentity;  
    LPCWSTR     lpPostPolicyIdentity;  
    DWORD       ePolicyLevel;  
} AssemblyBindInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="8eaa8-105">멤버</span><span class="sxs-lookup"><span data-stu-id="8eaa8-105">Members</span></span>  
  
|<span data-ttu-id="8eaa8-106">멤버</span><span class="sxs-lookup"><span data-stu-id="8eaa8-106">Member</span></span>|<span data-ttu-id="8eaa8-107">설명</span><span class="sxs-lookup"><span data-stu-id="8eaa8-107">Description</span></span>|  
|------------|-----------------|  
|`dwAppDomainId`|<span data-ttu-id="8eaa8-108">`IStream`참조 된 어셈블리를 로드할 [IHostAssemblyStore::P rovideassembly](ihostassemblystore-provideassembly-method.md)에 대 한 호출에서 반환 된의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="8eaa8-108">A unique identifier for the `IStream` returned by a call to [IHostAssemblyStore::ProvideAssembly](ihostassemblystore-provideassembly-method.md), from which the referenced assembly is to be loaded.</span></span>|  
|`lpReferencedIdentity`|<span data-ttu-id="8eaa8-109">참조 된 어셈블리에 대 한 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="8eaa8-109">A unique identifier for the referenced assembly.</span></span>|  
|`lpPostPolicyIdentity`|<span data-ttu-id="8eaa8-110">바인딩 정책 값을 적용 한 후 참조 된 어셈블리의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="8eaa8-110">The identifier for the referenced assembly after the application of any binding policy values.</span></span>|  
|`ePolicyLevel`|<span data-ttu-id="8eaa8-111">참조 된 어셈블리에 적용 해야 하는 버전 관리 정책 (있는 경우)을 나타내는 [EPolicyAction](epolicyaction-enumeration.md) 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="8eaa8-111">One of the [EPolicyAction](epolicyaction-enumeration.md) values that indicate which versioning policies, if any, should be applied to the referenced assembly.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8eaa8-112">설명</span><span class="sxs-lookup"><span data-stu-id="8eaa8-112">Remarks</span></span>  
 <span data-ttu-id="8eaa8-113">호스트는 `dwAppDomainId` CLR (공용 언어 런타임)에 고유 식별자를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8eaa8-113">The host supplies the unique identifier `dwAppDomainId` to the common language runtime (CLR).</span></span> <span data-ttu-id="8eaa8-114">에 대 한 호출이 `IHostAssemblyStore::ProvideAssembly` 반환 된 후 런타임은 식별자를 사용 하 여의 내용이 매핑 되었는지 여부를 확인 합니다 `IStream` .</span><span class="sxs-lookup"><span data-stu-id="8eaa8-114">After a call to `IHostAssemblyStore::ProvideAssembly` returns, the runtime uses the identifier to determine whether the contents of the `IStream` have been mapped.</span></span> <span data-ttu-id="8eaa8-115">이 경우 런타임은 스트림을 다시 매핑하지 않고 기존 복사본을 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="8eaa8-115">If so, the runtime loads the existing copy rather than remapping the stream.</span></span> <span data-ttu-id="8eaa8-116">또한 런타임은 [IHostAssemblyStore::P rovidemodule](ihostassemblystore-providemodule-method.md)에 대 한 호출에서 반환 되는 스트림의 조회 키로이 식별자를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8eaa8-116">The runtime also uses this identifier as a lookup key for streams returned from calls to [IHostAssemblyStore::ProvideModule](ihostassemblystore-providemodule-method.md).</span></span> <span data-ttu-id="8eaa8-117">따라서 식별자는 모듈 요청 및 어셈블리 요청에 대해 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8eaa8-117">Therefore, the identifier must be unique for module requests and for assembly requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8eaa8-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8eaa8-118">Requirements</span></span>  
 <span data-ttu-id="8eaa8-119">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8eaa8-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8eaa8-120">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="8eaa8-120">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="8eaa8-121">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8eaa8-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8eaa8-122">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8eaa8-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8eaa8-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8eaa8-123">See also</span></span>

- [<span data-ttu-id="8eaa8-124">호스팅 구조체</span><span class="sxs-lookup"><span data-stu-id="8eaa8-124">Hosting Structures</span></span>](hosting-structures.md)
- [<span data-ttu-id="8eaa8-125">ICLRAssemblyIdentityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8eaa8-125">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="8eaa8-126">ICLRAssemblyReferenceList 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8eaa8-126">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="8eaa8-127">IHostAssemblyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8eaa8-127">IHostAssemblyManager Interface</span></span>](ihostassemblymanager-interface.md)
- [<span data-ttu-id="8eaa8-128">IHostAssemblyStore 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8eaa8-128">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)
- [<span data-ttu-id="8eaa8-129">ModuleBindInfo 구조체</span><span class="sxs-lookup"><span data-stu-id="8eaa8-129">ModuleBindInfo Structure</span></span>](modulebindinfo-structure.md)
