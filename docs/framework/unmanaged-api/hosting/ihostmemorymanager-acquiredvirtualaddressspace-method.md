---
description: '자세히 알아보기: IHostMemoryManager:: AcquiredVirtualAddressSpace 메서드'
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
ms.openlocfilehash: 70424c5bf907cfc3fb2e8951464335323f9331f4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99707907"
---
# <a name="ihostmemorymanageracquiredvirtualaddressspace-method"></a><span data-ttu-id="33848-103">IHostMemoryManager::AcquiredVirtualAddressSpace 메서드</span><span class="sxs-lookup"><span data-stu-id="33848-103">IHostMemoryManager::AcquiredVirtualAddressSpace Method</span></span>

<span data-ttu-id="33848-104">CLR (공용 언어 런타임)이 운영 체제에서 지정 된 메모리를 획득 했음을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="33848-104">Notifies the host that the common language runtime (CLR) has acquired the specified memory from the operating system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33848-105">구문</span><span class="sxs-lookup"><span data-stu-id="33848-105">Syntax</span></span>  
  
```cpp  
HRESULT AcquiredVirtualAddressSpace(  
    [in] LPVOID  startAddress,  
    [in] SIZE_T  size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="33848-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="33848-106">Parameters</span></span>  

 `startAddress`  
 <span data-ttu-id="33848-107">진행 메모리의 시작 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="33848-107">[in] The starting address of the memory.</span></span>  
  
 `size`  
 <span data-ttu-id="33848-108">진행 메모리의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="33848-108">[in] The size, in bytes, of the memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="33848-109">설명</span><span class="sxs-lookup"><span data-stu-id="33848-109">Remarks</span></span>  

 <span data-ttu-id="33848-110">`AcquiredVirtualAddressSpace`메서드는 콜백 메서드 이며 호스팅 응용 프로그램의 작성기에서 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="33848-110">The `AcquiredVirtualAddressSpace` method is a callback method and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="33848-111">CLR에서 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="33848-111">It is called by the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33848-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="33848-112">Requirements</span></span>  

 <span data-ttu-id="33848-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="33848-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33848-114">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="33848-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="33848-115">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="33848-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="33848-116">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33848-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33848-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="33848-117">See also</span></span>

- [<span data-ttu-id="33848-118">IHostMemoryManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="33848-118">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
