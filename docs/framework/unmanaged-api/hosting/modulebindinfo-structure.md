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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f14d3dcaad1cc8cac11599b1647d61df3a793301
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61765182"
---
# <a name="modulebindinfo-structure"></a><span data-ttu-id="98638-102">ModuleBindInfo 구조체</span><span class="sxs-lookup"><span data-stu-id="98638-102">ModuleBindInfo Structure</span></span>
<span data-ttu-id="98638-103">참조 된 모듈 및 포함 된 어셈블리에 대 한 자세한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="98638-103">Provides detailed information about the referenced module and the assembly that contains it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98638-104">구문</span><span class="sxs-lookup"><span data-stu-id="98638-104">Syntax</span></span>  
  
```  
typedef struct _ModuleBindInfo {  
    DWORD    dwAppDomainId;  
    LPCWSTR  lpAssemblyIdentity;  
    LPCWSTR  lpModuleName  
} ModuleBindInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="98638-105">멤버</span><span class="sxs-lookup"><span data-stu-id="98638-105">Members</span></span>  
  
|<span data-ttu-id="98638-106">멤버</span><span class="sxs-lookup"><span data-stu-id="98638-106">Member</span></span>|<span data-ttu-id="98638-107">설명</span><span class="sxs-lookup"><span data-stu-id="98638-107">Description</span></span>|  
|------------|-----------------|  
|`dwAppDomainId`|<span data-ttu-id="98638-108">에 대 한 고유 식별자를 `IStream` 에 대 한 호출에서 반환 하는 [ihostassemblystore:: Providemodule](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md) 메서드는 참조 된 모듈 로드 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="98638-108">A unique identifier for the `IStream` that is returned by a call to the [IHostAssemblyStore::ProvideModule](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md) method from which the referenced module is to be loaded.</span></span>|  
|`lpAssemblyIdentity`|<span data-ttu-id="98638-109">참조 된 모듈을 포함 하는 어셈블리에 대 한 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="98638-109">A unique identifier for the assembly that contains the referenced module.</span></span>|  
|`lpModuleName`|<span data-ttu-id="98638-110">참조 된 모듈의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="98638-110">The name of the referenced module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="98638-111">설명</span><span class="sxs-lookup"><span data-stu-id="98638-111">Remarks</span></span>  
 <span data-ttu-id="98638-112">`ModuleBindInfo` 매개 변수로 전달 됩니다 `IHostAssemblyStore::ProvideModule`합니다.</span><span class="sxs-lookup"><span data-stu-id="98638-112">`ModuleBindInfo` is passed as a parameter to `IHostAssemblyStore::ProvideModule`.</span></span> <span data-ttu-id="98638-113">고유 식별자를 제공 하는 호스트 `dwAppDomainId` 는 CLR (공용 언어 런타임)에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98638-113">The host supplies the unique identifier `dwAppDomainId` to the common language runtime (CLR).</span></span> <span data-ttu-id="98638-114">호출한 후에 [ihostassemblystore:: Provideassembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) 런타임 식별자를 사용 하 여 결정 메서드는 반환 여부를 내용의 `IStream` 매핑되어 있는 합니다.</span><span class="sxs-lookup"><span data-stu-id="98638-114">After a call to the [IHostAssemblyStore::ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) method returns, the runtime uses the identifier to determine whether the contents of the `IStream` have been mapped.</span></span> <span data-ttu-id="98638-115">그렇다면 런타임 스트림에 다시 매핑하는 것이 아니라 기존 복사본을 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="98638-115">If so, the runtime loads the existing copy rather than remapping the stream.</span></span> <span data-ttu-id="98638-116">또한 공용 언어 런타임은이 식별자에 대 한 호출에서 반환 되는 스트림에 대 한 조회 키로는 `IHostAssemblyStore::ProvideAssembly` 메서드.</span><span class="sxs-lookup"><span data-stu-id="98638-116">The runtime also uses this identifier as a lookup key for streams that are returned from calls to the `IHostAssemblyStore::ProvideAssembly` method.</span></span> <span data-ttu-id="98638-117">따라서 식별자 어셈블리 요청 모듈 요청도 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98638-117">Therefore, the identifier must be unique for module requests as well as for assembly requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98638-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="98638-118">Requirements</span></span>  
 <span data-ttu-id="98638-119">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="98638-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98638-120">**헤더:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="98638-120">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="98638-121">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="98638-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="98638-122">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98638-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98638-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="98638-123">See also</span></span>

- [<span data-ttu-id="98638-124">호스팅 구조체</span><span class="sxs-lookup"><span data-stu-id="98638-124">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [<span data-ttu-id="98638-125">AssemblyBindInfo 구조체</span><span class="sxs-lookup"><span data-stu-id="98638-125">AssemblyBindInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/assemblybindinfo-structure.md)
- [<span data-ttu-id="98638-126">ICLRAssemblyIdentityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="98638-126">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="98638-127">ICLRAssemblyReferenceList 인터페이스</span><span class="sxs-lookup"><span data-stu-id="98638-127">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="98638-128">IHostAssemblyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="98638-128">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
