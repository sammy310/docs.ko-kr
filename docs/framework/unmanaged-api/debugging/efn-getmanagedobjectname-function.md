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
ms.openlocfilehash: 0fb694cf85256c0f3ac5ae179e53ff504ab707e9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676207"
---
# <a name="_efn_getmanagedobjectname-function"></a><span data-ttu-id="596d2-102">\_EFN \_ GetManagedObjectName 함수</span><span class="sxs-lookup"><span data-stu-id="596d2-102">\_EFN\_GetManagedObjectName Function</span></span>

<span data-ttu-id="596d2-103">제공 된 관리 되는 개체 포인터를 사용 하 여 형식의 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="596d2-103">Gets the name of a type using the provided managed object pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="596d2-104">구문</span><span class="sxs-lookup"><span data-stu-id="596d2-104">Syntax</span></span>  
  
```cpp  
HRESULT _EFN_GetManagedObjectName(  
    [in]  PDEBUG_CLIENT  Client,  
    [in]  ULONG64        objAddr,  
    [out] __out_ecount(cbName) PSTR szName,  
    [out] ULONG          cbName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="596d2-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="596d2-105">Parameters</span></span>  

 `Client`  
 <span data-ttu-id="596d2-106">진행 디버그 클라이언트에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="596d2-106">[in] A pointer to the debug client.</span></span>  
  
 `objAddr`  
 <span data-ttu-id="596d2-107">진행 관리 되는 개체 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="596d2-107">[in] A managed object pointer.</span></span>  
  
 <span data-ttu-id="596d2-108">szName</span><span class="sxs-lookup"><span data-stu-id="596d2-108">szName</span></span>  
 <span data-ttu-id="596d2-109">제한이 형식의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="596d2-109">[out] The name of the type.</span></span>  
  
 `cbName`  
 <span data-ttu-id="596d2-110">제한이 문자열 버퍼에서 사용할 수 있는 문자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="596d2-110">[out] The number of characters available in the string buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="596d2-111">설명</span><span class="sxs-lookup"><span data-stu-id="596d2-111">Remarks</span></span>  

 <span data-ttu-id="596d2-112">현재 컨텍스트에 있는 스레드에 관리 코드가 없는 경우 함수는 기능 값 0xa0 및 0x1000 오류 코드를 사용 하 여 HRESULT SOS_E_NOMANAGEDCODE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="596d2-112">If there is no managed code on the thread currently in context, the function returns HRESULT SOS_E_NOMANAGEDCODE with a facility value of 0xa0 and an error code of 0x1000.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="596d2-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="596d2-113">Requirements</span></span>  

 <span data-ttu-id="596d2-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="596d2-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="596d2-115">**헤더:** SOS_Stacktrace. h</span><span class="sxs-lookup"><span data-stu-id="596d2-115">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="596d2-116">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="596d2-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="596d2-117">참조</span><span class="sxs-lookup"><span data-stu-id="596d2-117">See also</span></span>

- [<span data-ttu-id="596d2-118">디버깅 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="596d2-118">Debugging Global Static Functions</span></span>](debugging-global-static-functions.md)
