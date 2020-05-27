---
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
ms.openlocfilehash: bb13c7329c558aa92ec65237aa8a9963c82fe1dc
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804519"
---
# <a name="ihostmemorymanagerneedsvirtualaddressspace-method"></a><span data-ttu-id="8dbd8-102">IHostMemoryManager::NeedsVirtualAddressSpace 메서드</span><span class="sxs-lookup"><span data-stu-id="8dbd8-102">IHostMemoryManager::NeedsVirtualAddressSpace Method</span></span>
<span data-ttu-id="8dbd8-103">CLR (공용 언어 런타임)이 지정 된 메모리를 사용 하려고 함을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="8dbd8-103">Notifies the host that the common language runtime (CLR) is going to attempt to use the specified memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8dbd8-104">구문</span><span class="sxs-lookup"><span data-stu-id="8dbd8-104">Syntax</span></span>  
  
```cpp  
HRESULT NeedsVirtualAddressSpace (  
    [in] LPVOID  startAddress,  
    [in] SIZE_T  size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8dbd8-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8dbd8-105">Parameters</span></span>  
 `startAddress`  
 <span data-ttu-id="8dbd8-106">진행 메모리의 시작 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="8dbd8-106">[in] The starting address of the memory.</span></span>  
  
 `size`  
 <span data-ttu-id="8dbd8-107">진행 메모리의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="8dbd8-107">[in] The size, in bytes, of the memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8dbd8-108">설명</span><span class="sxs-lookup"><span data-stu-id="8dbd8-108">Remarks</span></span>  
 <span data-ttu-id="8dbd8-109">`NeedsVirtualAddressSpace`메서드는 콜백 메서드 이며 호스팅 응용 프로그램의 작성기에서 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dbd8-109">The `NeedsVirtualAddressSpace` method is a callback method and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="8dbd8-110">CLR에서 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dbd8-110">It is called by the CLR.</span></span>  
  
 <span data-ttu-id="8dbd8-111">호스트에서 지정 된 메모리를 사용 하는 것을 원하지 않는 경우 E_OUTOFMEMORY HRESULT를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dbd8-111">If the host does not want the CLR to use the specified memory, it may return an E_OUTOFMEMORY HRESULT.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8dbd8-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8dbd8-112">Requirements</span></span>  
 <span data-ttu-id="8dbd8-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8dbd8-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8dbd8-114">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="8dbd8-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8dbd8-115">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dbd8-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8dbd8-116">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8dbd8-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8dbd8-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8dbd8-117">See also</span></span>

- [<span data-ttu-id="8dbd8-118">IHostMemoryManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8dbd8-118">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
