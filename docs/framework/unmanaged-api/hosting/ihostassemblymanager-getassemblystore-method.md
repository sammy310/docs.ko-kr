---
title: IHostAssemblyManager::GetAssemblyStore 메서드
ms.date: 03/30/2017
api_name:
- IHostAssemblyManager.GetAssemblyStore
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyManager::GetAssemblyStore
helpviewer_keywords:
- IHostAssemblyManager::GetAssemblyStore method [.NET Framework hosting]
- GetAssemblyStore method [.NET Framework hosting]
ms.assetid: d0f74593-9bb1-4a11-8096-e29734b20698
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 62965fa928522052b6885769e02c0211ca8d3fe0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937938"
---
# <a name="ihostassemblymanagergetassemblystore-method"></a><span data-ttu-id="9fe58-102">IHostAssemblyManager::GetAssemblyStore 메서드</span><span class="sxs-lookup"><span data-stu-id="9fe58-102">IHostAssemblyManager::GetAssemblyStore Method</span></span>
<span data-ttu-id="9fe58-103">호스트에서 로드 한 어셈블리 목록을 나타내는 [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md) 에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9fe58-103">Gets an interface pointer to an [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md) that represents the list of assemblies loaded by the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9fe58-104">구문</span><span class="sxs-lookup"><span data-stu-id="9fe58-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyStore (  
    [out] IHostAssemblyStore **ppAssemblyStore  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9fe58-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9fe58-105">Parameters</span></span>  
 `ppAssemblyStore`  
 <span data-ttu-id="9fe58-106">제한이 `IHostAssemblyStore` 인스턴스에 대 한 함수 포인터 이거나, 호스트에서을 구현 `IHostAssemblyStore`하지 않는 경우 null입니다.</span><span class="sxs-lookup"><span data-stu-id="9fe58-106">[out] A function pointer to an `IHostAssemblyStore` instance, or null, if the host does not implement `IHostAssemblyStore`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9fe58-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="9fe58-107">Return Value</span></span>  
  
|<span data-ttu-id="9fe58-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9fe58-108">HRESULT</span></span>|<span data-ttu-id="9fe58-109">Description</span><span class="sxs-lookup"><span data-stu-id="9fe58-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9fe58-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="9fe58-110">S_OK</span></span>|<span data-ttu-id="9fe58-111">`GetAssemblyStore`성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9fe58-111">`GetAssemblyStore` returned successfully.</span></span>|  
|<span data-ttu-id="9fe58-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9fe58-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9fe58-113">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fe58-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9fe58-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9fe58-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9fe58-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9fe58-115">The call timed out.</span></span>|  
|<span data-ttu-id="9fe58-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9fe58-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9fe58-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9fe58-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9fe58-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9fe58-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9fe58-119">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="9fe58-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9fe58-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9fe58-120">E_FAIL</span></span>|<span data-ttu-id="9fe58-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="9fe58-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9fe58-122">메서드가 E_FAIL을 반환 하는 경우 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9fe58-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9fe58-123">호스팅 메서드에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fe58-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="9fe58-124">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="9fe58-124">E_NOINTERFACE</span></span>|<span data-ttu-id="9fe58-125">호스트는의 `IHostAssemblyStore`구현을 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9fe58-125">The host does not provide an implementation of `IHostAssemblyStore`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9fe58-126">설명</span><span class="sxs-lookup"><span data-stu-id="9fe58-126">Remarks</span></span>  
 <span data-ttu-id="9fe58-127">`IHostAssemblyStore`호스트가 CLR과는 독립적으로 어셈블리 및 모듈에 바인딩할 수 있도록 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fe58-127">`IHostAssemblyStore` provides methods that allow a host to bind to assemblies and modules independently of the CLR.</span></span> <span data-ttu-id="9fe58-128">호스트는 일반적으로 어셈블리 저장소를 제공 하 여 파일 시스템 이외의 형식에서 어셈블리를 로드할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fe58-128">Hosts typically provide assembly stores to allow assemblies to be loaded from formats other than the file system.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9fe58-129">호스트에서을 `IHostAssemblyStore` `GetAssemblyStore` 구현 하지 않는 경우는 HRESULT 값으로 E_NOINTERFACE을 반환 해야 하며을 null `ppAssemblyStore` 로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fe58-129">If the host does not implement `IHostAssemblyStore`, `GetAssemblyStore` should return an HRESULT value of E_NOINTERFACE, and should set `ppAssemblyStore` to null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9fe58-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9fe58-130">Requirements</span></span>  
 <span data-ttu-id="9fe58-131">**플랫폼** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9fe58-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9fe58-132">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9fe58-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9fe58-133">**라이브러리** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fe58-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9fe58-134">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9fe58-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fe58-135">참고자료</span><span class="sxs-lookup"><span data-stu-id="9fe58-135">See also</span></span>

- [<span data-ttu-id="9fe58-136">IHostAssemblyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9fe58-136">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="9fe58-137">IHostAssemblyStore 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9fe58-137">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
