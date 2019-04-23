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
ms.openlocfilehash: 21fa9a17067f754fe9b13c4d32193856a57750ca
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59227368"
---
# <a name="iclrdatatargetgettlsvalue-method"></a><span data-ttu-id="68fe2-102">ICLRDataTarget::GetTLSValue 메서드</span><span class="sxs-lookup"><span data-stu-id="68fe2-102">ICLRDataTarget::GetTLSValue Method</span></span>
<span data-ttu-id="68fe2-103">대상 프로세스에서 지정 된 스레드의 스레드 로컬 저장소 (TLS)에서 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="68fe2-103">Gets a value from the thread local storage (TLS) of the specified thread in the target process.</span></span> <span data-ttu-id="68fe2-104">이 메서드는 공용 언어 런타임 (CLR) 데이터 액세스 서비스에 의해 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="68fe2-104">This method is called by the common language runtime (CLR) data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68fe2-105">구문</span><span class="sxs-lookup"><span data-stu-id="68fe2-105">Syntax</span></span>  
  
```  
HRESULT GetTLSValue (  
    [in] ULONG32            threadID,  
    [in] ULONG32            index,  
    [out] CLRDATA_ADDRESS   *value  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="68fe2-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="68fe2-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="68fe2-107">[in] 대상 프로세스에서 스레드의 운영 체제 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="68fe2-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `index`  
 <span data-ttu-id="68fe2-108">[in] 인덱스 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="68fe2-108">[in] The index of the location.</span></span> <span data-ttu-id="68fe2-109">이 값은 지정 된 스레드 로컬 저장소에 유효한 인덱스 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="68fe2-109">This value must be a valid index in the local store of the specified thread.</span></span>  
  
 `value`  
 <span data-ttu-id="68fe2-110">[out] 에 대 한 포인터를 `CLRDATA_ADDRESS` 지정된 TLS 위치에서 반환 된 값을 지정 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="68fe2-110">[out] A pointer to a `CLRDATA_ADDRESS` value that specifies the value returned from the given TLS location.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="68fe2-111">설명</span><span class="sxs-lookup"><span data-stu-id="68fe2-111">Remarks</span></span>  
 <span data-ttu-id="68fe2-112">이 메서드는 디버깅 응용 프로그램의 작성자가 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="68fe2-112">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="68fe2-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="68fe2-113">Requirements</span></span>  
 <span data-ttu-id="68fe2-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="68fe2-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="68fe2-115">**헤더:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="68fe2-115">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="68fe2-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="68fe2-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="68fe2-117">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="68fe2-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68fe2-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="68fe2-118">See also</span></span>

- [<span data-ttu-id="68fe2-119">ICLRDataTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="68fe2-119">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
