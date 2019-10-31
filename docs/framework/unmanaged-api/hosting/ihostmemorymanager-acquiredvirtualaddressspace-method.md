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
ms.openlocfilehash: b70454cd1e2d6d38e6ca4d0ea0bd8974963c201c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136734"
---
# <a name="ihostmemorymanageracquiredvirtualaddressspace-method"></a><span data-ttu-id="48215-102">IHostMemoryManager::AcquiredVirtualAddressSpace 메서드</span><span class="sxs-lookup"><span data-stu-id="48215-102">IHostMemoryManager::AcquiredVirtualAddressSpace Method</span></span>
<span data-ttu-id="48215-103">CLR (공용 언어 런타임)이 운영 체제에서 지정 된 메모리를 획득 했음을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="48215-103">Notifies the host that the common language runtime (CLR) has acquired the specified memory from the operating system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48215-104">구문</span><span class="sxs-lookup"><span data-stu-id="48215-104">Syntax</span></span>  
  
```cpp  
HRESULT AcquiredVirtualAddressSpace(  
    [in] LPVOID  startAddress,  
    [in] SIZE_T  size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="48215-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="48215-105">Parameters</span></span>  
 `startAddress`  
 <span data-ttu-id="48215-106">진행 메모리의 시작 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="48215-106">[in] The starting address of the memory.</span></span>  
  
 `size`  
 <span data-ttu-id="48215-107">진행 메모리의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="48215-107">[in] The size, in bytes, of the memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="48215-108">주의</span><span class="sxs-lookup"><span data-stu-id="48215-108">Remarks</span></span>  
 <span data-ttu-id="48215-109">`AcquiredVirtualAddressSpace` 메서드는 콜백 메서드 이며 호스팅 응용 프로그램의 작성기에서 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="48215-109">The `AcquiredVirtualAddressSpace` method is a callback method and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="48215-110">CLR에서 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="48215-110">It is called by the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48215-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="48215-111">Requirements</span></span>  
 <span data-ttu-id="48215-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="48215-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48215-113">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="48215-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="48215-114">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="48215-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="48215-115">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48215-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48215-116">참조</span><span class="sxs-lookup"><span data-stu-id="48215-116">See also</span></span>

- [<span data-ttu-id="48215-117">IHostMemoryManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="48215-117">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
