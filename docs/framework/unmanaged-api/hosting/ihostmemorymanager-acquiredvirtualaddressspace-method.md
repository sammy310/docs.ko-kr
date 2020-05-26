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
ms.openlocfilehash: f5469a6f35826bcb06fe821e3748861dbf3682f3
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804539"
---
# <a name="ihostmemorymanageracquiredvirtualaddressspace-method"></a><span data-ttu-id="142e9-102">IHostMemoryManager::AcquiredVirtualAddressSpace 메서드</span><span class="sxs-lookup"><span data-stu-id="142e9-102">IHostMemoryManager::AcquiredVirtualAddressSpace Method</span></span>
<span data-ttu-id="142e9-103">CLR (공용 언어 런타임)이 운영 체제에서 지정 된 메모리를 획득 했음을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="142e9-103">Notifies the host that the common language runtime (CLR) has acquired the specified memory from the operating system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="142e9-104">구문</span><span class="sxs-lookup"><span data-stu-id="142e9-104">Syntax</span></span>  
  
```cpp  
HRESULT AcquiredVirtualAddressSpace(  
    [in] LPVOID  startAddress,  
    [in] SIZE_T  size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="142e9-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="142e9-105">Parameters</span></span>  
 `startAddress`  
 <span data-ttu-id="142e9-106">진행 메모리의 시작 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="142e9-106">[in] The starting address of the memory.</span></span>  
  
 `size`  
 <span data-ttu-id="142e9-107">진행 메모리의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="142e9-107">[in] The size, in bytes, of the memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="142e9-108">설명</span><span class="sxs-lookup"><span data-stu-id="142e9-108">Remarks</span></span>  
 <span data-ttu-id="142e9-109">`AcquiredVirtualAddressSpace`메서드는 콜백 메서드 이며 호스팅 응용 프로그램의 작성기에서 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="142e9-109">The `AcquiredVirtualAddressSpace` method is a callback method and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="142e9-110">CLR에서 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="142e9-110">It is called by the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="142e9-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="142e9-111">Requirements</span></span>  
 <span data-ttu-id="142e9-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="142e9-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="142e9-113">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="142e9-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="142e9-114">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="142e9-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="142e9-115">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="142e9-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="142e9-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="142e9-116">See also</span></span>

- [<span data-ttu-id="142e9-117">IHostMemoryManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="142e9-117">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
