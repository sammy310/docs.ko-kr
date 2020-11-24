---
title: _EFN_GetManagedExcepStack 함수
ms.date: 03/30/2017
api_name:
- _EFN_GetManagedExcepStack
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- _EFN_GetManagedExcepStack
helpviewer_keywords:
- _EFN_GetManagedExcepStack function [.NET Framework debugging]
ms.assetid: 21ceed9e-62b2-4024-b027-6d095109955a
topic_type:
- apiref
ms.openlocfilehash: b86277836b1be48c9f8020d59071aba8c5b1e457
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676233"
---
# <a name="_efn_getmanagedexcepstack-function"></a><span data-ttu-id="56b73-102">\_EFN \_ GetManagedExcepStack 함수</span><span class="sxs-lookup"><span data-stu-id="56b73-102">\_EFN\_GetManagedExcepStack Function</span></span>

<span data-ttu-id="56b73-103">관리되는 예외 개체 주소를 제공하면 내부에 포함된 스택 추적의 문자열 버전을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="56b73-103">Given a managed exception object address, returns a string version of the stack trace contained inside.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56b73-104">구문</span><span class="sxs-lookup"><span data-stu-id="56b73-104">Syntax</span></span>  
  
```cpp  
HRESULT _EFN_GetManagedExcepStack(  
    [in]  PDEBUG_CLIENT Client,  
    [in]  ULONG64       StackObjAddr,  
    [out] __out_ecount(cbString) PSTR szStackString,  
    [out] ULONG         cbString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="56b73-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="56b73-105">Parameters</span></span>  

 `Client`  
 <span data-ttu-id="56b73-106">진행 디버깅 중인 클라이언트입니다.</span><span class="sxs-lookup"><span data-stu-id="56b73-106">[in] The client being debugged.</span></span>  
  
 `StackObjAddr`  
 <span data-ttu-id="56b73-107">진행 에서 파생 된 관리 되는 개체 포인터 <xref:System.Exception> 입니다.</span><span class="sxs-lookup"><span data-stu-id="56b73-107">[in] A managed object pointer, derived from <xref:System.Exception>.</span></span>  
  
 <span data-ttu-id="56b73-108">szStackString</span><span class="sxs-lookup"><span data-stu-id="56b73-108">szStackString</span></span>  
 <span data-ttu-id="56b73-109">제한이 반환 된 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="56b73-109">[out] The returned string.</span></span>  
  
 `cbString`  
 <span data-ttu-id="56b73-110">제한이 문자열 버퍼에서 사용할 수 있는 문자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="56b73-110">[out] The number of characters available in the string buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="56b73-111">설명</span><span class="sxs-lookup"><span data-stu-id="56b73-111">Remarks</span></span>  

 <span data-ttu-id="56b73-112">현재 컨텍스트에 있는 스레드에 관리 코드가 없는 경우 함수는 기능 값 0xa0 및 0x1000 오류 코드를 사용 하 여 HRESULT SOS_E_NOMANAGEDCODE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="56b73-112">If there is no managed code on the thread currently in context, the function returns HRESULT SOS_E_NOMANAGEDCODE with a facility value of 0xa0 and an error code of 0x1000.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="56b73-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="56b73-113">Requirements</span></span>  

 <span data-ttu-id="56b73-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="56b73-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="56b73-115">**헤더:** SOS_Stacktrace. h</span><span class="sxs-lookup"><span data-stu-id="56b73-115">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="56b73-116">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="56b73-116">**.NET Framework Version:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56b73-117">참조</span><span class="sxs-lookup"><span data-stu-id="56b73-117">See also</span></span>

- [<span data-ttu-id="56b73-118">디버깅 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="56b73-118">Debugging Global Static Functions</span></span>](debugging-global-static-functions.md)
