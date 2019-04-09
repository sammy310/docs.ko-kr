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
ms.openlocfilehash: 35e38949ce945d93216daffd3c0d91dad6c8739b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59092775"
---
# <a name="ihostassemblymanagergetassemblystore-method"></a><span data-ttu-id="a1501-102">IHostAssemblyManager::GetAssemblyStore 메서드</span><span class="sxs-lookup"><span data-stu-id="a1501-102">IHostAssemblyManager::GetAssemblyStore Method</span></span>
<span data-ttu-id="a1501-103">한 인터페이스 포인터를 가져옵니다는 [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md) 호스트에 의해 로드 된 어셈블리의 목록을 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="a1501-103">Gets an interface pointer to an [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md) that represents the list of assemblies loaded by the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1501-104">구문</span><span class="sxs-lookup"><span data-stu-id="a1501-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyStore (  
    [out] IHostAssemblyStore **ppAssemblyStore  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a1501-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a1501-105">Parameters</span></span>  
 `ppAssemblyStore`  
 <span data-ttu-id="a1501-106">[out] 에 대 한 함수 포인터를 `IHostAssemblyStore` 인스턴스이거나, null, 호스트를 구현 하지 않는 경우 `IHostAssemblyStore`합니다.</span><span class="sxs-lookup"><span data-stu-id="a1501-106">[out] A function pointer to an `IHostAssemblyStore` instance, or null, if the host does not implement `IHostAssemblyStore`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a1501-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="a1501-107">Return Value</span></span>  
  
|<span data-ttu-id="a1501-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a1501-108">HRESULT</span></span>|<span data-ttu-id="a1501-109">설명</span><span class="sxs-lookup"><span data-stu-id="a1501-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a1501-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="a1501-110">S_OK</span></span>|`GetAssemblyStore` <span data-ttu-id="a1501-111">성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1501-111">returned successfully.</span></span>|  
|<span data-ttu-id="a1501-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a1501-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a1501-113">프로세스에는 CLR (공용 언어 런타임)에 로드 되지 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a1501-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a1501-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a1501-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a1501-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a1501-115">The call timed out.</span></span>|  
|<span data-ttu-id="a1501-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a1501-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a1501-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a1501-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a1501-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a1501-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a1501-119">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1501-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a1501-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a1501-120">E_FAIL</span></span>|<span data-ttu-id="a1501-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="a1501-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a1501-122">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a1501-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a1501-123">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1501-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="a1501-124">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="a1501-124">E_NOINTERFACE</span></span>|<span data-ttu-id="a1501-125">호스트의 구현을 제공 하지 않습니다 `IHostAssemblyStore`합니다.</span><span class="sxs-lookup"><span data-stu-id="a1501-125">The host does not provide an implementation of `IHostAssemblyStore`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a1501-126">설명</span><span class="sxs-lookup"><span data-stu-id="a1501-126">Remarks</span></span>  
 `IHostAssemblyStore` <span data-ttu-id="a1501-127">호스트 어셈블리 및 CLR 독립적으로 모듈을 바인딩하는 데 사용할 수 있는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1501-127">provides methods that allow a host to bind to assemblies and modules independently of the CLR.</span></span> <span data-ttu-id="a1501-128">호스트는 일반적으로 어셈블리를 파일 시스템 이외의 형식에서 로드할 수 있도록 어셈블리 저장소를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1501-128">Hosts typically provide assembly stores to allow assemblies to be loaded from formats other than the file system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a1501-129">호스트 구현 하지 않는 경우 `IHostAssemblyStore`, `GetAssemblyStore` E_NOINTERFACE의 HRESULT 값을 반환 해야 하 고 설정 해야 `ppAssemblyStore` null로 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1501-129">If the host does not implement `IHostAssemblyStore`, `GetAssemblyStore` should return an HRESULT value of E_NOINTERFACE, and should set `ppAssemblyStore` to null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1501-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a1501-130">Requirements</span></span>  
 <span data-ttu-id="a1501-131">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a1501-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1501-132">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a1501-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a1501-133">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="a1501-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="a1501-134">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="a1501-134">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a1501-135">참고자료</span><span class="sxs-lookup"><span data-stu-id="a1501-135">See also</span></span>

- [<span data-ttu-id="a1501-136">IHostAssemblyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a1501-136">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="a1501-137">IHostAssemblyStore 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a1501-137">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
