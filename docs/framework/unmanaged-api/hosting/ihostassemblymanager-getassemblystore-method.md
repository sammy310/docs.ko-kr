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
ms.openlocfilehash: 936ea068f3cc5567a00af5f2bdd5f3d9cd52bc81
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95681186"
---
# <a name="ihostassemblymanagergetassemblystore-method"></a><span data-ttu-id="fd778-102">IHostAssemblyManager::GetAssemblyStore 메서드</span><span class="sxs-lookup"><span data-stu-id="fd778-102">IHostAssemblyManager::GetAssemblyStore Method</span></span>

<span data-ttu-id="fd778-103">호스트에서 로드 한 어셈블리 목록을 나타내는 [IHostAssemblyStore](ihostassemblystore-interface.md) 에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="fd778-103">Gets an interface pointer to an [IHostAssemblyStore](ihostassemblystore-interface.md) that represents the list of assemblies loaded by the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd778-104">구문</span><span class="sxs-lookup"><span data-stu-id="fd778-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyStore (  
    [out] IHostAssemblyStore **ppAssemblyStore  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fd778-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fd778-105">Parameters</span></span>  

 `ppAssemblyStore`  
 <span data-ttu-id="fd778-106">제한이 인스턴스에 대 한 함수 포인터 `IHostAssemblyStore` 이거나, 호스트에서을 구현 하지 않는 경우 null `IHostAssemblyStore` 입니다.</span><span class="sxs-lookup"><span data-stu-id="fd778-106">[out] A function pointer to an `IHostAssemblyStore` instance, or null, if the host does not implement `IHostAssemblyStore`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fd778-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="fd778-107">Return Value</span></span>  
  
|<span data-ttu-id="fd778-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fd778-108">HRESULT</span></span>|<span data-ttu-id="fd778-109">설명</span><span class="sxs-lookup"><span data-stu-id="fd778-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fd778-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="fd778-110">S_OK</span></span>|<span data-ttu-id="fd778-111">`GetAssemblyStore` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fd778-111">`GetAssemblyStore` returned successfully.</span></span>|  
|<span data-ttu-id="fd778-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="fd778-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="fd778-113">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd778-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="fd778-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="fd778-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="fd778-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fd778-115">The call timed out.</span></span>|  
|<span data-ttu-id="fd778-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="fd778-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="fd778-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fd778-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="fd778-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="fd778-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="fd778-119">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="fd778-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="fd778-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fd778-120">E_FAIL</span></span>|<span data-ttu-id="fd778-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="fd778-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="fd778-122">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fd778-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="fd778-123">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd778-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="fd778-124">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="fd778-124">E_NOINTERFACE</span></span>|<span data-ttu-id="fd778-125">호스트는의 구현을 제공 하지 않습니다 `IHostAssemblyStore` .</span><span class="sxs-lookup"><span data-stu-id="fd778-125">The host does not provide an implementation of `IHostAssemblyStore`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fd778-126">설명</span><span class="sxs-lookup"><span data-stu-id="fd778-126">Remarks</span></span>  

 <span data-ttu-id="fd778-127">`IHostAssemblyStore` 호스트가 CLR과는 독립적으로 어셈블리 및 모듈에 바인딩할 수 있도록 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd778-127">`IHostAssemblyStore` provides methods that allow a host to bind to assemblies and modules independently of the CLR.</span></span> <span data-ttu-id="fd778-128">호스트는 일반적으로 어셈블리 저장소를 제공 하 여 파일 시스템 이외의 형식에서 어셈블리를 로드할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd778-128">Hosts typically provide assembly stores to allow assemblies to be loaded from formats other than the file system.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fd778-129">호스트에서을 구현 하지 않는 경우는 `IHostAssemblyStore` `GetAssemblyStore` E_NOINTERFACE HRESULT 값을 반환 해야 하며을 null로 설정 해야 합니다 `ppAssemblyStore` .</span><span class="sxs-lookup"><span data-stu-id="fd778-129">If the host does not implement `IHostAssemblyStore`, `GetAssemblyStore` should return an HRESULT value of E_NOINTERFACE, and should set `ppAssemblyStore` to null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd778-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fd778-130">Requirements</span></span>  

 <span data-ttu-id="fd778-131">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fd778-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd778-132">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="fd778-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fd778-133">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd778-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fd778-134">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd778-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd778-135">참조</span><span class="sxs-lookup"><span data-stu-id="fd778-135">See also</span></span>

- [<span data-ttu-id="fd778-136">IHostAssemblyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fd778-136">IHostAssemblyManager Interface</span></span>](ihostassemblymanager-interface.md)
- [<span data-ttu-id="fd778-137">IHostAssemblyStore 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fd778-137">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)
