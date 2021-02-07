---
description: '자세히 알아보기: IHostAssemblyManager:: GetAssemblyStore 메서드'
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
ms.openlocfilehash: 5edfdc5481803ce0dd3a6f8f400b18e3f1600ea8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99709115"
---
# <a name="ihostassemblymanagergetassemblystore-method"></a><span data-ttu-id="791fa-103">IHostAssemblyManager::GetAssemblyStore 메서드</span><span class="sxs-lookup"><span data-stu-id="791fa-103">IHostAssemblyManager::GetAssemblyStore Method</span></span>

<span data-ttu-id="791fa-104">호스트에서 로드 한 어셈블리 목록을 나타내는 [IHostAssemblyStore](ihostassemblystore-interface.md) 에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="791fa-104">Gets an interface pointer to an [IHostAssemblyStore](ihostassemblystore-interface.md) that represents the list of assemblies loaded by the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="791fa-105">구문</span><span class="sxs-lookup"><span data-stu-id="791fa-105">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyStore (  
    [out] IHostAssemblyStore **ppAssemblyStore  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="791fa-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="791fa-106">Parameters</span></span>  

 `ppAssemblyStore`  
 <span data-ttu-id="791fa-107">제한이 인스턴스에 대 한 함수 포인터 `IHostAssemblyStore` 이거나, 호스트에서을 구현 하지 않는 경우 null `IHostAssemblyStore` 입니다.</span><span class="sxs-lookup"><span data-stu-id="791fa-107">[out] A function pointer to an `IHostAssemblyStore` instance, or null, if the host does not implement `IHostAssemblyStore`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="791fa-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="791fa-108">Return Value</span></span>  
  
|<span data-ttu-id="791fa-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="791fa-109">HRESULT</span></span>|<span data-ttu-id="791fa-110">설명</span><span class="sxs-lookup"><span data-stu-id="791fa-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="791fa-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="791fa-111">S_OK</span></span>|<span data-ttu-id="791fa-112">`GetAssemblyStore` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="791fa-112">`GetAssemblyStore` returned successfully.</span></span>|  
|<span data-ttu-id="791fa-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="791fa-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="791fa-114">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="791fa-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="791fa-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="791fa-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="791fa-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="791fa-116">The call timed out.</span></span>|  
|<span data-ttu-id="791fa-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="791fa-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="791fa-118">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="791fa-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="791fa-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="791fa-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="791fa-120">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="791fa-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="791fa-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="791fa-121">E_FAIL</span></span>|<span data-ttu-id="791fa-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="791fa-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="791fa-123">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="791fa-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="791fa-124">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="791fa-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="791fa-125">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="791fa-125">E_NOINTERFACE</span></span>|<span data-ttu-id="791fa-126">호스트는의 구현을 제공 하지 않습니다 `IHostAssemblyStore` .</span><span class="sxs-lookup"><span data-stu-id="791fa-126">The host does not provide an implementation of `IHostAssemblyStore`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="791fa-127">설명</span><span class="sxs-lookup"><span data-stu-id="791fa-127">Remarks</span></span>  

 <span data-ttu-id="791fa-128">`IHostAssemblyStore` 호스트가 CLR과는 독립적으로 어셈블리 및 모듈에 바인딩할 수 있도록 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="791fa-128">`IHostAssemblyStore` provides methods that allow a host to bind to assemblies and modules independently of the CLR.</span></span> <span data-ttu-id="791fa-129">호스트는 일반적으로 어셈블리 저장소를 제공 하 여 파일 시스템 이외의 형식에서 어셈블리를 로드할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="791fa-129">Hosts typically provide assembly stores to allow assemblies to be loaded from formats other than the file system.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="791fa-130">호스트에서을 구현 하지 않는 경우는 `IHostAssemblyStore` `GetAssemblyStore` E_NOINTERFACE HRESULT 값을 반환 해야 하며을 null로 설정 해야 합니다 `ppAssemblyStore` .</span><span class="sxs-lookup"><span data-stu-id="791fa-130">If the host does not implement `IHostAssemblyStore`, `GetAssemblyStore` should return an HRESULT value of E_NOINTERFACE, and should set `ppAssemblyStore` to null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="791fa-131">요구 사항</span><span class="sxs-lookup"><span data-stu-id="791fa-131">Requirements</span></span>  

 <span data-ttu-id="791fa-132">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="791fa-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="791fa-133">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="791fa-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="791fa-134">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="791fa-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="791fa-135">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="791fa-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="791fa-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="791fa-136">See also</span></span>

- [<span data-ttu-id="791fa-137">IHostAssemblyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="791fa-137">IHostAssemblyManager Interface</span></span>](ihostassemblymanager-interface.md)
- [<span data-ttu-id="791fa-138">IHostAssemblyStore 인터페이스</span><span class="sxs-lookup"><span data-stu-id="791fa-138">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)
