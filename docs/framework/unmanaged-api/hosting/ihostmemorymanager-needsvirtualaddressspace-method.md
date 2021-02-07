---
description: '자세히 알아보기: IHostMemoryManager:: NeedsVirtualAddressSpace 메서드'
title: IHostMemoryManager::NeedsVirtualAddressSpace 메서드
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.NeedsVirtualAddressSpace
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::NeedsVirtualAddressSpace
helpviewer_keywords:
- IHostMemoryManager::NeedsVirtualAddressSpace method [.NET Framework hosting]
- NeedsVirtualAddressSpace method [.NET Framework hosting]
ms.assetid: 71f0eab5-0170-46f8-9f88-1df5abdeb34a
topic_type:
- apiref
ms.openlocfilehash: 95d4128decffc82fdcb198155b48a31420f71220
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99707789"
---
# <a name="ihostmemorymanagerneedsvirtualaddressspace-method"></a><span data-ttu-id="e1c00-103">IHostMemoryManager::NeedsVirtualAddressSpace 메서드</span><span class="sxs-lookup"><span data-stu-id="e1c00-103">IHostMemoryManager::NeedsVirtualAddressSpace Method</span></span>

<span data-ttu-id="e1c00-104">CLR (공용 언어 런타임)이 지정 된 메모리를 사용 하려고 함을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="e1c00-104">Notifies the host that the common language runtime (CLR) is going to attempt to use the specified memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1c00-105">구문</span><span class="sxs-lookup"><span data-stu-id="e1c00-105">Syntax</span></span>  
  
```cpp  
HRESULT NeedsVirtualAddressSpace (  
    [in] LPVOID  startAddress,  
    [in] SIZE_T  size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e1c00-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e1c00-106">Parameters</span></span>  

 `startAddress`  
 <span data-ttu-id="e1c00-107">진행 메모리의 시작 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="e1c00-107">[in] The starting address of the memory.</span></span>  
  
 `size`  
 <span data-ttu-id="e1c00-108">진행 메모리의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="e1c00-108">[in] The size, in bytes, of the memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e1c00-109">설명</span><span class="sxs-lookup"><span data-stu-id="e1c00-109">Remarks</span></span>  

 <span data-ttu-id="e1c00-110">`NeedsVirtualAddressSpace`메서드는 콜백 메서드 이며 호스팅 응용 프로그램의 작성기에서 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1c00-110">The `NeedsVirtualAddressSpace` method is a callback method and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="e1c00-111">CLR에서 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1c00-111">It is called by the CLR.</span></span>  
  
 <span data-ttu-id="e1c00-112">호스트에서 지정 된 메모리를 사용 하는 것을 원하지 않는 경우 E_OUTOFMEMORY HRESULT를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1c00-112">If the host does not want the CLR to use the specified memory, it may return an E_OUTOFMEMORY HRESULT.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1c00-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e1c00-113">Requirements</span></span>  

 <span data-ttu-id="e1c00-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e1c00-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1c00-115">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="e1c00-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e1c00-116">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1c00-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e1c00-117">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1c00-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1c00-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e1c00-118">See also</span></span>

- [<span data-ttu-id="e1c00-119">IHostMemoryManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e1c00-119">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
