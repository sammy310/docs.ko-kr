---
title: IHostMemoryManager::ReleasedVirtualAddressSpace 메서드
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.ReleasedVirtualAddressSpace
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::ReleasedVirtualAddressSpace
helpviewer_keywords:
- ReleasedVirtualAddressSpace method [.NET Framework hosting]
- IHostMemoryManager::ReleasedVirtualAddressSpace method [.NET Framework hosting]
ms.assetid: d1876601-6ab9-48e1-8ebd-184af1d0cd76
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0acbf4163e98b1171510260c4fac72c3d6f6fb1d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59189289"
---
# <a name="ihostmemorymanagerreleasedvirtualaddressspace-method"></a><span data-ttu-id="2e630-102">IHostMemoryManager::ReleasedVirtualAddressSpace 메서드</span><span class="sxs-lookup"><span data-stu-id="2e630-102">IHostMemoryManager::ReleasedVirtualAddressSpace Method</span></span>
<span data-ttu-id="2e630-103">지정 된 메모리를 사용 하는 CLR (공용 언어 런타임)가 완료 했음을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="2e630-103">Notifies the host that the common language runtime (CLR) has finished using the specified memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e630-104">구문</span><span class="sxs-lookup"><span data-stu-id="2e630-104">Syntax</span></span>  
  
```  
HRESULT ReleasedVirtualAddressSpace(  
    [in] LPVOID startAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2e630-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2e630-105">Parameters</span></span>  
 `startAddress`  
 <span data-ttu-id="2e630-106">[in] 해제할 메모리의 시작 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="2e630-106">[in] Pointer to the starting address of the memory to be released.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2e630-107">설명</span><span class="sxs-lookup"><span data-stu-id="2e630-107">Remarks</span></span>  
 <span data-ttu-id="2e630-108">`ReleasedVirtualAddressSpace` 메서드가 콜백 메서드를 이며 호스팅 응용 프로그램의 작성기에 의해 구현 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e630-108">The `ReleasedVirtualAddressSpace` method is a callback method and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="2e630-109">CLR에서 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e630-109">It is called by the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e630-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2e630-110">Requirements</span></span>  
 <span data-ttu-id="2e630-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="2e630-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e630-112">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2e630-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2e630-113">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="2e630-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="2e630-114">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="2e630-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2e630-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="2e630-115">See also</span></span>

- [<span data-ttu-id="2e630-116">IHostMemoryManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2e630-116">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
