---
title: CLRDataCreateInstance 함수
ms.date: 03/30/2017
api_name:
- CLRDataCreateInstance
api_location:
- mscordbi.dll
- mscordacwks.dll
api_type:
- COM
f1_keywords:
- CLRDataCreateInstance
helpviewer_keywords:
- CLRDataCreateInstance function [.NET Framework debugging]
ms.assetid: 440bad90-5a88-45e7-9157-4596801d8d19
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 73a4a8a2fc737bbf4b49ca859f0549ca7efd54a2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61701283"
---
# <a name="clrdatacreateinstance-function"></a><span data-ttu-id="e9398-102">CLRDataCreateInstance 함수</span><span class="sxs-lookup"><span data-stu-id="e9398-102">CLRDataCreateInstance Function</span></span>
<span data-ttu-id="e9398-103">지정 된 대상 항목에 대 한 인터페이스 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e9398-103">Creates an interface object for the specified target item.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9398-104">구문</span><span class="sxs-lookup"><span data-stu-id="e9398-104">Syntax</span></span>  
  
```  
HRESULT CLRDataCreateInstance (  
    [in]  REFIID           iid,   
    [in]  ICLRDataTarget  *target,   
    [out] void           **iface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e9398-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e9398-105">Parameters</span></span>  
 `iid`  
 <span data-ttu-id="e9398-106">[in] 인스턴스화할 인터페이스의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="e9398-106">[in] The identifier of the interface to be instantiated.</span></span>  
  
 `target`  
 <span data-ttu-id="e9398-107">[in] 사용자가 구현한 포인터로 [ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md) 인터페이스 개체를 만들 대상 항목을 나타내는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="e9398-107">[in] A pointer to a user-implemented [ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md) object that represents the target item for which to create the interface object.</span></span>  
  
 `iface`  
 <span data-ttu-id="e9398-108">[out] 반환 된 인터페이스 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e9398-108">[out] A pointer to the address of the returned interface object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e9398-109">설명</span><span class="sxs-lookup"><span data-stu-id="e9398-109">Remarks</span></span>  
 <span data-ttu-id="e9398-110">`ICLRDataTarget` 개체 작성기는 디버깅 응용 프로그램에 의해 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9398-110">The `ICLRDataTarget` object is implemented by the writer of the debugging application.</span></span> <span data-ttu-id="e9398-111">구현을 표시 되는 대상 항목의 유형에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="e9398-111">The implementation depends on the type of target item being represented.</span></span> <span data-ttu-id="e9398-112">프로세스, 메모리 덤프, 원격 컴퓨터 및 등 대상 항목 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9398-112">The target item may be a process, memory dump, remote machine, and so on.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9398-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e9398-113">Requirements</span></span>  
 <span data-ttu-id="e9398-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e9398-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9398-115">**헤더:** ClrData.idl</span><span class="sxs-lookup"><span data-stu-id="e9398-115">**Header:** ClrData.idl</span></span>  
  
 <span data-ttu-id="e9398-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e9398-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e9398-117">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9398-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9398-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="e9398-118">See also</span></span>

- [<span data-ttu-id="e9398-119">디버깅 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="e9398-119">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
