---
title: ModuleBindInfo 구조체
ms.date: 03/30/2017
api_name:
- ModuleBindInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ModuleBindInfo
helpviewer_keywords:
- ModuleBindInfo structure [.NET Framework hosting]
ms.assetid: 632d4adc-dbc9-4ce8-9397-abc3285c1c69
topic_type:
- apiref
ms.openlocfilehash: ae40d8adaae70ccff6e8058858a506267d58873f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133743"
---
# <a name="modulebindinfo-structure"></a><span data-ttu-id="8c0ee-102">ModuleBindInfo 구조체</span><span class="sxs-lookup"><span data-stu-id="8c0ee-102">ModuleBindInfo Structure</span></span>
<span data-ttu-id="8c0ee-103">참조 된 모듈 및이 모듈을 포함 하는 어셈블리에 대 한 자세한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c0ee-103">Provides detailed information about the referenced module and the assembly that contains it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c0ee-104">구문</span><span class="sxs-lookup"><span data-stu-id="8c0ee-104">Syntax</span></span>  
  
```cpp  
typedef struct _ModuleBindInfo {  
    DWORD    dwAppDomainId;  
    LPCWSTR  lpAssemblyIdentity;  
    LPCWSTR  lpModuleName  
} ModuleBindInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="8c0ee-105">멤버</span><span class="sxs-lookup"><span data-stu-id="8c0ee-105">Members</span></span>  
  
|<span data-ttu-id="8c0ee-106">멤버</span><span class="sxs-lookup"><span data-stu-id="8c0ee-106">Member</span></span>|<span data-ttu-id="8c0ee-107">설명</span><span class="sxs-lookup"><span data-stu-id="8c0ee-107">Description</span></span>|  
|------------|-----------------|  
|`dwAppDomainId`|<span data-ttu-id="8c0ee-108">참조 된 모듈을 로드할 [IHostAssemblyStore::P rovidemodule](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md) 메서드를 호출 하 여 반환 되는 `IStream`에 대 한 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="8c0ee-108">A unique identifier for the `IStream` that is returned by a call to the [IHostAssemblyStore::ProvideModule](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md) method from which the referenced module is to be loaded.</span></span>|  
|`lpAssemblyIdentity`|<span data-ttu-id="8c0ee-109">참조 된 모듈이 포함 된 어셈블리에 대 한 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="8c0ee-109">A unique identifier for the assembly that contains the referenced module.</span></span>|  
|`lpModuleName`|<span data-ttu-id="8c0ee-110">참조 된 모듈의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8c0ee-110">The name of the referenced module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8c0ee-111">주의</span><span class="sxs-lookup"><span data-stu-id="8c0ee-111">Remarks</span></span>  
 <span data-ttu-id="8c0ee-112">`ModuleBindInfo`는 `IHostAssemblyStore::ProvideModule`에 대 한 매개 변수로 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c0ee-112">`ModuleBindInfo` is passed as a parameter to `IHostAssemblyStore::ProvideModule`.</span></span> <span data-ttu-id="8c0ee-113">호스트는 CLR (공용 언어 런타임)에 `dwAppDomainId` 고유 식별자를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c0ee-113">The host supplies the unique identifier `dwAppDomainId` to the common language runtime (CLR).</span></span> <span data-ttu-id="8c0ee-114">[IHostAssemblyStore::P rovideassembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) 메서드에 대 한 호출이 반환 된 후에는 런타임에서 식별자를 사용 하 여 `IStream` 내용이 매핑되는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c0ee-114">After a call to the [IHostAssemblyStore::ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) method returns, the runtime uses the identifier to determine whether the contents of the `IStream` have been mapped.</span></span> <span data-ttu-id="8c0ee-115">이 경우 런타임은 스트림을 다시 매핑하지 않고 기존 복사본을 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c0ee-115">If so, the runtime loads the existing copy rather than remapping the stream.</span></span> <span data-ttu-id="8c0ee-116">또한 런타임은 `IHostAssemblyStore::ProvideAssembly` 메서드에 대 한 호출에서 반환 되는 스트림의 조회 키로이 식별자를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c0ee-116">The runtime also uses this identifier as a lookup key for streams that are returned from calls to the `IHostAssemblyStore::ProvideAssembly` method.</span></span> <span data-ttu-id="8c0ee-117">따라서 식별자는 어셈블리 요청 뿐만 아니라 모듈 요청에 대해서만 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c0ee-117">Therefore, the identifier must be unique for module requests as well as for assembly requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c0ee-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8c0ee-118">Requirements</span></span>  
 <span data-ttu-id="8c0ee-119">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8c0ee-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c0ee-120">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="8c0ee-120">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="8c0ee-121">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c0ee-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8c0ee-122">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c0ee-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c0ee-123">참조</span><span class="sxs-lookup"><span data-stu-id="8c0ee-123">See also</span></span>

- [<span data-ttu-id="8c0ee-124">호스팅 구조체</span><span class="sxs-lookup"><span data-stu-id="8c0ee-124">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [<span data-ttu-id="8c0ee-125">AssemblyBindInfo 구조체</span><span class="sxs-lookup"><span data-stu-id="8c0ee-125">AssemblyBindInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/assemblybindinfo-structure.md)
- [<span data-ttu-id="8c0ee-126">ICLRAssemblyIdentityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8c0ee-126">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="8c0ee-127">ICLRAssemblyReferenceList 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8c0ee-127">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="8c0ee-128">IHostAssemblyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8c0ee-128">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
