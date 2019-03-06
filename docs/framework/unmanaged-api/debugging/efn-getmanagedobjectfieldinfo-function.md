---
title: _EFN_GetManagedObjectFieldInfo 함수
ms.date: 03/30/2017
api_name:
- _EFN_GetManagedObjectFieldInfo
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- _EFN_GetManagedObjectFieldInfo
helpviewer_keywords:
- _EFN_GetManagedObjectFieldInfo function [.NET Framework debugging]
ms.assetid: 3b93bcff-62a4-47b2-babc-6bcf4216119a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 675bf2ad36fe5006a44890f8ccd6e6197f264ac1
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57484474"
---
# <a name="efngetmanagedobjectfieldinfo-function"></a><span data-ttu-id="848c1-102">_EFN_GetManagedObjectFieldInfo 함수</span><span class="sxs-lookup"><span data-stu-id="848c1-102">_EFN_GetManagedObjectFieldInfo Function</span></span>
<span data-ttu-id="848c1-103">제공된 개체 포인터와 필드 이름을 사용하여 개체 시작부터 필드 및 필드 값까지의 오프셋을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="848c1-103">Gets the offset from the start of an object to a field and the field's value, using the provided object pointer and field name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="848c1-104">구문</span><span class="sxs-lookup"><span data-stu-id="848c1-104">Syntax</span></span>  
  
```  
HRESULT _EFN_GetManagedObjectFieldInfo(  
    [in]  PDEBUG_CLIENT Client,  
    [in]  ULONG64       objAddr,  
    [in]  __out_ecount (mdNameLen) PSTR szFieldName,  
    [out] PULONG64      pValue,  
    [out] PULONG        pOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="848c1-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="848c1-105">Parameters</span></span>  
 `Client`  
 <span data-ttu-id="848c1-106">[in] 디버그 클라이언트에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="848c1-106">[in] A pointer to the debug client.</span></span>  
  
 `objAddr`  
 <span data-ttu-id="848c1-107">[in] 관리 되는 개체 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="848c1-107">[in] A managed object pointer.</span></span>  
  
 <span data-ttu-id="848c1-108">szFieldName</span><span class="sxs-lookup"><span data-stu-id="848c1-108">szFieldName</span></span>  
 <span data-ttu-id="848c1-109">[in] 필드 이름 관리 되는 개체 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="848c1-109">[in] A managed object pointer to the field name.</span></span>  
  
 `pValue`  
 <span data-ttu-id="848c1-110">[out] 필드 값입니다.</span><span class="sxs-lookup"><span data-stu-id="848c1-110">[out] The field value.</span></span> <span data-ttu-id="848c1-111">이 매개 변수는 null일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="848c1-111">This parameter can be null.</span></span>  
  
 `pOffset`  
 <span data-ttu-id="848c1-112">[out] 오프셋 `objAddr` 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="848c1-112">[out] The offset from `objAddr` to the field.</span></span> <span data-ttu-id="848c1-113">이 매개 변수는 null일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="848c1-113">This parameter can be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="848c1-114">설명</span><span class="sxs-lookup"><span data-stu-id="848c1-114">Remarks</span></span>  
 <span data-ttu-id="848c1-115">오프셋 0 인 경우 오프셋 없이 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="848c1-115">If the offset is 0, no offset is written.</span></span>  
  
 <span data-ttu-id="848c1-116">관리 되는 코드가 없는 스레드에서 현재 컨텍스트에서 함수 HRESULT SOS_E_NOMANAGEDCODE 0xa0 기능 값 및 0x1000의 오류 코드를 사용 하 여 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="848c1-116">If there is no managed code on the thread currently in context, the function returns HRESULT SOS_E_NOMANAGEDCODE with a facility value of 0xa0 and an error code of 0x1000.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="848c1-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="848c1-117">Requirements</span></span>  
 <span data-ttu-id="848c1-118">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="848c1-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="848c1-119">**헤더:** SOS_Stacktrace.h</span><span class="sxs-lookup"><span data-stu-id="848c1-119">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="848c1-120">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="848c1-120">**.NET Framework Version:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="848c1-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="848c1-121">See also</span></span>
- [<span data-ttu-id="848c1-122">디버깅 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="848c1-122">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
