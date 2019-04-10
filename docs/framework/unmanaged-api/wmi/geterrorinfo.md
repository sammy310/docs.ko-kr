---
title: GetErrorInfo 함수 (관리 되지 않는 API 참조)
description: GetErrorInfo 함수는 이전 함수 호출에서 오류 정보를 검색합니다.
ms.date: 11/06/2017
api_name:
- GetErrorInfo
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetErrorInfo
helpviewer_keywords:
- GetErrorInfo function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c2df4b87016394d1998ef90abe2e3eeb911886ef
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59217507"
---
# <a name="geterrorinfo-function"></a><span data-ttu-id="46f1b-103">GetErrorInfo 함수</span><span class="sxs-lookup"><span data-stu-id="46f1b-103">GetErrorInfo function</span></span>
<span data-ttu-id="46f1b-104">이전 함수 호출에서 오류 정보를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="46f1b-104">Retrieves error information from the previous function call.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="46f1b-105">구문</span><span class="sxs-lookup"><span data-stu-id="46f1b-105">Syntax</span></span>  
  
```  
IErrorInfo* GetErrorInfo(); 
```  

## <a name="return-value"></a><span data-ttu-id="46f1b-106">반환 값</span><span class="sxs-lookup"><span data-stu-id="46f1b-106">Return value</span></span>

<span data-ttu-id="46f1b-107">에 대 한 포인터를 [IErrorInfo](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo) 함수 호출에 성공 하면 개체 또는 `null` 실패 한 경우.</span><span class="sxs-lookup"><span data-stu-id="46f1b-107">An pointer to an [IErrorInfo](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo) object if the function call succeeds, or `null` if it fails.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="46f1b-108">설명</span><span class="sxs-lookup"><span data-stu-id="46f1b-108">Remarks</span></span>

<span data-ttu-id="46f1b-109">이 함수에 대 한 호출을 래핑하는 [IComThreadingInfo::GetErrorInfo](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) 메서드.</span><span class="sxs-lookup"><span data-stu-id="46f1b-109">This function wraps a call to the [IComThreadingInfo::GetErrorInfo](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="46f1b-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="46f1b-110">Requirements</span></span>  
 <span data-ttu-id="46f1b-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="46f1b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46f1b-112">**헤더:** WMINet_Utils.def</span><span class="sxs-lookup"><span data-stu-id="46f1b-112">**Header:** WMINet_Utils.def</span></span>  
  
 **<span data-ttu-id="46f1b-113">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="46f1b-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a><span data-ttu-id="46f1b-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="46f1b-114">See also</span></span>

- [<span data-ttu-id="46f1b-115">WMI 및 성능 카운터(관리되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="46f1b-115">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
