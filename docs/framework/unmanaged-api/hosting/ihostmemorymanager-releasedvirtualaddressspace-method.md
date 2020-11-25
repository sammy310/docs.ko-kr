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
ms.openlocfilehash: 8a875d59d270f087ce22079830818a9205309cc5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731295"
---
# <a name="ihostmemorymanagerreleasedvirtualaddressspace-method"></a><span data-ttu-id="cc60b-102">IHostMemoryManager::ReleasedVirtualAddressSpace 메서드</span><span class="sxs-lookup"><span data-stu-id="cc60b-102">IHostMemoryManager::ReleasedVirtualAddressSpace Method</span></span>

<span data-ttu-id="cc60b-103">지정 된 메모리를 사용 하 여 CLR (공용 언어 런타임)이 완료 되었음을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="cc60b-103">Notifies the host that the common language runtime (CLR) has finished using the specified memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc60b-104">구문</span><span class="sxs-lookup"><span data-stu-id="cc60b-104">Syntax</span></span>  
  
```cpp  
HRESULT ReleasedVirtualAddressSpace(  
    [in] LPVOID startAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cc60b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cc60b-105">Parameters</span></span>  

 `startAddress`  
 <span data-ttu-id="cc60b-106">진행 해제할 메모리의 시작 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="cc60b-106">[in] Pointer to the starting address of the memory to be released.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cc60b-107">설명</span><span class="sxs-lookup"><span data-stu-id="cc60b-107">Remarks</span></span>  

 <span data-ttu-id="cc60b-108">`ReleasedVirtualAddressSpace`메서드는 콜백 메서드 이며 호스팅 응용 프로그램의 작성기에서 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc60b-108">The `ReleasedVirtualAddressSpace` method is a callback method and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="cc60b-109">CLR에서 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc60b-109">It is called by the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc60b-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cc60b-110">Requirements</span></span>  

 <span data-ttu-id="cc60b-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cc60b-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc60b-112">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="cc60b-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cc60b-113">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc60b-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cc60b-114">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc60b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc60b-115">참조</span><span class="sxs-lookup"><span data-stu-id="cc60b-115">See also</span></span>

- [<span data-ttu-id="cc60b-116">IHostMemoryManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cc60b-116">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
