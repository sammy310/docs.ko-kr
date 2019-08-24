---
title: ICLRDataTarget::GetTLSValue 메서드
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetTLSValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetTLSValue
helpviewer_keywords:
- GetTLSValue method [.NET Framework debugging]
- ICLRDataTarget::GetTLSValue method [.NET Framework debugging]
ms.assetid: 0d8a7730-edc9-4728-898f-41b219cf5a28
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7de415b998ef97e7500c289a1bca4402d203b152
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67738696"
---
# <a name="iclrdatatargetgettlsvalue-method"></a><span data-ttu-id="a52b4-102">ICLRDataTarget::GetTLSValue 메서드</span><span class="sxs-lookup"><span data-stu-id="a52b4-102">ICLRDataTarget::GetTLSValue Method</span></span>
<span data-ttu-id="a52b4-103">대상 프로세스에서 지정 된 스레드의 스레드 로컬 저장소 (TLS)에서 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a52b4-103">Gets a value from the thread local storage (TLS) of the specified thread in the target process.</span></span> <span data-ttu-id="a52b4-104">이 메서드는 공용 언어 런타임 (CLR) 데이터 액세스 서비스에 의해 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a52b4-104">This method is called by the common language runtime (CLR) data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a52b4-105">구문</span><span class="sxs-lookup"><span data-stu-id="a52b4-105">Syntax</span></span>  
  
```cpp  
HRESULT GetTLSValue (  
    [in] ULONG32            threadID,  
    [in] ULONG32            index,  
    [out] CLRDATA_ADDRESS   *value  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a52b4-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a52b4-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="a52b4-107">[in] 대상 프로세스에서 스레드의 운영 체제 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="a52b4-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `index`  
 <span data-ttu-id="a52b4-108">[in] 인덱스 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="a52b4-108">[in] The index of the location.</span></span> <span data-ttu-id="a52b4-109">이 값은 지정 된 스레드 로컬 저장소에 유효한 인덱스 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a52b4-109">This value must be a valid index in the local store of the specified thread.</span></span>  
  
 `value`  
 <span data-ttu-id="a52b4-110">[out] 에 대 한 포인터를 `CLRDATA_ADDRESS` 지정된 TLS 위치에서 반환 된 값을 지정 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="a52b4-110">[out] A pointer to a `CLRDATA_ADDRESS` value that specifies the value returned from the given TLS location.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a52b4-111">설명</span><span class="sxs-lookup"><span data-stu-id="a52b4-111">Remarks</span></span>  
 <span data-ttu-id="a52b4-112">이 메서드는 디버깅 애플리케이션의 작성자가 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="a52b4-112">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a52b4-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a52b4-113">Requirements</span></span>  
 <span data-ttu-id="a52b4-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a52b4-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a52b4-115">**헤더:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="a52b4-115">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="a52b4-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a52b4-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a52b4-117">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a52b4-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a52b4-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="a52b4-118">See also</span></span>

- [<span data-ttu-id="a52b4-119">ICLRDataTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a52b4-119">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
