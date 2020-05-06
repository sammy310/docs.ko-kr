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
ms.openlocfilehash: 42f7020212dd2db793b7c7d20a15c129157e7261
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860757"
---
# <a name="_efn_getmanagedobjectfieldinfo-function"></a><span data-ttu-id="ed529-102">\_EFN\_GetManagedObjectFieldInfo 함수</span><span class="sxs-lookup"><span data-stu-id="ed529-102">\_EFN\_GetManagedObjectFieldInfo Function</span></span>
<span data-ttu-id="ed529-103">제공된 개체 포인터와 필드 이름을 사용하여 개체 시작부터 필드 및 필드 값까지의 오프셋을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ed529-103">Gets the offset from the start of an object to a field and the field's value, using the provided object pointer and field name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed529-104">구문</span><span class="sxs-lookup"><span data-stu-id="ed529-104">Syntax</span></span>  
  
```cpp  
HRESULT _EFN_GetManagedObjectFieldInfo(  
    [in]  PDEBUG_CLIENT Client,  
    [in]  ULONG64       objAddr,  
    [in]  __out_ecount (mdNameLen) PSTR szFieldName,  
    [out] PULONG64      pValue,  
    [out] PULONG        pOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ed529-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ed529-105">Parameters</span></span>  
 `Client`  
 <span data-ttu-id="ed529-106">진행 디버그 클라이언트에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ed529-106">[in] A pointer to the debug client.</span></span>  
  
 `objAddr`  
 <span data-ttu-id="ed529-107">진행 관리 되는 개체 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ed529-107">[in] A managed object pointer.</span></span>  
  
 <span data-ttu-id="ed529-108">szFieldName</span><span class="sxs-lookup"><span data-stu-id="ed529-108">szFieldName</span></span>  
 <span data-ttu-id="ed529-109">진행 필드 이름에 대 한 관리 되는 개체 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ed529-109">[in] A managed object pointer to the field name.</span></span>  
  
 `pValue`  
 <span data-ttu-id="ed529-110">제한이 필드 값입니다.</span><span class="sxs-lookup"><span data-stu-id="ed529-110">[out] The field value.</span></span> <span data-ttu-id="ed529-111">이 매개 변수는 null일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed529-111">This parameter can be null.</span></span>  
  
 `pOffset`  
 <span data-ttu-id="ed529-112">제한이 에서 `objAddr` 필드로의 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="ed529-112">[out] The offset from `objAddr` to the field.</span></span> <span data-ttu-id="ed529-113">이 매개 변수는 null일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed529-113">This parameter can be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ed529-114">설명</span><span class="sxs-lookup"><span data-stu-id="ed529-114">Remarks</span></span>  
 <span data-ttu-id="ed529-115">오프셋이 0 이면 오프셋이 기록 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ed529-115">If the offset is 0, no offset is written.</span></span>  
  
 <span data-ttu-id="ed529-116">현재 컨텍스트에 있는 스레드에 관리 코드가 없는 경우 함수는 기능 값 0xa0 및 0x1000 오류 코드를 사용 하 여 HRESULT SOS_E_NOMANAGEDCODE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed529-116">If there is no managed code on the thread currently in context, the function returns HRESULT SOS_E_NOMANAGEDCODE with a facility value of 0xa0 and an error code of 0x1000.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed529-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ed529-117">Requirements</span></span>  
 <span data-ttu-id="ed529-118">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ed529-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed529-119">**헤더:** SOS_Stacktrace. h</span><span class="sxs-lookup"><span data-stu-id="ed529-119">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="ed529-120">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed529-120">**.NET Framework Version:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed529-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ed529-121">See also</span></span>

- [<span data-ttu-id="ed529-122">디버깅 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="ed529-122">Debugging Global Static Functions</span></span>](debugging-global-static-functions.md)
