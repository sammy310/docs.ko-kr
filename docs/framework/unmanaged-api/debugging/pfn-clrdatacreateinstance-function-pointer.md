---
title: PFN_CLRDataCreateInstance 함수 포인터
ms.date: 03/30/2017
api_name:
- PFN_CLRDataCreateInstance
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- PFN_CLRDataCreateInstance
helpviewer_keywords:
- PFN_CLRDataCreateInstance function pointer [.NET Framework debugging]
ms.assetid: 5c66ac57-d751-4de5-af9f-26ceb949af8b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 81fcc99a739d5e673d1d01d5efb801ba4930bdee
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67752550"
---
# <a name="pfnclrdatacreateinstance-function-pointer"></a><span data-ttu-id="f8048-102">PFN_CLRDataCreateInstance 함수 포인터</span><span class="sxs-lookup"><span data-stu-id="f8048-102">PFN_CLRDataCreateInstance Function Pointer</span></span>
<span data-ttu-id="f8048-103">지정 된 대상 항목에 대 한 인터페이스 개체를 만드는 함수를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="f8048-103">Points to a function that creates an interface object for the specified target item.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8048-104">구문</span><span class="sxs-lookup"><span data-stu-id="f8048-104">Syntax</span></span>  
  
```cpp  
typedef HRESULT (STDAPICALLTYPE* PFN_CLRDataCreateInstance) (  
    [in]  REFIID           iid,  
    [in]  ICLRDataTarget  *target,  
    [out] void           **iface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f8048-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f8048-105">Parameters</span></span>  
 `iid`  
 <span data-ttu-id="f8048-106">[in] 인스턴스화할 인터페이스의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="f8048-106">[in] The identifier of the interface to be instantiated.</span></span>  
  
 `target`  
 <span data-ttu-id="f8048-107">[in] 사용자가 구현한 포인터로 [ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md) 인터페이스 개체를 만들 대상 항목을 나타내는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="f8048-107">[in] A pointer to a user-implemented [ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md) object that represents the target item for which to create the interface object.</span></span>  
  
 `iface`  
 <span data-ttu-id="f8048-108">[out] 반환 된 인터페이스 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f8048-108">[out] A pointer to the address of the returned interface object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f8048-109">설명</span><span class="sxs-lookup"><span data-stu-id="f8048-109">Remarks</span></span>  
 <span data-ttu-id="f8048-110">`ICLRDataTarget` 개체 작성기는 디버깅 응용 프로그램에 의해 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8048-110">The `ICLRDataTarget` object is implemented by the writer of the debugging application.</span></span> <span data-ttu-id="f8048-111">구현을 표시 되는 대상 항목의 유형에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="f8048-111">The implementation depends on the type of target item being represented.</span></span> <span data-ttu-id="f8048-112">프로세스, 메모리 덤프, 원격 컴퓨터 및 등 대상 항목 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8048-112">The target item may be a process, memory dump, remote machine, and so on.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8048-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f8048-113">Requirements</span></span>  
 <span data-ttu-id="f8048-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f8048-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8048-115">**헤더:** ClrData.idl</span><span class="sxs-lookup"><span data-stu-id="f8048-115">**Header:** ClrData.idl</span></span>  
  
 <span data-ttu-id="f8048-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f8048-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f8048-117">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8048-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8048-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="f8048-118">See also</span></span>

- [<span data-ttu-id="f8048-119">디버깅 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="f8048-119">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
