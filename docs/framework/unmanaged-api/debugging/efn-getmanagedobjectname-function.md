---
title: _EFN_GetManagedObjectName 함수
ms.date: 03/30/2017
api_name:
- _EFN_GetManagedObjectName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- _EFN_GetManagedObjectName
helpviewer_keywords:
- _EFN_GetManagedObjectName function [.NET Framework debugging]
ms.assetid: 6e7c6bee-7ced-495f-bf6c-2a5f0c716f7e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4a95008d98436161ac919ef307273bc797519f15
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59080620"
---
# <a name="efngetmanagedobjectname-function"></a><span data-ttu-id="cd9c4-102">_EFN_GetManagedObjectName 함수</span><span class="sxs-lookup"><span data-stu-id="cd9c4-102">_EFN_GetManagedObjectName Function</span></span>
<span data-ttu-id="cd9c4-103">제공 된 관리 되는 개체 포인터를 사용 하는 형식의 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cd9c4-103">Gets the name of a type using the provided managed object pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd9c4-104">구문</span><span class="sxs-lookup"><span data-stu-id="cd9c4-104">Syntax</span></span>  
  
```  
HRESULT _EFN_GetManagedObjectName(  
    [in]  PDEBUG_CLIENT  Client,  
    [in]  ULONG64        objAddr,  
    [out] __out_ecount(cbName) PSTR szName,  
    [out] ULONG          cbName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cd9c4-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cd9c4-105">Parameters</span></span>  
 `Client`  
 <span data-ttu-id="cd9c4-106">[in] 디버그 클라이언트에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="cd9c4-106">[in] A pointer to the debug client.</span></span>  
  
 `objAddr`  
 <span data-ttu-id="cd9c4-107">[in] 관리 되는 개체 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="cd9c4-107">[in] A managed object pointer.</span></span>  
  
 <span data-ttu-id="cd9c4-108">szName</span><span class="sxs-lookup"><span data-stu-id="cd9c4-108">szName</span></span>  
 <span data-ttu-id="cd9c4-109">[out] 형식의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="cd9c4-109">[out] The name of the type.</span></span>  
  
 `cbName`  
 <span data-ttu-id="cd9c4-110">[out] 문자열 버퍼에서 사용할 수 있는 문자의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="cd9c4-110">[out] The number of characters available in the string buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cd9c4-111">설명</span><span class="sxs-lookup"><span data-stu-id="cd9c4-111">Remarks</span></span>  
 <span data-ttu-id="cd9c4-112">관리 되는 코드가 없는 스레드에서 현재 컨텍스트에서 함수 HRESULT SOS_E_NOMANAGEDCODE 0xa0 기능 값 및 0x1000의 오류 코드를 사용 하 여 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd9c4-112">If there is no managed code on the thread currently in context, the function returns HRESULT SOS_E_NOMANAGEDCODE with a facility value of 0xa0 and an error code of 0x1000.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd9c4-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cd9c4-113">Requirements</span></span>  
 <span data-ttu-id="cd9c4-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="cd9c4-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd9c4-115">**헤더:** SOS_Stacktrace.h</span><span class="sxs-lookup"><span data-stu-id="cd9c4-115">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="cd9c4-116">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd9c4-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd9c4-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="cd9c4-117">See also</span></span>

- [<span data-ttu-id="cd9c4-118">디버깅 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="cd9c4-118">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
