---
title: IHostMemoryManager::AcquiredVirtualAddressSpace 메서드
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.AcquiredVirtualAddressSpace
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::AcquiredVirtualAddressSpace
helpviewer_keywords:
- IHostMemoryManager::AcquiredVirtualAddressSpace method [.NET Framework hosting]
- AcquiredVirtualAddressSpace method [.NET Framework hosting]
ms.assetid: ef2f83c2-127e-4c38-8385-306c03cd2167
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 423fbfc2bda9d3544a5c32b6cd650643209f0e86
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67767234"
---
# <a name="ihostmemorymanageracquiredvirtualaddressspace-method"></a><span data-ttu-id="6ef2e-102">IHostMemoryManager::AcquiredVirtualAddressSpace 메서드</span><span class="sxs-lookup"><span data-stu-id="6ef2e-102">IHostMemoryManager::AcquiredVirtualAddressSpace Method</span></span>
<span data-ttu-id="6ef2e-103">CLR (공용 언어 런타임) 운영 체제에서 지정된 된 메모리를 획득에 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="6ef2e-103">Notifies the host that the common language runtime (CLR) has acquired the specified memory from the operating system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ef2e-104">구문</span><span class="sxs-lookup"><span data-stu-id="6ef2e-104">Syntax</span></span>  
  
```cpp  
HRESULT AcquiredVirtualAddressSpace(  
    [in] LPVOID  startAddress,  
    [in] SIZE_T  size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6ef2e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6ef2e-105">Parameters</span></span>  
 `startAddress`  
 <span data-ttu-id="6ef2e-106">[in] 메모리의 시작 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="6ef2e-106">[in] The starting address of the memory.</span></span>  
  
 `size`  
 <span data-ttu-id="6ef2e-107">[in] 메모리의 바이트 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="6ef2e-107">[in] The size, in bytes, of the memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6ef2e-108">설명</span><span class="sxs-lookup"><span data-stu-id="6ef2e-108">Remarks</span></span>  
 <span data-ttu-id="6ef2e-109">`AcquiredVirtualAddressSpace` 메서드가 콜백 메서드를 이며 호스팅 응용 프로그램의 작성기에 의해 구현 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ef2e-109">The `AcquiredVirtualAddressSpace` method is a callback method and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="6ef2e-110">CLR에서 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ef2e-110">It is called by the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ef2e-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6ef2e-111">Requirements</span></span>  
 <span data-ttu-id="6ef2e-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6ef2e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ef2e-113">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6ef2e-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6ef2e-114">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="6ef2e-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6ef2e-115">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ef2e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ef2e-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="6ef2e-116">See also</span></span>

- [<span data-ttu-id="6ef2e-117">IHostMemoryManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6ef2e-117">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
