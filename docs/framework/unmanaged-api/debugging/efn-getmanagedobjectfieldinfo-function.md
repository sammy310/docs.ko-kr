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
ms.openlocfilehash: 4c088b7e1096f8b4cad11a3e27b4045e233989ae
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676220"
---
# <a name="_efn_getmanagedobjectfieldinfo-function"></a><span data-ttu-id="37c17-102">\_EFN \_ GetManagedObjectFieldInfo 함수</span><span class="sxs-lookup"><span data-stu-id="37c17-102">\_EFN\_GetManagedObjectFieldInfo Function</span></span>

<span data-ttu-id="37c17-103">제공된 개체 포인터와 필드 이름을 사용하여 개체 시작부터 필드 및 필드 값까지의 오프셋을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="37c17-103">Gets the offset from the start of an object to a field and the field's value, using the provided object pointer and field name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37c17-104">구문</span><span class="sxs-lookup"><span data-stu-id="37c17-104">Syntax</span></span>  
  
```cpp  
HRESULT _EFN_GetManagedObjectFieldInfo(  
    [in]  PDEBUG_CLIENT Client,  
    [in]  ULONG64       objAddr,  
    [in]  __out_ecount (mdNameLen) PSTR szFieldName,  
    [out] PULONG64      pValue,  
    [out] PULONG        pOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="37c17-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="37c17-105">Parameters</span></span>  

 `Client`  
 <span data-ttu-id="37c17-106">진행 디버그 클라이언트에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="37c17-106">[in] A pointer to the debug client.</span></span>  
  
 `objAddr`  
 <span data-ttu-id="37c17-107">진행 관리 되는 개체 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="37c17-107">[in] A managed object pointer.</span></span>  
  
 <span data-ttu-id="37c17-108">szFieldName</span><span class="sxs-lookup"><span data-stu-id="37c17-108">szFieldName</span></span>  
 <span data-ttu-id="37c17-109">진행 필드 이름에 대 한 관리 되는 개체 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="37c17-109">[in] A managed object pointer to the field name.</span></span>  
  
 `pValue`  
 <span data-ttu-id="37c17-110">제한이 필드 값입니다.</span><span class="sxs-lookup"><span data-stu-id="37c17-110">[out] The field value.</span></span> <span data-ttu-id="37c17-111">이 매개 변수는 null일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37c17-111">This parameter can be null.</span></span>  
  
 `pOffset`  
 <span data-ttu-id="37c17-112">제한이 에서 필드로의 오프셋 `objAddr` 입니다.</span><span class="sxs-lookup"><span data-stu-id="37c17-112">[out] The offset from `objAddr` to the field.</span></span> <span data-ttu-id="37c17-113">이 매개 변수는 null일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37c17-113">This parameter can be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="37c17-114">설명</span><span class="sxs-lookup"><span data-stu-id="37c17-114">Remarks</span></span>  

 <span data-ttu-id="37c17-115">오프셋이 0 이면 오프셋이 기록 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="37c17-115">If the offset is 0, no offset is written.</span></span>  
  
 <span data-ttu-id="37c17-116">현재 컨텍스트에 있는 스레드에 관리 코드가 없는 경우 함수는 기능 값 0xa0 및 0x1000 오류 코드를 사용 하 여 HRESULT SOS_E_NOMANAGEDCODE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="37c17-116">If there is no managed code on the thread currently in context, the function returns HRESULT SOS_E_NOMANAGEDCODE with a facility value of 0xa0 and an error code of 0x1000.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="37c17-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="37c17-117">Requirements</span></span>  

 <span data-ttu-id="37c17-118">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="37c17-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37c17-119">**헤더:** SOS_Stacktrace. h</span><span class="sxs-lookup"><span data-stu-id="37c17-119">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="37c17-120">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="37c17-120">**.NET Framework Version:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37c17-121">참조</span><span class="sxs-lookup"><span data-stu-id="37c17-121">See also</span></span>

- [<span data-ttu-id="37c17-122">디버깅 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="37c17-122">Debugging Global Static Functions</span></span>](debugging-global-static-functions.md)
