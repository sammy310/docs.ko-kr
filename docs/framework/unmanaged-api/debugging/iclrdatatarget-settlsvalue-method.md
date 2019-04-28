---
title: ICLRDataTarget::SetTLSValue 메서드
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.SetTLSValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::SetTLSValue
helpviewer_keywords:
- ICLRDataTarget::SetTLSValue method [.NET Framework debugging]
- SetTLSValue method [.NET Framework debugging]
ms.assetid: 4a2d6a24-749a-47ad-9f01-4517203d3f35
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4c0be35772b10d89f90da5b33f47aa781034b13a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61698085"
---
# <a name="iclrdatatargetsettlsvalue-method"></a><span data-ttu-id="d1c22-102">ICLRDataTarget::SetTLSValue 메서드</span><span class="sxs-lookup"><span data-stu-id="d1c22-102">ICLRDataTarget::SetTLSValue Method</span></span>
<span data-ttu-id="d1c22-103">대상 프로세스에서 지정 된 스레드의 스레드 로컬 저장소 (TLS)에서 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1c22-103">Sets a value in the thread local storage (TLS) of the specified thread in the target process.</span></span> <span data-ttu-id="d1c22-104">이 메서드는 공용 언어 런타임 (CLR) 데이터 액세스 서비스에 의해 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1c22-104">This method is called by the common language runtime (CLR) data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1c22-105">구문</span><span class="sxs-lookup"><span data-stu-id="d1c22-105">Syntax</span></span>  
  
```  
HRESULT SetTLSValue (  
    [in] ULONG32            threadID,  
    [in] ULONG32            index,  
    [in] CLRDATA_ADDRESS    value  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d1c22-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d1c22-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="d1c22-107">[in] 대상 프로세스에서 스레드의 운영 체제 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="d1c22-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `index`  
 <span data-ttu-id="d1c22-108">[in] 인덱스 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="d1c22-108">[in] The index of the location.</span></span> <span data-ttu-id="d1c22-109">이 값은 지정 된 스레드 로컬 저장소에 유효한 인덱스 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1c22-109">This value must be a valid index in the local store of the specified thread.</span></span>  
  
 `value`  
 <span data-ttu-id="d1c22-110">[in] `CLRDATA_ADDRESS` 지정된 TLS 위치에 넣을 값을 지정 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="d1c22-110">[in] A `CLRDATA_ADDRESS` value that specifies the value to place in the given TLS location.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d1c22-111">설명</span><span class="sxs-lookup"><span data-stu-id="d1c22-111">Remarks</span></span>  
 <span data-ttu-id="d1c22-112">이 메서드는 디버깅 응용 프로그램의 작성자가 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="d1c22-112">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1c22-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d1c22-113">Requirements</span></span>  
 <span data-ttu-id="d1c22-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d1c22-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1c22-115">**헤더:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="d1c22-115">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="d1c22-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d1c22-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d1c22-117">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1c22-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1c22-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="d1c22-118">See also</span></span>

- [<span data-ttu-id="d1c22-119">ICLRDataTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d1c22-119">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
