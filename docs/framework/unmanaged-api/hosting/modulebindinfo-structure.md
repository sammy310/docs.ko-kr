---
description: '다음에 대 한 자세한 정보: ModuleBindInfo 구조체'
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
ms.openlocfilehash: 0969c0ecc459414336800e8e7da5817ac0c1a8ce
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99679630"
---
# <a name="modulebindinfo-structure"></a><span data-ttu-id="c6e11-103">ModuleBindInfo 구조체</span><span class="sxs-lookup"><span data-stu-id="c6e11-103">ModuleBindInfo Structure</span></span>

<span data-ttu-id="c6e11-104">참조 된 모듈 및이 모듈을 포함 하는 어셈블리에 대 한 자세한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e11-104">Provides detailed information about the referenced module and the assembly that contains it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6e11-105">구문</span><span class="sxs-lookup"><span data-stu-id="c6e11-105">Syntax</span></span>  
  
```cpp  
typedef struct _ModuleBindInfo {  
    DWORD    dwAppDomainId;  
    LPCWSTR  lpAssemblyIdentity;  
    LPCWSTR  lpModuleName  
} ModuleBindInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="c6e11-106">구성원</span><span class="sxs-lookup"><span data-stu-id="c6e11-106">Members</span></span>  
  
|<span data-ttu-id="c6e11-107">멤버</span><span class="sxs-lookup"><span data-stu-id="c6e11-107">Member</span></span>|<span data-ttu-id="c6e11-108">설명</span><span class="sxs-lookup"><span data-stu-id="c6e11-108">Description</span></span>|  
|------------|-----------------|  
|`dwAppDomainId`|<span data-ttu-id="c6e11-109">`IStream`참조 된 모듈을 로드할 [IHostAssemblyStore::P rovidemodule](ihostassemblystore-providemodule-method.md) 메서드에 대 한 호출에서 반환 되는의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="c6e11-109">A unique identifier for the `IStream` that is returned by a call to the [IHostAssemblyStore::ProvideModule](ihostassemblystore-providemodule-method.md) method from which the referenced module is to be loaded.</span></span>|  
|`lpAssemblyIdentity`|<span data-ttu-id="c6e11-110">참조 된 모듈이 포함 된 어셈블리에 대 한 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="c6e11-110">A unique identifier for the assembly that contains the referenced module.</span></span>|  
|`lpModuleName`|<span data-ttu-id="c6e11-111">참조 된 모듈의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c6e11-111">The name of the referenced module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c6e11-112">설명</span><span class="sxs-lookup"><span data-stu-id="c6e11-112">Remarks</span></span>  

 <span data-ttu-id="c6e11-113">`ModuleBindInfo` 는에 대 한 매개 변수로 전달 됩니다 `IHostAssemblyStore::ProvideModule` .</span><span class="sxs-lookup"><span data-stu-id="c6e11-113">`ModuleBindInfo` is passed as a parameter to `IHostAssemblyStore::ProvideModule`.</span></span> <span data-ttu-id="c6e11-114">호스트는 `dwAppDomainId` CLR (공용 언어 런타임)에 고유 식별자를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e11-114">The host supplies the unique identifier `dwAppDomainId` to the common language runtime (CLR).</span></span> <span data-ttu-id="c6e11-115">[IHostAssemblyStore::P rovideassembly](ihostassemblystore-provideassembly-method.md) 메서드에 대 한 호출이 반환 된 후 런타임은 식별자를 사용 하 여의 내용이 매핑 되었는지 여부를 확인 합니다 `IStream` .</span><span class="sxs-lookup"><span data-stu-id="c6e11-115">After a call to the [IHostAssemblyStore::ProvideAssembly](ihostassemblystore-provideassembly-method.md) method returns, the runtime uses the identifier to determine whether the contents of the `IStream` have been mapped.</span></span> <span data-ttu-id="c6e11-116">이 경우 런타임은 스트림을 다시 매핑하지 않고 기존 복사본을 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e11-116">If so, the runtime loads the existing copy rather than remapping the stream.</span></span> <span data-ttu-id="c6e11-117">또한 런타임은 메서드 호출에서 반환 되는 스트림의 조회 키로이 식별자를 사용 합니다 `IHostAssemblyStore::ProvideAssembly` .</span><span class="sxs-lookup"><span data-stu-id="c6e11-117">The runtime also uses this identifier as a lookup key for streams that are returned from calls to the `IHostAssemblyStore::ProvideAssembly` method.</span></span> <span data-ttu-id="c6e11-118">따라서 식별자는 어셈블리 요청 뿐만 아니라 모듈 요청에 대해서만 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e11-118">Therefore, the identifier must be unique for module requests as well as for assembly requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6e11-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c6e11-119">Requirements</span></span>  

 <span data-ttu-id="c6e11-120">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c6e11-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6e11-121">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="c6e11-121">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="c6e11-122">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6e11-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c6e11-123">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6e11-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6e11-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c6e11-124">See also</span></span>

- [<span data-ttu-id="c6e11-125">호스팅 구조체</span><span class="sxs-lookup"><span data-stu-id="c6e11-125">Hosting Structures</span></span>](hosting-structures.md)
- [<span data-ttu-id="c6e11-126">AssemblyBindInfo 구조체</span><span class="sxs-lookup"><span data-stu-id="c6e11-126">AssemblyBindInfo Structure</span></span>](assemblybindinfo-structure.md)
- [<span data-ttu-id="c6e11-127">ICLRAssemblyIdentityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c6e11-127">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="c6e11-128">ICLRAssemblyReferenceList 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c6e11-128">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="c6e11-129">IHostAssemblyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c6e11-129">IHostAssemblyManager Interface</span></span>](ihostassemblymanager-interface.md)
